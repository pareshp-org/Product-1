# UAT Runbook — Product-1 (User Identity & Profile Management)

## Feature
User registration, authentication and profile persistence

## Preconditions
- Service is configured with valid environment (`.env.local` or `.env.example`).
- Database migrations have been applied via `make migrate`.
- Required port is free and accessible.

## Steps
1. Start Product-1 service using `python app.py --serve --port 8081`
2. Execute GET /health to ensure database connection and user table are initialized
3. Register new user via POST /api/v1/users with username and profile metadata
4. Query GET /api/v1/users to assert newly created user profile is present

## Expected Results
- HTTP 200 OK returned for /health
- HTTP 201 Created returned with user ID and timestamp
- User record appears in user list with correct email and active status

---
*Author: QA & Primary Owner (MasterSpec Section 31.1, Section 33.1)*
*Verification Contract: `verification/contract.yaml`*
