# GET /users — List Users API

## Test Objective
Verify that the List Users API returns user list data with correct structure, valid field types, and acceptable performance for frontend user listing scenarios.

---

## Endpoint
Base URL: https://reqres.in/api  
Endpoint: GET /users

---

## Test Scope
- HTTP response status and format
- User list data structure
- Required user fields and basic data validation
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

### TC-LU-001: Successful retrieval of user list

**Description**  
Verify that the API returns a non-empty list of users for a valid page number.

**Request**
- GET `/users?page=2`

**Expected Results**
- Status code is `200`
- Response format is JSON
- `data` field exists and is a non-empty array
- Each user object contains:
  - `id` (number)
  - `email` (string, contains "@")
  - `first_name` (string)
  - `last_name` (string)
  - `avatar` (string, valid URL)
- Response time is under 800ms

---

### TC-LU-002: Request with invalid page parameter

**Description**  
Verify API behavior when the page parameter is invalid.

**Request**
- GET `/users?page=invalid`

**Expected Results**
- Status code is `200`
- Response structure remains valid
- No server error (5xx) occurs

**Notes**
- A dedicated Postman request is created for this case to ensure repeatability and easier collection runs.

---

### TC-LU-003: Request with page parameter exceeding available pages

**Description**  
Verify API behavior when the requested page exceeds available data.

**Request**
- GET `/users?page=999`

**Expected Results**
- Status code is `200`
- `data` field exists and is an empty array
- Response structure remains valid
- Response time is under 800ms

---

## Postman Assertions Mapping

### TC-LU-001
- Status code is 200
- Response is JSON
- `data` exists and is an array
- `data.length > 0`
- Required user fields validation
- Response time < 800ms

 ### TC-LU-002
- Status code is 200
- Response is JSON
- `data` exists and is an array
- No server error (5xx)


### TC-LU-003
- Status code is 200
- Response is JSON
- `data` exists and is an array
- `data.length === 0`
- Response time < 800ms

---

## Notes
- This API is commonly used for frontend user list rendering.
- Test cases focus on API contract stability and frontend safety rather than backend business logic.
