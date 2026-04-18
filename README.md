# Google Search Console (google-search-console)
The Google Search Console API provides programmatic access to Search Console data, allowing you to monitor and maintain your site's presence in Google Search results.

**URL:** [Visit APIs.json URL](https://search.google.com/search-console/about)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Analytics, Google, Search, SEO, Webmaster Tools

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-04-18

## APIs

### Google Search Console API
Provides access to Search Console data including search analytics, sitemaps, URL inspection, and index coverage reports.

**Human URL:** [https://developers.google.com/webmaster-tools](https://developers.google.com/webmaster-tools)

#### Tags:

 - Indexing, Search Analytics, SEO, Sitemaps

#### Properties

- [Documentation](https://developers.google.com/webmaster-tools/v1/api_reference_index)
- [OpenAPI](openapi/google-search-console-api-openapi.yml)
- [Discovery Document](https://searchconsole.googleapis.com/$discovery/rest?version=v1)
- [Authentication](https://developers.google.com/webmaster-tools/v1/how-tos/authorizing)
- [GettingStarted](https://developers.google.com/webmaster-tools/v1/quickstart)
- [Console](https://console.cloud.google.com/apis/library/searchconsole.googleapis.com)
- [Pricing](https://developers.google.com/webmaster-tools/v1/limits)
- [TermsOfService](https://developers.google.com/terms)
- [CodeExamples](https://developers.google.com/webmaster-tools/v1/samples)
- [ChangeLog](https://developers.google.com/webmaster-tools/v1/release-notes)
- [Support](https://support.google.com/webmasters/)
- [Overview](https://developers.google.com/webmaster-tools/about)
- [Python Quickstart](https://developers.google.com/webmaster-tools/v1/quickstart/quickstart-python)
- [Client Libraries](https://developers.google.com/webmaster-tools/v1/libraries)
- [JSONSchema](json-schema/google-search-console-query-schema.json)
- [JSONLD](json-ld/google-search-console-context.jsonld)

### Google Search Console URL Testing Tools API
Provides tools for running validation tests against single URLs, including mobile-friendly testing and rich results validation for structured data.

**Human URL:** [https://developers.google.com/webmaster-tools/search-console-api](https://developers.google.com/webmaster-tools/search-console-api)

#### Tags:

 - Mobile Friendly, Rich Results, Structured Data, Testing, Validation

#### Properties

- [Documentation](https://developers.google.com/webmaster-tools/search-console-api/v1/)
- [About](https://developers.google.com/webmaster-tools/search-console-api/about)
- [Rich Results Test](https://search.google.com/test/rich-results)

### Google Indexing API
The Indexing API allows any site owner to directly notify Google when pages are added or removed, enabling faster crawling and indexing of content such as job postings and livestream videos.

**Human URL:** [https://developers.google.com/search/apis/indexing-api/v3/quickstart](https://developers.google.com/search/apis/indexing-api/v3/quickstart)

#### Tags:

 - Crawling, Indexing, SEO, URL Submission

#### Properties

- [Documentation](https://developers.google.com/search/apis/indexing-api/v3/reference/indexing/rest)
- [GettingStarted](https://developers.google.com/search/apis/indexing-api/v3/quickstart)
- [Tutorials](https://developers.google.com/search/apis/indexing-api/v3/using-api)
- [Pricing](https://developers.google.com/search/apis/indexing-api/v3/quota-pricing)
- [Client Libraries](https://developers.google.com/search/apis/indexing-api/v3/libraries)

## Common Properties

- [DeveloperPortal](https://developers.google.com/)
- [StatusPage](https://status.cloud.google.com/)
- [Blog](https://developers.googleblog.com/)
- [PrivacyPolicy](https://policies.google.com/privacy)
- [TermsOfService](https://policies.google.com/terms)
- [OAuth 2.0 Scopes](https://developers.google.com/identity/protocols/oauth2/scopes)
- [API Client Libraries](https://developers.google.com/api-client-library)
- [Console](https://console.cloud.google.com/)

## Features

| Name | Description |
|------|-------------|
| Search Analytics | Analyze search traffic data including impressions, clicks, CTR, and average position by query, page, country, device, and date. |
| Sitemap Management | Submit, monitor, and manage XML sitemaps and sitemap indexes to optimize crawling and indexing. |
| URL Inspection | Inspect individual URLs for indexing status, crawl details, mobile usability, and rich results eligibility. |
| Index Coverage | Monitor which pages are indexed, identify indexing errors, and track coverage status across your site. |
| Mobile Usability Testing | Test pages for mobile-friendliness and identify mobile usability issues. |
| Rich Results Validation | Validate structured data markup and check rich results eligibility for individual URLs. |
| Site Verification | Manage site ownership verification and access permissions for Search Console properties. |

## Use Cases

| Name | Description |
|------|-------------|
| SEO Performance Monitoring | Track organic search performance metrics to identify trends, measure optimization impact, and report on search visibility. |
| Technical SEO Auditing | Identify and resolve indexing issues, crawl errors, and mobile usability problems affecting search performance. |
| Content Optimization | Analyze which queries drive traffic to specific pages and optimize content to improve rankings and click-through rates. |
| Automated Sitemap Submission | Programmatically submit sitemaps when content is published or updated to accelerate indexing. |
| Multi-Site Management | Monitor and manage search performance across multiple websites from a single integration. |

## Integrations

| Name | Description |
|------|-------------|
| Google Analytics | Combine Search Console data with Google Analytics for comprehensive website performance analysis. |
| Google Ads | Connect search performance data with advertising campaigns to optimize paid and organic strategy together. |
| Google Cloud | Deploy Search Console API integrations on Google Cloud Platform infrastructure. |
| BigQuery | Export Search Console data to BigQuery for advanced analytics and cross-platform reporting. |
| Data Studio / Looker | Visualize Search Console metrics in dashboards for stakeholder reporting and trend analysis. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Google Search Console API](openapi/google-search-console-api-openapi.yml)

### JSON Schema

- [Google Search Console Query Schema](json-schema/google-search-console-query-schema.json)
- [Search Analytics Query Request](json-schema/google-search-console-search-analytics-query-request-schema.json)
- [Search Analytics Query Response](json-schema/google-search-console-search-analytics-query-response-schema.json)
- [Sites List Response](json-schema/google-search-console-sites-list-response-schema.json)
- [Inspect URL Index Request](json-schema/google-search-console-inspect-url-index-request-schema.json)
- [Inspect URL Index Response](json-schema/google-search-console-inspect-url-index-response-schema.json)

### JSON-LD

- [Google Search Console Context](json-ld/google-search-console-context.jsonld)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Search Console](capabilities/shared/search-console.yaml) -- 10 operations for search analytics, sitemaps, URL inspection, and site management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [SEO Management](capabilities/seo-management.yaml) | Search Console | 10 | SEO Specialist |

## Rules

- [Google Search Console Spectral Rules](rules/google-search-console-spectral-rules.yml) -- 7 rules enforcing Google Search Console API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
