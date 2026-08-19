---
name: audit-search-performance
description: Pull Google Search traffic for a verified Search Console property and break it down by query, page, country, device or date, paging safely past the 25,000-row ceiling.
api: Google Search Console Search Analytics API
openapi: openapi/google-search-console-search-analytics-api-openapi.yml
operations:
  - listSites
  - querySearchAnalytics
scopes:
  - https://www.googleapis.com/auth/webmasters.readonly
generated: '2026-08-13'
method: generated
source: openapi/google-search-console-search-analytics-api-openapi.yml, openapi/google-search-console-sites-api-openapi.yml, conventions/google-search-console-conventions.yml, errors/google-search-console-problem-types.yml
---

# Audit search performance

Base URL `https://searchconsole.googleapis.com`. OAuth 2.0 bearer token with
`https://www.googleapis.com/auth/webmasters.readonly`.

## 1. Resolve the property string before anything else

Call `listSites` (`GET /webmasters/v3/sites`) and take `siteUrl` verbatim from the response. Do not
construct it. A URL-prefix property carries a trailing slash (`https://www.example.com/`); a domain
property is `sc-domain:example.com`. Guessing the wrong form is what produces a 403
`insufficientPermissions`, not a 404 — the API cannot tell "you typed it wrong" from "you do not
own this".

Percent-encode the chosen `siteUrl` when placing it in the path.

## 2. Query

`POST /webmasters/v3/sites/{siteUrl}/searchAnalytics/query` — `querySearchAnalytics`.

```json
{
  "startDate": "2026-07-01",
  "endDate": "2026-07-31",
  "dimensions": ["QUERY", "PAGE"],
  "type": "WEB",
  "rowLimit": 25000,
  "startRow": 0,
  "dataState": "final"
}
```

- `startDate` and `endDate` are **PT (UTC-7:00/8:00), not UTC**. If you are reconciling against a
  UTC warehouse, expect a one-day boundary skew and correct for it explicitly.
- `dimensions` is ordered, and the response's `rows[].keys` array is positional against it. Keep the
  request beside the response or the row keys are uninterpretable.
- Valid dimensions: `DATE`, `QUERY`, `PAGE`, `COUNTRY`, `DEVICE`, `SEARCH_APPEARANCE`, `HOUR`.
  `HOUR` requires `dataState: "HOURLY_ALL"` and only goes back 10 days.
- `type` is `WEB` (default), `IMAGE`, `VIDEO`, `NEWS`, `DISCOVER` or `GOOGLE_NEWS`.
- Data lags two to three days. `dataState: "all"` includes fresh partial data; the default includes
  only finalized data.

## 3. Page

There is no page token and no total count. Increment `startRow` by `rowLimit` and stop when a
response returns fewer than `rowLimit` rows.

```
startRow=0      rowLimit=25000  -> 25000 rows  -> continue
startRow=25000  rowLimit=25000  -> 25000 rows  -> continue
startRow=50000  rowLimit=25000  ->  8123 rows  -> done
```

Add `?fields=rows(keys,clicks,impressions,ctr,position)` to trim the payload.

## 4. Filter without grouping

`dimensionFilterGroups[].filters[]` takes `{dimension, operator, expression}` with operators
`contains`, `notContains`, `equals`, `notEquals`, `includingRegex`, `excludingRegex`. You can filter
on a dimension you did not group by — filter `PAGE contains /blog/` while grouping only by `QUERY`.

Note: if you group or filter by `PAGE`, you cannot set `aggregationType: BY_PROPERTY`. Use `AUTO`.

## 5. Handle throttling as the only signal you get

There are no `X-RateLimit-*` headers on this API. The first indication you are near a ceiling is the
error itself, so backoff is mandatory:

- **403 `rateLimitExceeded` / 429 `rateLimitExceeded`** — retry with exponential backoff and jitter.
  Search Analytics load is measured in 10-minute and 1-day windows, so you can be throttled below
  the documented 1,200 QPM per site.
- **403 `userRateLimitExceeded`** — you are over 20 QPS / 200 QPM per user. Serialize.
- **403 `dailyLimitExceeded`** — not retryable today. Stop and resume after the reset.
- **403 `insufficientPermissions`** — never retry. Re-check the `siteUrl` form and the account's
  access to the property.

Branch on `error.errors[0].reason`, not on `error.message` and not on the HTTP status alone — 403
covers both "back off" and "give up".

For server-side jobs serving many end users, set `quotaUser` to a stable per-user string (≤40 chars)
so one tenant cannot exhaust the shared per-user quota.
