# PetExec (petexec)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

PetExec is cloud-based business management software for dog daycares, boarding facilities, groomers, and trainers - scheduling, an owner portal, payments, and reporting. PetExec publishes a real, documented OAuth2 (password grant) REST API for existing customers and their developers, with a public GitHub examples repository covering owners, pets, boarding, daycare, grooming, scheduled services, vaccinations, billing, and reports. Access requires an active PetExec account - client credentials are self-issued from Company Preferences > Misc. Settings > Maintain API Applications, then exchanged for a Bearer token via a scoped password grant. PetExec was acquired by Togetherwork in November 2024 and joined the Gingr / Revelation Pets pet-care product group; PetExec is no longer accepting new customers and is being migrated toward Gingr, but the documented API remains live for existing PetExec accounts as of this review.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/petexec/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/petexec/refs/heads/main/apis.yml)

## Access model

This is **not** a self-serve public API with open signup. It is a real, technically documented REST API scoped to existing PetExec customers:

- **Base URL:** `https://secure.petexec.net/api` (a `https://beta.petexec.net/api` environment appears in some of PetExec's own examples for the same paths)
- **Auth:** OAuth2 Resource Owner Password Credentials (password) grant - `POST /token` with an `Authorization: Basic base64(client_id:client_secret)` header, plus `grant_type=password`, `username`, `password`, and a space-separated `scope` list (e.g. `owner_read owner_update`)
- **Credentials:** Self-issued inside the PetExec console under **Company Preferences > Misc. Settings > Maintain API Applications**
- **Interactive reference:** [https://secure.petexec.net/api/apidoc/index.html](https://secure.petexec.net/api/apidoc/index.html) (a JavaScript-rendered apidoc.js site with no machine-readable export)
- **Primary technical source:** PetExec's own public GitHub examples repository, [PetExec/API-Examples](https://github.com/PetExec/API-Examples) (PHP-Guzzle and JavaScript), which is what every endpoint in this entry's `openapi/petexec-openapi.yml` was transcribed from

## Corporate context

PetExec was acquired by [Togetherwork](https://www.togetherwork.com/) in November 2024 and joined the Gingr / Revelation Pets pet-care product group. PetExec is **no longer accepting new customers** and Togetherwork has been actively migrating existing accounts to Gingr (migration webinars; some customers report an added ~1% payment gateway fee). The API documented here is published and referenced from petexec.net as of this review, but its long-term availability should be treated as uncertain given the ongoing Gingr migration.

## Tags

- Pet Care
- Boarding
- Daycare
- Grooming
- Training
- Business Management
- Pet Business Software

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

### PetExec Owners API

List and retrieve owner (pet parent) account records and run paginated keyword search across the owner database. Requires the `owner_read` OAuth2 scope.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Owner](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Owner)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Pets API

Retrieve or delete an individual pet profile, list configured pet types and the breeds available for a type, search pets by keyword, and look up the facility's vet directory attached to pet records.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Pet](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Pet)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Reservations API

Retrieve or cancel a specific future boarding, daycare, grooming, or scheduled-service reservation, and look up an owner's active boarding packages.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Boarding](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Boarding)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Calendar API

Pull company-wide or single-owner boarding, daycare, grooming, and scheduled-service reservations for a given date range, for external calendar and scheduling integrations.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Calender](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Calender)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Services API

List the boarding, daycare, and grooming service catalog, the roster of company groomers, and scheduled-service types plus the individual services within each type.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Scheduled%20Services](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Scheduled%20Services)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Vaccinations API

Retrieve or delete an individual vaccination (shot) record and list the shots configured for a given pet type, supporting vaccine-compliance integrations.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Vaccinations](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Vaccinations)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Billing & Reports API

Pull an owner's purchase history and stored credit cards, and generate billing and statistics reports for a date range, optionally broken down by payment type or service.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Reports](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Reports)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### PetExec Company & Account API

Read company-level configuration - locations, employees, lead sources ("how found"), and named preference values - plus the authenticated user's own profile and owner-portal menu.

- **Human URL:** [https://github.com/PetExec/API-Examples/tree/master/JavaScript/Company](https://github.com/PetExec/API-Examples/tree/master/JavaScript/Company)
- **Base URL:** `https://secure.petexec.net/api`

#### Properties

- [Documentation](https://www.petexec.net/features/api-for-developers)
- [API Reference](https://secure.petexec.net/api/apidoc/index.html)
- [OpenAPI](openapi/petexec-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/petexec.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/petexec.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/PetExec)
- [Website](https://www.petexec.net/)
- [Documentation](https://docs2.petexec.net/)
- [Plans](plans/petexec-plans-pricing.yml)
- [Rate Limits](rate-limits/petexec-rate-limits.yml)
- [Fin Ops](finops/petexec-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
