# Auth API

## Purpose

Document the mock authentication API.

## Status

- Current State: Example API documentation.
- Implementation: Mock example.
- Auth Required: Login is public. Current-user lookup requires an authenticated session.

## Endpoint List

| Method | Endpoint | Purpose | Status |
|---|---|---|---|
| POST | `/api/auth/login` | Authenticate a user with email and password. | Example |
| GET | `/api/auth/me` | Return the current authenticated user. | Example |

## POST `/api/auth/login`

Create an authenticated session for a user.

### Request

- `email`: string
- `password`: string

### Response

- `user.id`
- `user.email`
- `session.active`

### Error Response

- `401`: invalid credentials
- `400`: missing email or password

### Auth

No existing session required.

### Validation

- Email is required.
- Password is required.

## GET `/api/auth/me`

Return the current authenticated user.

### Request

No request body.

### Response

- `user.id`
- `user.email`

### Error Response

- `401`: no active session

### Auth

Requires an active session.

### Validation

- Session must be present.

## Related Files

- `../frontend/login-page.md`

## Notes for Agent

- This is an example document, not a real implementation contract.
- Do not copy endpoint details into frontend docs. Link here instead.
