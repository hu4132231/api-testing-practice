# POST /users — Create User API

## API

* **Method:** `POST`
* **Base URL:** `https://reqres.in`
* **Endpoint:** `/api/users`

## Objective

Verify that the Create User API returns the expected response for valid and incomplete request bodies based on the mock behavior of the Reqres public API.

This document focuses on request body validation, response field checking, status code verification, and basic response time validation.

---

## Test Cases

### TC-CU-001 - Create User - valid name and job

**Test Type**
Positive test case

**Description**
Verify that the API returns a successful creation response when both `name` and `job` are provided.

**Request**

* Method: `POST`
* Endpoint: `/api/users`
* Request Body:

```json
{
  "name": "Jill",
  "job": "QA Engineer"
}
```

**Expected Result**

* Status code should be `201`
* Response should contain `name`
* Response should contain `job`
* Response should contain `id`
* Response should contain `createdAt`
* Returned `name` should match the request body
* Returned `job` should match the request body
* Response time should be under `1000ms`

---

### TC-CU-002 - Create User - missing job

**Test Type**
Incomplete request body / mock API behavior check

**Description**
Verify that the API still returns a success response when `job` is missing, based on the mock behavior of Reqres.

**Request**

* Method: `POST`
* Endpoint: `/api/users`
* Request Body:

```json
{
  "name": "Jill"
}
```

**Expected Result**

* Status code should be `201`
* Response should contain `name`
* Response should contain `id`
* Response should contain `createdAt`
* Returned `name` should match the request body
* Response should not contain `job`
* Response time should be under `1000ms`

---

### TC-CU-003 - Create User - empty request body

**Test Type**
Empty request body / mock API behavior check

**Description**
Verify how the API behaves when an empty request body is sent.

**Request**

* Method: `POST`
* Endpoint: `/api/users`
* Request Body:

```json
{}
```

**Expected Result**

* Status code should be `201`
* Response should contain `id`
* Response should contain `createdAt`
* Response should not contain `name`
* Response should not contain `job`
* Response time should be under `1000ms`

---

## Notes

Reqres is a public mock API. Some POST requests may return a successful response even when the request body is incomplete or empty.
In a real production system, missing required fields such as `name` or `job` may need to return a validation error instead.

These test cases are designed to document the actual behavior of the mock API and practice API response validation, not to define production-level business rules.
