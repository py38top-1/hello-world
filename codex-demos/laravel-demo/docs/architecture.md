# Architecture (Laravel Demo)

## Layers

- HTTP layer: routes, controllers, requests, resources.
- Domain layer: services and business logic.
- Data layer: models, repositories, migrations.

## Design Intent

- Keep controllers thin.
- Put business decisions in services.
- Keep validation rules in `FormRequest` classes.

## Change Policy

- New endpoint requires request validation, service method, and tests.
- Schema changes require migration and rollback note.
