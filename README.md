# Insurance Council of Australia (insurance-council-australia)

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
