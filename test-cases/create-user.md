# POST /users — Create User API

## Test Objective
Verify that the Create User API correctly handles user creation requests, returns a stable and predictable response structure, and safely handles invalid or incomplete input without causing server errors.

---

## Endpoint
Base URL: https://reqres.in/api  
Endpoint: POST /users

---

## Test Scope
- HTTP response status and format
- Request body handling and validation
- Response contract validation
- Auto-generated fields behavior (`id`, `createdAt`)
- API response performance

---

## Out of Scope
- Authentication / authorization
- Backend data persistence
- Database or external service validation

---

## Preconditions
- API base URL is reachable
- No authentication is required

---

## Test Cases

### TC-CU-001: Create user successfully with valid request

**Description**  
Verify that the API successfully creates a user when valid input data is provided.

**Request**
```json
{
  "name": "John",
  "job": "QA Engineer"
}
```

**Expected Results**
- Status code is 201
- Response format is JSON
- Response body contains:
  - name (string)
  - job (string)
  - id (string, auto-generated)
  - createdAt (ISO 8601 timestamp)
- Auto-generated fields are present and non-empty
- Response time is under 800ms

**Notes**
- Do not assert exact values for id and createdAt

---

### TC-CU-002: Create user with missing optional field (job)

**Description**
Verify API behavior when an optional field is omitted from the request body.

**Request**
```json
{
  "name": "John"
}
```

**Expected Results**
- Status code is 201
- No server error (5xx) occurs
- Response structure is stable and predictable
- No unexpected fields are returned
- Response time is under 800ms

---

### TC-CU-003: Create user with empty request body

**Description**
Verify API stability when an empty request body is sent.

**Request**
```json
{}
```

**Expected Results**
- Status code is predictable (201 or 400, based on API behavior)
- No server error (5xx) occurs
- Response structure remains stable
- API does not crash
- Response time is under 800ms

---

### TC-CU-004: Create user with invalid data types

**Description**
Verify API robustness when request body contains invalid data types.

**Request**
```json
{
  "name": 123,
  "job": true
}
```
**Expected Results**
- Status code is predictable
- No server error (5xx) occurs
- API response remains stable
- Invalid input does not cause system failure
- Response time is under 800ms

---

### TC-CU-005: Verify auto-generated fields behavior

**Description**
Verify that auto-generated fields are unique and correctly generated for each request.

**Steps**
- Send the same valid request multiple times
- Compare responses

**Expected Results**
- Each response contains a unique id
- createdAt reflects request time
- API does not reuse identifiers
- Response time is under 800ms

---

## Postman Assertions Mapping

### TC-CU-001
- Status code is 201
- Response is JSON
- Required response fields validation
- id exists and is non-empty
- createdAt matches ISO 8601 format
- Response time < 800ms

### TC-CU-002
- Status code is 201
- No server error (5xx)
- Response structure is stable
- Response time < 800ms

### #TC-CU-003
- No server error (5xx)
- Status code is predictable
- Response structure is stable
- Response time < 800ms

### TC-CU-004
- No server error (5xx)
- Response is stable
- Response time < 800ms

### TC-CU-005
- Auto-generated id values are unique
- createdAt values differ between requests
- Response time < 800ms

---

## Notes
- This API does not persist data.
- Test cases focus on API contract stability, defensive testing, and frontend-safe behavior.
