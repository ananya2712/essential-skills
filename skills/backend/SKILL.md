---
name: flask-postgres-backend
description: Use when planning, building, or reviewing Flask APIs, PostgreSQL data models, database migrations, or backend integration in this project.
---

# Backend Skill

Use this skill for backend work in this project. Read the root `AGENTS.md` first. It contains the approved stack and product constraints.

## Architecture

- Use Flask app factories and blueprints.
- Keep route handlers, business logic, and feature-specific database queries in separate modules.
- Use a modular monolith. Do not add a generic repository base class by default.
- Keep REST JSON endpoints under `/api/v1`.
- Validate request and response data with Pydantic schemas at the API boundary.
- Return consistent error responses. Keep validation at trust boundaries.

## API contract

Flask does not create an OpenAPI schema by default. Maintain `openapi.yaml` as the API contract. Keep it aligned with routes and Pydantic schemas. Generate a typed client with `openapi-typescript` and `openapi-fetch` when the contract changes.

Define resource names, request and response shapes, validation rules, and error responses. Add pagination or filters only when a collection needs them. Inspect callers before changing an endpoint. Update affected callers and the API contract in the same change.

During final verification, compare actual HTTP responses with `openapi.yaml` and the Pydantic schemas. Check status codes, response fields, null values, validation errors, and pagination when used. Exercise both successful and failed requests through the running API and the generated client. A generated type or a successful build does not prove that the runtime response matches the contract. Follow the test timing below.

## Data and persistence

- Use PostgreSQL, SQLAlchemy 2, and Alembic.
- Model the approved main records and their relationships.
- Add a field only when a requirement needs it. Add an index only when a query or constraint needs it.
- Do not add enrichment history, provider payload storage, or provenance tables by default.
- Use database constraints for important data rules. Add a migration for each schema change.
- Do not add queues, caches, microservices, or deployment services until an approved requirement needs them.

Define transaction boundaries around each logical write. Roll back failed writes. Use stable record identity and database uniqueness rules to prevent duplicates during retries or concurrent requests. Define how concurrent edits are detected or resolved when they can overwrite user work. Preserve saved values when a provider call fails or omits a field; apply explicit clearing only under an approved rule. Keep slow provider calls outside database write transactions where possible. For partial results, persist only validated data and the status needed by the approved recovery flow.

## Business rules

Keep scoring, ranking, eligibility, and other business rules in service modules. For the same inputs, rule version, and effective time, return the same result. Define tie-breaking, numeric precision, thresholds, and missing-data behavior when relevant. Pass the effective time explicitly for time-dependent decisions. Keep provider or generated advice separate from authoritative rules. Let it change a business result only when the approved requirements explicitly allow that behavior.

## Configuration and security

Load configuration from environment variables. Keep placeholder values in `.env.example`. Do not store secrets in source control. Do not add login or account features unless the user asks for them or the requirements need them.

Preserve validation and error handling when code moves. Handle failures so they do not cause data loss. Do not expose secrets or private data in responses or logs.

## External services

Call external providers from backend service modules. Set timeouts. Handle expected provider errors. Keep provider-specific behavior out of route handlers. Do not add request-history or provider-payload tables by default. Do not connect tests to live provider accounts.

Treat provider responses as untrusted input. Validate their shape and values before use, then map them to internal schemas. Distinguish a valid empty result from unavailable data, invalid data, and a failed request. Bound request duration and retry attempts. Retry only failures that can recover, and account for rate limits. Do not repeat a request with external side effects unless duplicate effects are prevented. Preserve the user's input and useful saved results on failure. Return a safe error and the supported next action. Keep credentials and raw sensitive payloads out of errors and logs.

## Tests and verification

Follow the test scope in `AGENTS.md`:

- Finish all approved functionality before writing or running automated application tests.
- Use pytest for API and database integration tests.
- Use the Playwright Python pytest plugin for browser end-to-end tests.
- Use a separate test database.
- Do not add unit or smoke tests unless the user changes this decision.
- Do not use test-driven development.

Check Docker Compose, API behavior, persistence after restart, and the relevant data flow during final verification. Report commands, observed results, and any check you could not run.
