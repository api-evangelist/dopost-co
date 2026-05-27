# dopost (dopost-co)

Social media scheduler API. Schedule and publish posts across Instagram, Facebook, TikTok, Pinterest, X (Twitter), and YouTube from a single REST API.

**APIs.yml:** [apis.yml](apis.yml) · **Review:** [review.yml](review.yml)

## Type
- **x-type:** company
- **submitted via:** [api-search/network#31](https://github.com/api-search/network/issues/31)

## APIs
- **dopost Social Media Scheduler API** — `https://dopost.co/api/v1/` — multi-network publishing API (Instagram, Facebook, TikTok, Pinterest, X, YouTube). [Docs](https://dopost.co/docs/api) · [Pricing](https://dopost.co/pricing)

## Authentication
API key sent via `x-api-key` header. Keys are issued from the dopost web app (Pro tier and above per marketing copy).

## Documented Endpoints
| Method | Path | Capability |
| --- | --- | --- |
| POST | `/api/v1/post/publish` | publish / schedule a post |
| GET | `/api/v1/post` | list posts (cursor-paginated, status filter) |
| GET | `/api/v1/post/{postId}` | get a post |
| PATCH | `/api/v1/post/{postId}` | reschedule a post |
| DELETE | `/api/v1/post/delete/{postId}` | delete a draft/scheduled post |
| GET | `/api/v1/social/accounts` | list connected accounts |
| GET | `/api/v1/social/limits/{platform}` | per-network posting limits |
| POST | `/api/v1/media` | initiate media upload (presigned URL flow) |
| GET | `/api/v1/media` | list media |
| DELETE | `/api/v1/media/{mediaId}` | delete media |

## Artifacts
- **OpenAPI 3.1:** [`openapi/dopost-openapi.yml`](openapi/dopost-openapi.yml) — hand-authored from the dopost docs (no upstream OpenAPI/Postman is published).
- **Capabilities:** [`capabilities/`](capabilities/) — posts, accounts, media, analytics (stub, `reconciled: false`).
- **JSON Schema:** [`json-schema/`](json-schema/) — Post, Account, MediaAsset.
- **JSON-LD context:** [`json-ld/dopost-co-context.jsonld`](json-ld/dopost-co-context.jsonld) — schema.org `SocialMediaPosting` alignment.
- **Examples:** [`examples/`](examples/) — schedule on Instagram, cross-network fan-out, fetch platform limits.
- **Spectral rules:** [`rules/dopost-co-rules.yml`](rules/dopost-co-rules.yml).
- **Vocabulary:** [`vocabulary/dopost-co-vocabulary.yml`](vocabulary/dopost-co-vocabulary.yml) — Network, Account, Post, Schedule, Media, Engagement, PlatformLimits.
- **Plans & pricing:** [`plans/dopost-co-plans-pricing.yml`](plans/dopost-co-plans-pricing.yml) — `reconciled: false` (pricing page is gated behind login for anonymous fetchers; headline EUR prices captured from marketing home page).
- **Rate limits:** [`rate-limits/dopost-co-rate-limits.yml`](rate-limits/dopost-co-rate-limits.yml) — `reconciled: false` (no public rate-limit policy; only content limits are documented).
- **FinOps (FOCUS 1.3):** [`finops/dopost-co-finops.yml`](finops/dopost-co-finops.yml) — subscription billing model, `reconciled: false`.

## Tags
Social Media, Scheduling, Publishing, Instagram, Facebook, TikTok, Pinterest, X Twitter, YouTube, Content Management, REST

## Notes
dopost's API reference at `/docs/api` is a JS-rendered Next.js page; no public downloadable OpenAPI document is available as of 2026-05-27. The OpenAPI in this repo was hand-authored from the per-endpoint docs pages and is partially reconciled — per-network publish-option schemas are intentionally open (`additionalProperties: true`) because dopost does not enumerate them field-by-field publicly. See [`review.yml`](review.yml) for the full gap list.

## Timestamps
- **Created:** 2026-05-27
- **Modified:** 2026-05-27

## Maintainers
- **Kin Lane** — kin@apievangelist.com
