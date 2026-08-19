---
name: notify-google-of-url-changes
description: Tell Google that a page was published, updated or removed using the Web Search Indexing API, and confirm the notification landed.
api: Web Search Indexing API
openapi: openapi/google-search-console-indexing-api-openapi.yml
operations:
  - indexing_urlNotifications_publish
  - indexing_urlNotifications_getMetadata
scopes:
  - https://www.googleapis.com/auth/indexing
generated: '2026-08-13'
method: generated
source: openapi/google-search-console-indexing-api-openapi.yml, openapi/_original/google-search-console-indexing-v3-discovery.json, https://developers.google.com/search/apis/indexing-api/v3/quickstart, errors/google-search-console-problem-types.yml
---

# Notify Google that a URL changed

Base URL `https://indexing.googleapis.com`. This is a **different host and a different OAuth scope**
from the rest of Search Console: `https://www.googleapis.com/auth/indexing`. A token minted for
`webmasters` will not work here.

## Prerequisite that is not in the contract

The calling identity is normally a service account, and that service account must be added as an
**Owner of the property inside Search Console** — not merely granted a Google Cloud IAM role.
Skipping this is the standard cause of a 403 on a request that looks correct. The Indexing API also
has to be enabled on the Cloud project, or you get 403 `accessNotConfigured`.

## 1. Publish — `indexing_urlNotifications_publish`

`POST /v3/urlNotifications:publish`

```json
{
  "url": "https://www.example.com/jobs/12345",
  "type": "URL_UPDATED"
}
```

`type` is `URL_UPDATED` (published or changed) or `URL_DELETED` (removed — the page must actually
return 404/410 or be noindexed, or the notification is ignored).

The response echoes the notification back as `urlNotificationMetadata`, carrying `latestUpdate`
and/or `latestRemove` with a `notifyTime`.

Do not batch a whole sitemap through this endpoint. Google's documented scope for the Indexing API
is pages whose value decays fast; for everything else the sitemap is the right channel.

## 2. Confirm — `indexing_urlNotifications_getMetadata`

`GET /v3/urlNotifications/metadata?url=<url-encoded page URL>`

Returns the last `URL_UPDATED` and `URL_DELETED` notification Google recorded for that URL. Use it
to prove the publish landed and to avoid re-notifying a URL you already sent.

A 404 here means Google has no record of a notification for that URL — expected before the first
publish, a finding afterwards.

## 3. Retries

This endpoint has **no idempotency key** and `POST` is not idempotent. Republishing the same URL does
no harm to the index, but it consumes quota every time. So:

- Before a blind retry, call `getMetadata` and compare `latestUpdate.notifyTime`. If your
  notification is already recorded, the original call succeeded and the failure was in the response
  path — do not resend.
- Retry only on **429**, **500 `internalError`** and **503 `backendError`**, with exponential backoff
  and jitter.
- Never retry **400 `invalid`** (URL outside the owned property, or a bad `type`), **401
  `authError`**, or **403 `insufficientPermissions`**.

There are no rate-limit response headers. The Indexing API falls under the "all other resources"
quota — 20 QPS and 200 QPM per user — on top of a separate publish quota that Google grants per
project.

## Error codes to branch on

Read `error.errors[0].reason`, not `error.message`:

`invalid`, `required`, `authError`, `insufficientPermissions`, `accessNotConfigured`,
`rateLimitExceeded`, `dailyLimitExceeded`, `quotaExceeded`, `internalError`, `backendError`.
Full catalogue in `errors/google-search-console-problem-types.yml`.
