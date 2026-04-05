# AGENTS Contract (FastAPI)

## Scope

- Modify only requested modules.
- Keep endpoints backward compatible unless explicitly approved.

## Coding Rules

- Use type hints for public interfaces.
- Keep routers thin; place business logic in services.
- Validate input with Pydantic models.
- Add tests for endpoint and domain behavior changes.

## Safety Rules

- No destructive data operations without explicit approval.
- Avoid secret or token hardcoding.

## Required Workflow

1. Read `docs/` context files.
2. Create a short execution plan from `plans/TASK_TEMPLATE.md`.
3. Implement minimal changes.
4. Run quality checks and tests.
5. Provide risk and rollback notes.

## Done Criteria

- Tests pass.
- API contract remains consistent or is documented.
- CI checks pass.
