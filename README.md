# PetExec (petexec)

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
