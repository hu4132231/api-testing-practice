# GET /users — List Users API

## Base URL
`https://reqres.in/api`

## Objective
Verify that the List Users API returns user list data correctly for valid and invalid page query scenarios.

## Test Cases

### TC-LU-001 - List Users - valid page 2

**Request**
- GET `/users?page=2`

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `data`
- `data` is an array
- Response time is under 800ms

---

### TC-LU-002 - List Users - valid page 1

**Request**
- GET `/users?page=1`

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `data`
- `data` is an array
- Response time is under 800ms

---

### TC-LU-003 - List Users - invalid page

**Request**
- GET `/users?page=999`

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `data`
- `data` is an empty array
- No server error (5xx)

## Notes
- Tested with Reqres demo API
- Negative case is based on actual API behavior
