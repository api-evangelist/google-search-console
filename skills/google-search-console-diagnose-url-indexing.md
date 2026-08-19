---
name: diagnose-url-indexing
description: Determine why a specific page is or is not in the Google index — crawl state, canonical, robots.txt verdict, rich-results eligibility — and confirm which sitemap references it.
api: Google Search Console URL Inspection API
openapi: openapi/google-search-console-url-inspection-api-openapi.yml
operations:
  - listSites
  - inspectUrl
  - listSitemaps
  - searchconsole_urlTestingTools_mobileFriendlyTest_run
scopes:
  - https://www.googleapis.com/auth/webmasters.readonly
generated: '2026-08-13'
method: generated
source: openapi/google-search-console-url-inspection-api-openapi.yml, openapi/google-search-console-url-testing-tools-api-openapi.yml, openapi/_original/google-search-console-searchconsole-v1-discovery.json, errors/google-search-console-problem-types.yml
---

# Diagnose why a URL is not indexed

Base URL `https://searchconsole.googleapis.com`. OAuth 2.0 with
`https://www.googleapis.com/auth/webmasters.readonly`.

## 1. Inspect the URL

`POST /v1/urlInspection/index:inspect` — `inspectUrl`.

```json
{
  "inspectionUrl": "https://www.example.com/pricing",
  "siteUrl": "https://www.example.com/",
  "languageCode": "en-US"
}
```

Both fields are required. `inspectionUrl` must fall inside the property named by `siteUrl`, and
`siteUrl` must be the exact verified property string from `listSites`.

## 2. Read the verdict in order

`inspectionResult.indexStatusResult` is where the answer is:

| Field | What it tells you |
| --- | --- |
| `verdict` | `PASS`, `PARTIAL`, `FAIL`, `NEUTRAL` — the headline |
| `coverageState` | The human-readable reason, e.g. "Submitted and indexed", "Crawled - currently not indexed" |
| `robotsTxtState` | `ALLOWED` / `DISALLOWED` — check this before anything else |
| `indexingState` | `INDEXING_ALLOWED`, `BLOCKED_BY_META_TAG`, `BLOCKED_BY_HTTP_HEADER`, `BLOCKED_BY_ROBOTS_TXT` |
| `pageFetchState` | Whether Google could fetch it at all |
| `googleCanonical` vs `userCanonical` | If these disagree, Google picked a different canonical and your page is being folded into another |
| `lastCrawlTime` | Stale here means the problem may already be fixed but not yet recrawled |
| `crawledAs` | `MOBILE` or `DESKTOP` user agent |
| `sitemap[]` | Which submitted sitemaps reference this URL — empty is a finding |
| `referringUrls[]` | Internal links Google found pointing at it |

Diagnose in this order: robots → indexingState → pageFetchState → canonical → coverageState.

## 3. Cross-check the sitemap

If `indexStatusResult.sitemap[]` is empty, the page is not in any submitted sitemap. Confirm with
`listSitemaps` (`GET /webmasters/v3/sites/{siteUrl}/sitemaps`) and check the `errors` and `warnings`
counts on the sitemap that should contain it, then use the manage-sitemaps skill.

## 4. Rich results

`inspectionResult.richResultsResult.detectedItems[]` groups by `richResultType`, each with
`items[].issues[]`. An item with issues is structured data Google parsed but rejected — fix those
before assuming the markup is absent.

Do **not** read `inspectionResult.mobileUsabilityResult`. It is marked `deprecated: true` in
Google's own Discovery document. For a live mobile check use
`POST /v1/urlTestingTools/mobileFriendlyTest:run` — the one operation on this whole surface that
declares no OAuth scope — with `{"url": "...", "requestScreenshot": false}` and read `testStatus`,
`mobileFriendliness`, `mobileFriendlyIssues[]` and `resourceIssues[]`.

## 5. Budget the calls

URL Inspection is the tightest quota on the product: **2,000 queries per day and 600 per minute, per
site**. That is a hard daily ceiling, not a rate to back off from.

- Never inspect a whole sitemap in a loop. Inspect the pages that Search Analytics already shows as
  losing impressions, or the ones a crawl flagged.
- **403 `dailyLimitExceeded`** is terminal for the day — stop, do not retry, resume tomorrow.
- **403 / 429 `rateLimitExceeded`** — exponential backoff with jitter.
- **403 `insufficientPermissions`** — the `siteUrl` form is wrong or the account does not own the
  property. Never retry.
