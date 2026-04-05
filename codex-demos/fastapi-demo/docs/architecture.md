# Architecture (FastAPI Demo)

## Layers

- API layer: `routers/` and request/response schemas.
- Domain layer: services containing business decisions.
- Data layer: repository/ORM access.

## Design Intent

- Keep routing functions focused on I/O and orchestration.
- Keep business rules isolated in testable services.

## Change Policy

- New endpoint requires router, schema, service, and tests.
