# Google Search Console

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Google Search Console gives site owners programmatic access to how their site appears in Google Search. Three separately versioned Google APIs make up the surface: the Search Console API for search analytics, sitemaps, site management and URL inspection; the URL Testing Tools API for the mobile-friendly test; and the Web Search Indexing API for telling Google that a page was published, updated or removed. All three are free of charge, authenticate with Google OAuth 2.0 against accounts.google.com, are authorized per verified property rather than per Cloud project, and are described by Google Discovery documents rather than a published OpenAPI.

**Areas:** Analytics · Google · Indexing · Search · Search Analytics · SEO · Sitemap · URL Inspection · Webmaster Tools

## Google Search Console on APIs.io

Everything profiled for Google Search Console is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/google-search-console/](https://apis.io/providers/google-search-console/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [Google Search Console Search Analytics API](https://apis.io/apis/google-search-console/google-search-console-search-analytics-api/) — Query search traffic data for your site. Retrieve impressions, clicks, click-through rate, and average position grouped by dimensions such as query, page,…
- [Google Search Console Sitemaps API](https://apis.io/apis/google-search-console/google-search-console-sitemaps-api/) — Submit and manage sitemaps and sitemap indexes for your site. List submitted sitemaps, check their processing status, submit new sitemaps, and delete…
- [Google Search Console Sites API](https://apis.io/apis/google-search-console/google-search-console-sites-api/) — Manage site-level access and verification. List verified sites, get details about a specific site, add new sites, and remove sites from your Search Console…
- [Google Search Console URL Inspection API](https://apis.io/apis/google-search-console/google-search-console-url-inspection-api/) — Inspect individual URLs to retrieve detailed indexing, crawling, and serving information. Check whether a URL is indexed, view crawl details, mobile…
- [Google Search Console URL Notifications API](https://apis.io/apis/google-search-console/google-search-console-urlnotifications-api/) — The urlNotifications API from Google Search Console — 2 operation(s) for urlnotifications.
- [Google Search Console URL Testing Tools API](https://apis.io/apis/google-search-console/google-search-console-urltestingtools-api/) — The urlTestingTools API from Google Search Console — 1 operation(s) for urltestingtools.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [google-search-console-mcp.yml](https://apis.io/servers/google-search-console/google-search-console-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Google Search Console Agentic Access](https://apis.io/agentic-access/google-search-console/google-search-console-agentic-access/)

#### JSON Schema (22)

The data models the API reads and writes.

- [DetectedItems](https://apis.io/schemas/google-search-console/google-search-console-detected-items/)
- [DimensionFilter](https://apis.io/schemas/google-search-console/google-search-console-dimension-filter/)
- [DimensionFilterGroup](https://apis.io/schemas/google-search-console/google-search-console-dimension-filter-group/)
- [Error](https://apis.io/schemas/google-search-console/google-search-console-error/)
- [IndexStatusInspectionResult](https://apis.io/schemas/google-search-console/google-search-console-index-status-inspection-result/)
- [InspectUrlIndexRequest](https://apis.io/schemas/google-search-console/google-search-console-inspect-url-index-request/)
- [InspectUrlIndexResponse](https://apis.io/schemas/google-search-console/google-search-console-inspect-url-index-response/)
- [Item](https://apis.io/schemas/google-search-console/google-search-console-item/)
- [MobileUsabilityInspectionResult](https://apis.io/schemas/google-search-console/google-search-console-mobile-usability-inspection-result/)
- [MobileUsabilityIssue](https://apis.io/schemas/google-search-console/google-search-console-mobile-usability-issue/)
- [Google Search Console Search Analytics Query](https://apis.io/schemas/google-search-console/google-search-console-query/)
- [RichResultsInspectionResult](https://apis.io/schemas/google-search-console/google-search-console-rich-results-inspection-result/)
- [RichResultsIssue](https://apis.io/schemas/google-search-console/google-search-console-rich-results-issue/)
- [SearchAnalyticsQueryRequest](https://apis.io/schemas/google-search-console/google-search-console-search-analytics-query-request/)
- [SearchAnalyticsQueryResponse](https://apis.io/schemas/google-search-console/google-search-console-search-analytics-query-response/)
- [SearchAnalyticsRow](https://apis.io/schemas/google-search-console/google-search-console-search-analytics-row/)
- [SitemapsListResponse](https://apis.io/schemas/google-search-console/google-search-console-sitemaps-list-response/)
- [SitesListResponse](https://apis.io/schemas/google-search-console/google-search-console-sites-list-response/)
- [UrlInspectionResult](https://apis.io/schemas/google-search-console/google-search-console-url-inspection-result/)
- [WmxSite](https://apis.io/schemas/google-search-console/google-search-console-wmx-site/)
- [WmxSitemap](https://apis.io/schemas/google-search-console/google-search-console-wmx-sitemap/)
- [WmxSitemapContent](https://apis.io/schemas/google-search-console/google-search-console-wmx-sitemap-content/)

#### JSON Structure (21)

Data models expressed in JSON Structure.

- [Google Search Console Detected Items Structure](https://apis.io/json-structure/google-search-console/google-search-console-detected-items-structure/)
- [Google Search Console Dimension Filter Group Structure](https://apis.io/json-structure/google-search-console/google-search-console-dimension-filter-group-structure/)
- [Google Search Console Dimension Filter Structure](https://apis.io/json-structure/google-search-console/google-search-console-dimension-filter-structure/)
- [Google Search Console Error Structure](https://apis.io/json-structure/google-search-console/google-search-console-error-structure/)
- [Google Search Console Index Status Inspection Result Structure](https://apis.io/json-structure/google-search-console/google-search-console-index-status-inspection-result-structure/)
- [Google Search Console Inspect Url Index Request Structure](https://apis.io/json-structure/google-search-console/google-search-console-inspect-url-index-request-structure/)
- [Google Search Console Inspect Url Index Response Structure](https://apis.io/json-structure/google-search-console/google-search-console-inspect-url-index-response-structure/)
- [Google Search Console Item Structure](https://apis.io/json-structure/google-search-console/google-search-console-item-structure/)
- [Google Search Console Mobile Usability Inspection Result Structure](https://apis.io/json-structure/google-search-console/google-search-console-mobile-usability-inspection-result-structure/)
- [Google Search Console Mobile Usability Issue Structure](https://apis.io/json-structure/google-search-console/google-search-console-mobile-usability-issue-structure/)
- [Google Search Console Rich Results Inspection Result Structure](https://apis.io/json-structure/google-search-console/google-search-console-rich-results-inspection-result-structure/)
- [Google Search Console Rich Results Issue Structure](https://apis.io/json-structure/google-search-console/google-search-console-rich-results-issue-structure/)
- [Google Search Console Search Analytics Query Request Structure](https://apis.io/json-structure/google-search-console/google-search-console-search-analytics-query-request-structure/)
- [Google Search Console Search Analytics Query Response Structure](https://apis.io/json-structure/google-search-console/google-search-console-search-analytics-query-response-structure/)
- [Google Search Console Search Analytics Row Structure](https://apis.io/json-structure/google-search-console/google-search-console-search-analytics-row-structure/)
- [Google Search Console Sitemaps List Response Structure](https://apis.io/json-structure/google-search-console/google-search-console-sitemaps-list-response-structure/)
- [Google Search Console Sites List Response Structure](https://apis.io/json-structure/google-search-console/google-search-console-sites-list-response-structure/)
- [Google Search Console Url Inspection Result Structure](https://apis.io/json-structure/google-search-console/google-search-console-url-inspection-result-structure/)
- [Google Search Console Wmx Site Structure](https://apis.io/json-structure/google-search-console/google-search-console-wmx-site-structure/)
- [Google Search Console Wmx Sitemap Content Structure](https://apis.io/json-structure/google-search-console/google-search-console-wmx-sitemap-content-structure/)
- [Google Search Console Wmx Sitemap Structure](https://apis.io/json-structure/google-search-console/google-search-console-wmx-sitemap-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Google Search Console Context](https://apis.io/jsonld/google-search-console/google-search-console-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [google-search-console API Vocabulary](https://apis.io/vocabularies/google-search-console/google-search-console-vocabulary/)

#### Examples (21)

Example requests and responses.

- [Google Search Console Detected Items Example](https://apis.io/examples/google-search-console/google-search-console-detected-items-example/)
- [Google Search Console Dimension Filter Example](https://apis.io/examples/google-search-console/google-search-console-dimension-filter-example/)
- [Google Search Console Dimension Filter Group Example](https://apis.io/examples/google-search-console/google-search-console-dimension-filter-group-example/)
- [Google Search Console Error Example](https://apis.io/examples/google-search-console/google-search-console-error-example/)
- [Google Search Console Index Status Inspection Result Example](https://apis.io/examples/google-search-console/google-search-console-index-status-inspection-result-example/)
- [Google Search Console Inspect Url Index Request Example](https://apis.io/examples/google-search-console/google-search-console-inspect-url-index-request-example/)
- [Google Search Console Inspect Url Index Response Example](https://apis.io/examples/google-search-console/google-search-console-inspect-url-index-response-example/)
- [Google Search Console Item Example](https://apis.io/examples/google-search-console/google-search-console-item-example/)
- [Google Search Console Mobile Usability Inspection Result Example](https://apis.io/examples/google-search-console/google-search-console-mobile-usability-inspection-result-example/)
- [Google Search Console Mobile Usability Issue Example](https://apis.io/examples/google-search-console/google-search-console-mobile-usability-issue-example/)
- [Google Search Console Rich Results Inspection Result Example](https://apis.io/examples/google-search-console/google-search-console-rich-results-inspection-result-example/)
- [Google Search Console Rich Results Issue Example](https://apis.io/examples/google-search-console/google-search-console-rich-results-issue-example/)
- [Google Search Console Search Analytics Query Request Example](https://apis.io/examples/google-search-console/google-search-console-search-analytics-query-request-example/)
- [Google Search Console Search Analytics Query Response Example](https://apis.io/examples/google-search-console/google-search-console-search-analytics-query-response-example/)
- [Google Search Console Search Analytics Row Example](https://apis.io/examples/google-search-console/google-search-console-search-analytics-row-example/)
- [Google Search Console Sitemaps List Response Example](https://apis.io/examples/google-search-console/google-search-console-sitemaps-list-response-example/)
- [Google Search Console Sites List Response Example](https://apis.io/examples/google-search-console/google-search-console-sites-list-response-example/)
- [Google Search Console Url Inspection Result Example](https://apis.io/examples/google-search-console/google-search-console-url-inspection-result-example/)
- [Google Search Console Wmx Site Example](https://apis.io/examples/google-search-console/google-search-console-wmx-site-example/)
- [Google Search Console Wmx Sitemap Content Example](https://apis.io/examples/google-search-console/google-search-console-wmx-sitemap-content-example/)
- [Google Search Console Wmx Sitemap Example](https://apis.io/examples/google-search-console/google-search-console-wmx-sitemap-example/)

#### Collections (11)

Postman and Open Collection request collections.

- [Google Search Console API](https://apis.io/collections/google-search-console/open-google-search-console-api/)
- [Google Web Search Indexing API](https://apis.io/collections/google-search-console/open-google-search-console-indexing-api/)
- [Google Search Console Search Analytics API](https://apis.io/collections/google-search-console/open-google-search-console-search-analytics-api/)
- [Google Search Console Search Analytics Sitemaps API](https://apis.io/collections/google-search-console/open-google-search-console-sitemaps-api/)
- [Google Search Console Search Analytics Sites API](https://apis.io/collections/google-search-console/open-google-search-console-sites-api/)
- [Google Search Console Search Analytics URL Inspection API](https://apis.io/collections/google-search-console/open-google-search-console-url-inspection-api/)
- [Google Search Console URL Testing Tools API](https://apis.io/collections/google-search-console/open-google-search-console-url-testing-tools-api/)
- [Google Search Console Search Analytics API](https://apis.io/collections/google-search-console/postman-google-search-console-search-analytics-api/)
- [Google Search Console Search Analytics Sitemaps API](https://apis.io/collections/google-search-console/postman-google-search-console-sitemaps-api/)
- [Google Search Console Search Analytics Sites API](https://apis.io/collections/google-search-console/postman-google-search-console-sites-api/)
- [Google Search Console Search Analytics URL Inspection API](https://apis.io/collections/google-search-console/postman-google-search-console-url-inspection-api/)

#### Overlays (12)

OpenAPI overlays, including conversational phrasing for each operation.

- [Google Search Console Indexing Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-indexing-api-overlay/)
- [Google Search Console Search Analytics Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-search-analytics-api-overlay/)
- [Google Search Console Search Analytics Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-search-analytics-api-phrasing-overlay/)
- [Google Search Console Sitemaps Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-sitemaps-api-overlay/)
- [Google Search Console Sitemaps Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-sitemaps-api-phrasing-overlay/)
- [Google Search Console Sites Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-sites-api-overlay/)
- [Google Search Console Sites Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-sites-api-phrasing-overlay/)
- [Google Search Console Url Inspection Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-url-inspection-api-overlay/)
- [Google Search Console Url Inspection Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-url-inspection-api-phrasing-overlay/)
- [Google Search Console Url Testing Tools Api Overlay](https://apis.io/overlays/google-search-console/google-search-console-url-testing-tools-api-overlay/)
- [Google Search Console Urlnotifications Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-urlnotifications-api-phrasing-overlay/)
- [Google Search Console Urltestingtools Api Phrasing Overlay](https://apis.io/overlays/google-search-console/google-search-console-urltestingtools-api-phrasing-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Google Search Console — jsonschema rules](https://apis.io/rules/google-search-console/google-search-console-jsonschema-spectral-rules/)
- [Google Search Console API Rules](https://apis.io/rules/google-search-console/google-search-console-spectral-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Google Search Console Authentication](https://apis.io/security/google-search-console/google-search-console-authentication/)
- [Google Search Console Domain Security](https://apis.io/security/google-search-console/google-search-console-domain-security/)
- [Google Search Console Vulnerability Disclosure](https://apis.io/security/google-search-console/google-search-console-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Google Search Console Scopes](https://apis.io/scopes/google-search-console/google-search-console-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Google Search Console Plans Pricing](https://apis.io/plans/google-search-console/google-search-console-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Google Search Console Rate Limits](https://apis.io/rate-limits/google-search-console/google-search-console-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Google Search Console Finops](https://apis.io/finops/google-search-console/google-search-console-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.google.com/)
- [Documentation](https://developers.google.com/webmaster-tools)
- [Getting started](https://developers.google.com/webmaster-tools/v1/quickstart/quickstart-python)
- [API reference](https://developers.google.com/webmaster-tools/v1/api_reference_index)
- [Pricing](https://developers.google.com/webmaster-tools/limits)
- [Sign up](https://search.google.com/search-console/welcome)
- [Support](https://support.google.com/webmasters/)
- [Blog](https://developers.googleblog.com/)
- [Terms of service](https://policies.google.com/terms)
- [Privacy policy](https://policies.google.com/privacy)
- [GitHub](https://github.com/googleapis)
- [Status](https://status.search.google.com/)

## API Evangelist rating

**Kin Score 67.2** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 63.4 |
| Contract governance | 18.2 |
| Operational transparency | 76.3 |
| Developer ergonomics | 75.6 |
| Access clarity | 65.8 |

**Agent readiness 37.9** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 40.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/google-search-console/](https://apis.io/providers/google-search-console/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Google Search Console: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/google-search-console/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
