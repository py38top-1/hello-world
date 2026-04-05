# Domain Rules (Laravel Demo)

## General

- IDs are immutable once created.
- Soft delete should be preferred when data recovery matters.

## Validation

- Required fields must be validated server-side.
- Cross-field business rules must be tested in feature tests.

## Auditability

- Significant state changes should be loggable and traceable.
