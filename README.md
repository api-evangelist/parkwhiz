# ParkWhiz (parkwhiz)

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

ParkWhiz is a parking reservation and mobility platform - with the BestParking discovery brand - that lets drivers search, price, reserve, and pay for parking at facilities, venues, and events across North America. Its consumer apps and website are backed by a documented v4 REST API covering location and quote search, bookings, parking passes, venues and events, monthly parking, vehicles, payment methods, and accounts.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/parkwhiz/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/parkwhiz/refs/heads/main/apis.yml)

## Access Model (Partner-Gated)

The ParkWhiz v4 API is **publicly documented but partner-gated**. The full reference lives at [developer.parkwhiz.com/v4](https://developer.parkwhiz.com/v4/) (mirrored at [developer.arrive.com/v4](https://developer.arrive.com/v4/)), but you cannot self-serve credentials. OAuth `client_id`, `client_secret`, and `redirect_uri` are issued to **approved integration partners** on request via **dev@parkwhiz.com**.

- **Production:** `https://api.parkwhiz.com/v4` (also `https://api.arrive.com/v4`)
- **Sandbox:** `https://api-sandbox.parkwhiz.com/v4`
- **Auth:** OAuth 2.0 bearer tokens (client_credentials, password, authorization_code, refresh_token, public/mobile grants)
- **Scopes:** `public` (default), `partner`, `mobile`, `internal`, `data` (assigned per partner; some partners receive only `public` and `partner`)

## Corporate History (Arrive / Flash / EasyPark / Flowbird)

The corporate lineage around this brand is easy to conflate, so it is documented explicitly here:

- **ParkWhiz** was founded in 2006 (Chicago) and, together with the **BestParking** discovery product, was consolidated under the **Arrive / Arrive Mobility** brand.
- In **January 2021**, **Arrive Mobility** - including the **ParkWhiz** and **BestParking** consumer brands - **merged into FlashParking (Flash)**.
- Separately, **EasyPark Group** acquired the **rights to the "Arrive" name** from Flash and rebranded EasyPark to **Arrive** (2025). EasyPark Group also **closed its acquisition of Flowbird Group in January 2025**.

Note: a common assumption that "Flowbird acquired ParkWhiz/Arrive in 2024" is **not** supported by the record. The **ParkWhiz product and its v4 API line up under Flash**, while the **"Arrive" consumer name is now used by EasyPark Group** (which owns Flowbird). The developer portal continues to serve the same ParkWhiz v4 API under both the `parkwhiz.com` and `arrive.com` developer domains.

## Tags

- Parking
- Mobility
- Reservations
- Bookings
- Transportation
- Location
- Events

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### ParkWhiz Quotes & Locations API

Search bookable parking availability and pricing (quotes) for an area, destination, venue, or event, and retrieve parking location (facility) details and reviews. Returns both bookable ParkWhiz inventory and non-bookable BestParking locations.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

### ParkWhiz Bookings API

Preview, create, retrieve, list, extend, cancel, and share bookings from a selected quote; retrieve the parking pass and scan/QR code; attach a vehicle for validation. Requires a user-authorized OAuth token.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

### ParkWhiz Monthly Parking API

List and retrieve recurring monthly parking bookings - the subscription-style counterpart to transient (hourly / daily / event) bookings.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

### ParkWhiz Venues & Events API

Search venues (stadiums, arenas, airports, theaters) and events, and retrieve events scheduled at a venue, to find and price event parking near a destination and time.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

### ParkWhiz Accounts & Vehicles API

Create and manage user accounts and profiles, saved vehicles, payment methods, frequent locations, and recommended bookings, plus account recovery, password reset, and phone verification.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

### ParkWhiz Tickets API

Preview, create, update, pay, and close parking tickets (drive-up / on-demand transactions and violations), and associate a vehicle with a ticket.

- **Human URL:** [https://developer.parkwhiz.com/v4/](https://developer.parkwhiz.com/v4/)
- **Base URL:** `https://api.parkwhiz.com/v4`

## Artifacts

- [OpenAPI](openapi/parkwhiz-openapi.yml) - v4 REST surface authored by API Evangelist from the public developer docs
- [Postman Collection](collections/parkwhiz.postman_collection.json)
- [Open Collection](collections/parkwhiz.opencollection.json)
- [Plans / Pricing](plans/parkwhiz-plans-pricing.yml) - partner / transaction-based economics
- [Rate Limits](rate-limits/parkwhiz-rate-limits.yml)
- [FinOps](finops/parkwhiz-finops.yml)

## Common Properties

- [Website](https://www.parkwhiz.com)
- [LinkedIn](https://www.linkedin.com/company/parkwhiz)
- [Documentation](https://developer.parkwhiz.com/)
- [Developer Portal](https://developer.parkwhiz.com/)
- [Getting Started](https://developer.parkwhiz.com/getting_started/)
- [Changelog](https://developer.parkwhiz.com/changes/)
- [SDK](https://developer.parkwhiz.com/libraries/)
- [Plans](plans/parkwhiz-plans-pricing.yml)
- [Rate Limits](rate-limits/parkwhiz-rate-limits.yml)
- [Fin Ops](finops/parkwhiz-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
