# GET /users — List Users API

## API

* **Method:** `GET`
* **Base URL:** `https://reqres.in`
* **Endpoint:** `/api/users`

## Objective

Verify that the List Users API returns user list data correctly for valid page queries and handles page values beyond the available range properly.

This document focuses on status code verification, response structure checking, array validation, query parameter handling, and basic response time validation.

---

## Test Cases

### TC-LU-001 - List Users - valid page 2

**Test Type**
Positive test case

**Description**
Verify that the API returns a user list successfully when `page=2` is provided.

**Request**

* Method: `GET`
* Endpoint: `/api/users`
* Query Params: `page=2`
* Request Body: Not applicable

**Expected Result**

* Status code should be `200`
* Response should contain `page`
* Response should contain `per_page`
* Response should contain `total`
* Response should contain `total_pages`
* Response should contain `data`
* `data` should be an array
* `page` should equal `2`
* Response time should be under `1000ms`

---

### TC-LU-002 - List Users - valid page 1

**Test Type**
Positive test case

**Description**
Verify that the API returns a user list successfully when `page=1` is provided.

**Request**

* Method: `GET`
* Endpoint: `/api/users`
* Query Params: `page=1`
* Request Body: Not applicable

**Expected Result**

* Status code should be `200`
* Response should contain `page`
* Response should contain `per_page`
* Response should contain `total`
* Response should contain `total_pages`
* Response should contain `data`
* `data` should be an array
* `page` should equal `1`
* Response time should be under `1000ms`

---

### TC-LU-003 - List Users - page beyond total pages

**Test Type**
Boundary / out-of-range query parameter check

**Description**
Verify that the API handles a page number beyond the total available pages by returning an empty user list.

**Request**

* Method: `GET`
* Endpoint: `/api/users`
* Query Params: `page=999`
* Request Body: Not applicable

**Expected Result**

* Status code should be `200`
* Response should contain `page`
* Response should contain `per_page`
* Response should contain `total`
* Response should contain `total_pages`
* Response should contain `data`
* `data` should be an array
* `data` should be empty
* `page` should equal `999`
* Response time should be under `1000ms`

---

## Notes

Reqres is a public mock API. When a page number is beyond the available range, the API may still return a successful `200` response with an empty `data` array.

This test case documents the actual behavior of the API and checks whether the response structure remains consistent even when the query parameter is outside the normal data range.
