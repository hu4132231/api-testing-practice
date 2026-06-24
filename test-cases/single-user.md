# GET /users/{id} — Single User API

## API

* **Method:** `GET`
* **Base URL:** `https://reqres.in`
* **Endpoint:** `/api/users/{id}`

## Objective

Verify that the Single User API returns correct user details for existing user IDs and handles non-existing user IDs properly.

This document focuses on path parameter validation, status code verification, response structure checking, required user field validation, not found response handling, and basic response time validation.

---

## Test Cases

### TC-SU-001 - Single User - valid existing user ID

**Test Type**
Positive test case

**Description**
Verify that the API returns a single user successfully when an existing user ID is provided.

**Request**

* Method: `GET`
* Endpoint: `/api/users/2`
* Path Params: `id=2`
* Request Body: Not applicable

**Expected Result**

* Status code should be `200`
* Response should contain `data`
* Response should contain `support`
* `data` should be an object
* `data` should contain `id`
* `data` should contain `email`
* `data` should contain `first_name`
* `data` should contain `last_name`
* `data` should contain `avatar`
* `data.id` should equal `2`
* Response time should be under `1000ms`

---

### TC-SU-002 - Single User - another valid user ID

**Test Type**
Positive test case

**Description**
Verify that the API returns a single user successfully when another valid user ID is provided.

**Request**

* Method: `GET`
* Endpoint: `/api/users/3`
* Path Params: `id=3`
* Request Body: Not applicable

**Expected Result**

* Status code should be `200`
* Response should contain `data`
* Response should contain `support`
* `data` should be an object
* `data` should contain `id`
* `data` should contain `email`
* `data` should contain `first_name`
* `data` should contain `last_name`
* `data` should contain `avatar`
* `data.id` should equal `3`
* Response time should be under `1000ms`

---

### TC-SU-003 - Single User - non-existing user ID

**Test Type**
Negative test case / not found response check

**Description**
Verify that the API returns the correct not found response when a non-existing user ID is provided.

**Request**

* Method: `GET`
* Endpoint: `/api/users/23`
* Path Params: `id=23`
* Request Body: Not applicable

**Expected Result**

* Status code should be `404`
* Response body should be an empty object or should not contain user data
* Response should not contain `data`
* Response time should be under `1000ms`

---

## Notes

Reqres is a public mock API. The `/api/users/23` request is commonly used as a not found case in this API.

These test cases are designed to validate both successful user detail responses and not found response behavior when the path parameter does not match an existing user.
