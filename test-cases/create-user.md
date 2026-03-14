# POST /users — Create User API

## API
- **Method:** POST
- **Endpoint:** `/api/users`

## Objective
Verify that the Create User API returns expected response data for valid and incomplete request bodies.

## Test Cases

### TC-CU-001 - Create User - valid name and job

**Description**  
Verify that the API can create a user successfully with valid `name` and `job`.

**Request Body**
```json
{
  "name": "morpheus",
  "job": "leader"
}
```
Expected Result

Status code is 201

Response contains name

Response contains job

Response contains id

Response contains createdAt

TC-CU-002 - Create User - missing job

Description
Verify the API behavior when job is missing in the request body.

Request Body

{
  "name": "morpheus"
}

Expected Result

Status code is 201

Response contains name

Response contains id

Response contains createdAt

Response does not contain job

TC-CU-003 - Create User - empty body

Description
Verify the API behavior when the request body is empty.

Request Body

{}

Expected Result

Status code is 201

Response contains id

Response contains createdAt

Response does not contain name

Response does not contain job

Notes

This API is tested using Reqres demo service.

Negative test cases are based on actual observed API behavior.
