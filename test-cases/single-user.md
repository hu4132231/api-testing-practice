# GET /users/{id} — Single User API

## Test Objective
Verify that the Single User API returns correct user detail data for a valid user ID, handles non-existent users properly, and maintains a stable response structure for frontend user detail scenarios.

---

## Endpoint
Base URL: https://reqres.in/api  
Endpoint: GET /users/{id}

---

## Test Scope
- HTTP response status and format
- Single user data structure and required fields validation
- Handling of non-existent users (404)
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

### TC-SU-001: Successful retrieval of a single user

**Description**  
Verify that the API returns user detail data for a valid user ID.

**Request**
- GET `/users/2`

**Expected Results**
- Status code is `200`
- Response format is JSON
- `data` field exists and is an object
- `support` field exists
- `data` contains:
  - `id` (number, equals `2`)
  - `email` (string, contains "@")
  - `first_name` (string)
  - `last_name` (string)
  - `avatar` (string, valid URL)
- Response time is under 800ms

---

### TC-SU-002: Request with non-existent user ID (Not Found)

**Description**  
Verify API behavior when the requested user ID does not exist.

**Request**
- GET `/users/23`

**Expected Results**
- Status code is `404`
- Response body is empty object `{}` (or no `data` field)
- No server error (5xx) occurs
- Response time is under 800ms

**Notes**
- This test focuses on correct HTTP status handling and frontend-safe behavior for missing resources.

---

### TC-SU-003: Request with invalid user ID format

**Description**  
Verify API stability when the user ID format is invalid.

**Request**
- GET `/users/abc`

**Expected Results**
- No server error (5xx) occurs
- Response is predictable and stable (either `404` or a valid JSON response)
- Response time is under 800ms

**Notes**
- This case avoids assuming strict validation rules and focuses on service stability and contract consistency.

---

## Postman Assertions Mapping

### TC-SU-001
- Status code is 200
- Response is JSON
- `data` exists and is an object
- `data.id === 2`
- Required user fields validation
- Response time < 800ms

### TC-SU-002
- Status code is 404
- Response is JSON (if applicable)
- Response body is empty object `{}` (or `data` not present)
- No server error (5xx)
- Response time < 800ms

### TC-SU-003
- No server error (5xx)
- Response is stable/predictable (404 or valid JSON)
- Response time < 800ms

---

## Notes
- This API is commonly used for frontend user detail rendering.
- Test cases focus on API contract stability and frontend safety rather than backend business logic.
