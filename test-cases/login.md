# POST /login — Login API

## API

* **Method:** `POST`
* **Base URL:** `https://reqres.in`
* **Endpoint:** `/api/login`

## Objective

Verify that the Login API returns a token for valid credentials and returns appropriate error responses when required fields are missing.

This document focuses on request body validation, status code verification, token response checking, error response checking, and basic response time validation.

---

## Test Cases

### TC-LI-001 - Login - valid email and password

**Test Type**
Positive test case

**Description**
Verify that login succeeds when both valid email and password are provided.

**Request**

* Method: `POST`
* Endpoint: `/api/login`
* Request Body:

```json
{
  "email": "eve.holt@reqres.in",
  "password": "cityslicka"
}
```

**Expected Result**

* Status code should be `200`
* Response should contain `token`
* `token` should not be empty
* Response time should be under `1000ms`

---

### TC-LI-002 - Login - missing password

**Test Type**
Negative test case

**Description**
Verify that login fails when the `password` field is missing.

**Request**

* Method: `POST`
* Endpoint: `/api/login`
* Request Body:

```json
{
  "email": "eve.holt@reqres.in"
}
```

**Expected Result**

* Status code should be `400`
* Response should contain `error`
* `error` should not be empty
* Response time should be under `1000ms`

---

### TC-LI-003 - Login - missing email

**Test Type**
Negative test case

**Description**
Verify that login fails when the `email` field is missing.

**Request**

* Method: `POST`
* Endpoint: `/api/login`
* Request Body:

```json
{
  "password": "cityslicka"
}
```

**Expected Result**

* Status code should be `400`
* Response should contain `error`
* `error` should not be empty
* Response time should be under `1000ms`

---

## Notes

Reqres is a public mock API. The login endpoint returns predefined success or error responses based on the request body.

These test cases are designed to validate the actual API response behavior, including successful token response handling and required field error handling.
