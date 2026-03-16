# GET /users/{id} — Single User API

## API
- **Method:** `GET`
- **Base URL:** `https://reqres.in`
- **Endpoint:** `/api/users/{id}`

## Objective
Verify that the Single User API returns correct user details for existing user IDs and handles non-existing user IDs properly.

---

## Test Cases

### TC-SU-001 - Single User - valid existing user ID

**Description**  
Verify that the API returns a single user successfully for an existing user ID.

**Request**
- Method: `GET`
- Endpoint: `/api/users/2`
- Path Params: `id=2`
- Request Body: Not applicable

**Expected Result**
- Status code is `200`
- Response contains `data`
- Response contains `support`
- `data` is an object
- `data` contains `id`
- `data` contains `email`
- `data` contains `first_name`
- `data` contains `last_name`
- `data` contains `avatar`
- `data.id` equals `2`
- Response time is under `1000ms`

---

### TC-SU-002 - Single User - another valid user ID

**Description**  
Verify that the API returns a single user successfully for another valid user ID.

**Request**
- Method: `GET`
- Endpoint: `/api/users/3`
- Path Params: `id=3`
- Request Body: Not applicable

**Expected Result**
- Status code is `200`
- Response contains `data`
- Response contains `support`
- `data` is an object
- `data` contains `id`
- `data` contains `email`
- `data` contains `first_name`
- `data` contains `last_name`
- `data` contains `avatar`
- `data.id` equals `3`
- Response time is under `1000ms`

---

### TC-SU-003 - Single User - non-existing user ID

**Description**  
Verify that the API returns the correct not found response for a non-existing user ID.

**Request**
- Method: `GET`
- Endpoint: `/api/users/23`
- Path Params: `id=23`
- Request Body: Not applicable

**Expected Result**
- Status code is `404`
- Response body is empty or minimal
- Response time is under `1000ms`
