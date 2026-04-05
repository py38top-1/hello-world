# API Contract (FastAPI Demo)

## Response Rules

- Success responses must have stable schema.
- Error responses should include machine-readable `code` and human `message`.

## HTTP Rules

- Return correct status codes.
- Avoid breaking changes in existing endpoint response fields.

## Versioning

- Prefer versioned prefix like `/api/v1` for public APIs.
