# Insurance Council of Australia (insurance-council-australia)

The Insurance Council of Australia (ICA) is the representative body for Australia's general insurance industry, whose members write approximately 90% of total premium income for private sector general insurers and reinsurers, spanning home and contents, motor, travel, liability, professional indemnity, commercial property and directors and officers lines. The ICA administers the General Insurance Code of Practice, issues catastrophe and significant event declarations, operates the member Data Hub that reports claim counts, incurred losses and closed rates for declared events, and advocates on resilience, climate risk, building standards and insurance affordability. It is a market body rather than a carrier — it sells no policies and exposes no quote, bind, issue or FNOL API. Its API posture is partner-gated with no public developer program: developer, developers, docs and api subdomains do not resolve, and /developers/, /developer/, /partners/ and /integrations/ all return 404. The only integration surface is the member portal at memberportal.insurancecouncil.com.au, an Azure AD B2C (OpenID Connect authorization code) login wall for member insurers. Catastrophe and resilience data is published as PDF reports and a downloadable XLSX master file rather than through an API, and no ACORD, AL3 or NGDS reference appears anywhere on the site — Australia's insurance data seam is the Consumer Data Right, which was designated for general insurance and then deferred.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/insurance-council-australia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/insurance-council-australia/refs/heads/main/apis.yml)

## Tags

- Insurance
- Australia
- General Insurance
- Industry Association
- Property and Casualty
- Claims
- Catastrophe
- Risk Data
- Code of Practice

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

### Insurance Council of Australia WordPress REST API

insurancecouncil.com.au runs on WordPress and leaves the standard WordPress REST API reachable anonymously at `/wp-json/`, returning JSON for pages, media (the PDF publication corpus of media releases, submissions and reports), categories, tags and site search. This is incidental CMS infrastructure rather than an ICA API product — the ICA publishes no documentation for it, `/wp/v2/posts` returns an empty array, `/wp/v2/users` returns 401, and the insurer, resource and insurance-type custom post types behind Find an Insurer are not registered with the REST API. It carries no insurance data model and no quote, bind, issue or FNOL operations.

- **Human URL:** [https://developer.wordpress.org/rest-api/](https://developer.wordpress.org/rest-api/)
- **Base URL:** `https://insurancecouncil.com.au/wp-json/wp/v2`

#### Tags

- Content
- WordPress
- REST
- JSON

#### Properties

- [Documentation](https://developer.wordpress.org/rest-api/)
- [API Reference](https://developer.wordpress.org/rest-api/reference/)
- [Discovery](https://insurancecouncil.com.au/wp-json/)

### Insurance Council of Australia News RSS Feed

The ICA publishes its news, media releases, catastrophe declarations and resource updates as a standard RSS 2.0 feed at `/feed/`, served as `application/rss+xml`. This is the only first-party machine-readable syndication surface the organisation advertises, and it is read-only, unauthenticated and undocumented beyond the WordPress default.

- **Human URL:** [https://insurancecouncil.com.au/news-hub/](https://insurancecouncil.com.au/news-hub/)
- **Base URL:** `https://insurancecouncil.com.au`

#### Tags

- Feed
- News
- RSS
- Syndication

#### Properties

- [Documentation](https://insurancecouncil.com.au/news-hub/news-resources/)
- [RSS Feed](https://insurancecouncil.com.au/feed/)

## API Posture

Reviewed 2026-07-25. See [review.yml](review.yml) for the full probe log.

- **Developer portal:** none. No `developer.`, `developers.`, `docs.`, `api.`, `apis.`, `data.` or `datahub.` subdomain resolves; `/developers/`, `/developer/`, `/partners/` and `/integrations/` all return 404. `/api/` returns 200 but redirects to `/insurer/apia/`, the member profile for the insurer brand **Apia** — a homonym, not an API.
- **Gated:** yes. The only integration surface is [memberportal.insurancecouncil.com.au](https://memberportal.insurancecouncil.com.au/), an Azure AD B2C login wall for member insurers.
- **OpenAPI harvested:** none. Zero specifications exist, so no `openapi/` directory was created.
- **ACORD posture:** no ACORD reference found. Site search for ACORD, AL3 and NGDS all returned empty. Australia's data seam is the Consumer Data Right, designated for general insurance and then deferred.
- **Quote / bind / issue / FNOL:** none exposed. ICA is a market body, not a carrier.
- **Auth model:** none for the public read surfaces; OAuth2 / OpenID Connect authorization code via Azure AD B2C for the member portal (issuer `https://icab2cprod.b2clogin.com/tfp/04c7fa07-b168-495f-9dcc-bcfceb1a274e/b2c_1_signin/v2.0/`, only the `openid` scope advertised).
- **Webhooks / AsyncAPI:** none. There is no machine-readable catastrophe-declaration event feed.
- **GraphQL / gRPC / Postman:** none found.
- **MCP:** a WordPress MCP adapter route exists at `/wp-json/mcp/mcp-adapter-default-server` with a `wp-abilities/v1` namespace, but anonymous JSON-RPC `initialize` returns 401 `rest_forbidden` — present on the estate, not publicly usable.

## Published Data and Standards

As a market body, ICA's real corpus is documents and datasets rather than APIs.

- [Data hub](https://insurancecouncil.com.au/industry-members/data-hub/) — HTML dashboard of per-event claim counts, incurred losses, outstanding amounts and closed rates for declared catastrophes and significant events.
- [ICA Historical Normalised Catastrophe Master (June 2026)](https://insurancecouncil.com.au/wp-content/uploads/2026/07/ICA-Historical-Normalised-Catastrophe-Master-Updated-2026_06.xlsx) — bulk XLSX of normalised Australian natural-hazard catastrophe losses; ICA's records run back to 1967.
- [Current catastrophes](https://insurancecouncil.com.au/news-hub/current-catastrophes/) — catastrophe and significant event declarations.
- [General Insurance Code of Practice](https://insurancecouncil.com.au/code-of-practice/) — the rulebook ICA administers, plus code subscribers, past codes and submissions.
- [ICA Reports](https://insurancecouncil.com.au/ica-reports/) — Insurance Catastrophe Resilience Report, Climate Change Impact Series and related PDFs.
- [Find an Insurer](https://insurancecouncil.com.au/find-an-insurer/) — public directory of general insurers and the product categories they offer, served by `wp-admin/admin-ajax.php` rather than a documented query API.

## Links

- [Website](https://insurancecouncil.com.au/)
- [Our Role](https://insurancecouncil.com.au/about-us/our-role/)
- [Member Portal](https://memberportal.insurancecouncil.com.au/) (login required)
- [News hub](https://insurancecouncil.com.au/news-hub/)
- [LinkedIn](https://www.linkedin.com/company/insurance-council-of-australia/)
- [X](https://twitter.com/icaus)
- [YouTube](https://www.youtube.com/user/insurancecouncil)
- [Facebook](https://www.facebook.com/InsuranceCouncilofAustralia)
