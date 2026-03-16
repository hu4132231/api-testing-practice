# GET /users — List Users API

## API
- **Method:** GET
- **Endpoint:** `/api/users`

## Objective
Verify that the List Users API returns user list data correctly for valid page queries and handles page values beyond the available range properly.

---

## Test Cases

### TC-LU-001 - List Users - valid page 2

**Description**  
Verify that the API returns a user list successfully for page 2.

**Request**
- Method: `GET`
- Endpoint: `/api/users?page=2`
- Query Params: `page=2`
- Request Body: Not applicable

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `per_page`
- Response contains `total`
- Response contains `total_pages`
- Response contains `data`
- `data` is an array
- `page` equals `2`
- Response time is under `1000ms`

---

### TC-LU-002 - List Users - valid page 1

**Description**  
Verify that the API returns a user list successfully for page 1.

**Request**
- Method: `GET`
- Endpoint: `/api/users?page=1`
- Query Params: `page=1`
- Request Body: Not applicable

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `per_page`
- Response contains `total`
- Response contains `total_pages`
- Response contains `data`
- `data` is an array
- `page` equals `1`
- Response time is under `1000ms`

---

### TC-LU-003 - List Users - page beyond total pages

**Description**  
Verify that the API handles a page number beyond the total available pages by returning an empty user list.

**Request**
- Method: `GET`
- Endpoint: `/api/users?page=999`
- Query Params: `page=999`
- Request Body: Not applicable

**Expected Result**
- Status code is `200`
- Response contains `page`
- Response contains `per_page`
- Response contains `total`
- Response contains `total_pages`
- Response contains `data`
- `data` is an array
- `data` is empty
- Response time is under `1000ms`
