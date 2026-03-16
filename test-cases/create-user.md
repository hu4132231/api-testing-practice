# POST /users — Create User API

## API
- **Method:** `POST`
- **Base URL:** `https://reqres.in`
- **Endpoint:** `/api/users`

## Objective
Verify that the Create User API returns the expected response for valid and incomplete request bodies based on the mock behavior of Reqres.

---

## Test Cases

### TC-CU-001 - Create User - valid name and job

**Description**  
Verify that the API creates a user successfully when both `name` and `job` are provided.

**Request**
- Method: `POST`
- Endpoint: `/api/users`
- Request Body:
```json
{
  "name": "Jill",
  "job": "QA engineer"
}

```

**Expected Result**

- Status code is 201
- Response contains name
- Response contains job
- Response contains id
- Response contains createdAt
- Returned name matches the request body
- Returned job matches the request body
- Response time is under 1000ms

---

### TC-CU-002 - Create User - missing job

**Description**
Verify that the API still returns a success response when job is missing, based on the mock behavior of Reqres.

**Request**
- Method: `POST`
- Endpoint: `/api/users`
- Request Body:
```json
{
  "name": "Jill",
}
```

---

**Expected Result***

- Status code is 201
- Response contains name
- Response contains id
- Response contains createdAt
- Returned name matches the request body
- job is not returned in the response
- Response time is under 1000ms

---

## TC-CU-003 - Create User - empty request body

Description
Verify how the API behaves when an empty request body is sent.

Request

Method: POST

Endpoint: /api/users

Request Body:

{}

Expected Result

Status code is 201

Response contains id

Response contains createdAt

name is not returned in the response

job is not returned in the response

Response time is under 1000ms
