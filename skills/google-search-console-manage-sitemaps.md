---
name: manage-sitemaps
description: List, submit, inspect and delete sitemaps for a verified Search Console property, and read their processing state and error counts.
api: Google Search Console Sitemaps API
openapi: openapi/google-search-console-sitemaps-api-openapi.yml
operations:
  - listSites
  - listSitemaps
  - getSitemap
  - submitSitemap
  - deleteSitemap
scopes:
  - https://www.googleapis.com/auth/webmasters
  - https://www.googleapis.com/auth/webmasters.readonly
generated: '2026-08-13'
method: generated
source: openapi/google-search-console-sitemaps-api-openapi.yml, conventions/google-search-console-conventions.yml, errors/google-search-console-problem-types.yml
---

# Manage sitemaps

Base URL `https://searchconsole.googleapis.com`. Reads need
`https://www.googleapis.com/auth/webmasters.readonly`; writes need
`https://www.googleapis.com/auth/webmasters`.

## Path encoding is the whole game

Both `{siteUrl}` and `{feedpath}` are full URLs sitting inside a path segment, so both must be
percent-encoded:

```
siteUrl   https://www.example.com/                    -> https%3A%2F%2Fwww.example.com%2F
feedpath  https://www.example.com/sitemap.xml         -> https%3A%2F%2Fwww.example.com%2Fsitemap.xml
```

Encode once, not twice. Most 404s on this API are an unencoded or double-encoded feedpath, not a
missing sitemap.

## 1. List — `listSitemaps`

`GET /webmasters/v3/sites/{siteUrl}/sitemaps`

Optional `sitemapIndex` query parameter restricts the result to sitemaps listed inside that index.
Returns both manually submitted sitemaps and ones discovered via robots.txt.

Per entry: `path`, `lastSubmitted`, `lastDownloaded`, `isPending`, `isSitemapsIndex`, `type`,
`warnings`, `errors`, and `contents[]` with `{type, submitted, indexed}`.

`isPending: true` means Google has accepted the sitemap but not processed it yet — the counts are
not final. Do not treat a pending sitemap as failed.

Ignore `contents[].indexed`: it is marked `deprecated: true` in Google's Discovery document with
the text "*Deprecated; do not use.*". Use the URL Inspection API for per-page index status instead.

## 2. Get one — `getSitemap`

`GET /webmasters/v3/sites/{siteUrl}/sitemaps/{feedpath}` — same shape, one entry.

## 3. Submit — `submitSitemap`

`PUT /webmasters/v3/sites/{siteUrl}/sitemaps/{feedpath}` with no request body. Returns 204.

`PUT`, not `POST` — sending `POST` returns 405 `httpMethodNotAllowed`.

Because it is a `PUT` it is idempotent: re-submitting the same feedpath after a timeout is safe and
simply refreshes `lastSubmitted`. There is no `Idempotency-Key` header on this API and none is
needed here.

The sitemap must already be reachable at that URL — Google fetches it asynchronously, so a 204 means
"accepted", not "valid". Poll `getSitemap` afterwards and read `errors` and `warnings`.

## 4. Delete — `deleteSitemap`

`DELETE /webmasters/v3/sites/{siteUrl}/sitemaps/{feedpath}`. Returns 204. Also idempotent.

This removes the submission, not the file. If the sitemap is still referenced from robots.txt Google
will rediscover it.

## Errors

Branch on `error.errors[0].reason`:

- **404 `notFound`** — check the encoding first, then whether the sitemap was ever submitted.
- **403 `insufficientPermissions`** — the account is not an owner of this property, or the `siteUrl`
  string does not match the verified property exactly (trailing slash, `sc-domain:` prefix).
- **400 `badRequest`** — usually a malformed feedpath.
- **403 / 429 `rateLimitExceeded`** — sitemaps fall under "all other resources": 20 QPS and 200 QPM
  per user. Back off exponentially with jitter; there are no rate-limit response headers to read.
