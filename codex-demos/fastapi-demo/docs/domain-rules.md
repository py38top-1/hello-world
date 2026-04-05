# Domain Rules (FastAPI Demo)

## General

- Resource identity must remain immutable.
- State transitions must be explicit and validated.

## Validation

- Input constraints must be enforced by Pydantic schemas.
- Critical domain rules must be covered by tests.

## Observability

- Important state changes should be logged with traceable context.
