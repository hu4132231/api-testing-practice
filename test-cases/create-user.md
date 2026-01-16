🧪 Create User API Test Cases

Endpoint: POST /users
API: Reqres Public API

📌 API Description

Create a new user with provided name and job information.
This API simulates user creation and returns a generated id and createdAt timestamp.

📥 Request Specification

Method: POST

Endpoint: /users

Headers:

Content-Type: application/json

Request Body (Example)
{
  "name": "John",
  "job": "QA Engineer"
}

📤 Expected Response (Success)

Status Code: 201 Created

Response Body:

{
  "name": "John",
  "job": "QA Engineer",
  "id": "123",
  "createdAt": "2026-01-15T08:00:00.000Z"
}

✅ Test Cases
TC-CU-001 — Create user successfully (valid request)

Request

name: valid string

job: valid string

Expected Result

Status code is 201

Response format is JSON

Response contains:

name (string)

job (string)

id (string, auto-generated)

createdAt (ISO 8601 timestamp)

Response time is within acceptable range

Notes

id and createdAt are system-generated and should not be fixed values

TC-CU-002 — Create user with missing optional field (job)

Request

{
  "name": "John"
}


Expected Result

Status code is 201

API does not return server error (5xx)

Response body is stable and predictable

No unexpected fields are returned

QA Focus

Verify backend tolerance to partial input

Ensure frontend safety for optional fields

TC-CU-003 — Create user with empty request body

Request

{}


Expected Result

Status code is predictable (201 or 400, based on API behavior)

No server error (5xx)

Response structure is stable

API does not crash

QA Focus

Input validation handling

API contract stability

TC-CU-004 — Create user with invalid data types

Request

{
  "name": 123,
  "job": true
}


Expected Result

Status code is predictable

No server error (5xx)

API response is stable

Invalid data does not cause system failure

QA Focus

Defensive testing

Backend robustness

TC-CU-005 — Verify auto-generated fields behavior

Steps

Send the same valid request multiple times

Compare responses

Expected Result

Each response has a unique id

createdAt reflects request time

API does not reuse identifiers

QA Focus

Data uniqueness

Backend consistency

🧠 QA Notes / Testing Mindset

This API does not persist data, but contract validation is still critical

Focus is on:

Response stability

Predictable status codes

Frontend-safe behavior

Avoid asserting exact values for:

id

createdAt

🧰 Tools Used

Postman — request execution & test scripts

JavaScript assertions — response validation

GitHub — test case documentation
