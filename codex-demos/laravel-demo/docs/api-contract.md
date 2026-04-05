# API Contract (Laravel Demo)

## Response Envelope

- Success: `{ "data": ..., "meta": ... }`
- Error: `{ "error": { "code": "...", "message": "..." } }`

## HTTP Rules

- Use correct status codes (`200`, `201`, `400`, `404`, `422`, `500`).
- Validation errors should be deterministic and testable.

## Versioning

- Prefer `/api/v1` route group for new APIs.
