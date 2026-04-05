# AGENTS Contract (Laravel)

## Scope

- Keep changes within requested modules.
- Do not refactor unrelated files.

## Coding Rules

- Follow PSR-12 style.
- Prefer Laravel conventions (Controller, FormRequest, Service, Resource).
- Add tests for behavior changes.

## Safety Rules

- Never run destructive commands without explicit approval.
- Do not edit `.env` values directly in commits.
- Avoid schema-breaking migration changes unless requested.

## Required Workflow

1. Read `docs/` context files first.
2. Create a small plan using `plans/TASK_TEMPLATE.md`.
3. Implement minimal change set.
4. Run quality checks and tests.
5. Provide change summary with risk notes.

## Done Criteria

- Relevant tests pass.
- CI checks pass.
- Behavior and API contract are updated in docs when needed.
