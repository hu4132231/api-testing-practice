# GET /users — List Users API

## Test Objective
Verify that the List Users API returns user list data with correct structure, valid field types, and acceptable performance for frontend user listing scenarios.

---

## Endpoint
GET https://reqres.in/api/users

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
- API falls back to default behavior
- No server error (5xx) occurs

**Notes**
- This scenario is validated by modifying the query parameter in an exis
