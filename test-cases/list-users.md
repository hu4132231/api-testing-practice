# GET /users?page=2 — List Users API

## Test Objective
Verify that the List Users API returns a valid list of users with the correct data structure, data types, and acceptable performance for frontend user listing.

## Endpoint
GET https://reqres.in/api/users?page=2

## Test Scope
- Response status and format
- User list data structure and required fields
- Basic data validation
- API response performance

## Out of Scope
- Authentication / authorization
- Data persistence
- Backend data source validation

## Preconditions
- API base URL is reachable
- No authentication is required

---

## Positive Test Cases

### TC-LU-001: Successful retrieval of user list

**Steps**
1. Send a GET request to `/users?page=2`

**Expected Results**
- HTTP status code is `200`
- Response format is JSON
- `data` field exists and is a non-empty array
- Each user object contains the following fields:
  - `id` (number)
  - `email` (string, contains "@")
  - `first_name` (string)
  - `last_name` (string)
  - `avatar` (string, valid URL)
- Response time is less
