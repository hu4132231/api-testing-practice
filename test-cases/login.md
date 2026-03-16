## API
- **Method:** `POST`
- **Base URL:** `https://reqres.in`
- **Endpoint:** `/api/login`

## Objective
Verify that the Login API returns a token for valid credentials and returns appropriate error responses for missing required fields.

---

## Test Cases

### TC-LI-001 - Login - valid email and password

**Description**  
Verify that login succeeds when both valid email and password are provided.

**Request**
- Method: `POST`
- Endpoint: `/api/login`
- Request Body:
```json
{
  "email": "eve.holt@reqres.in",
  "password": "cityslicka"
}
```

**Expected Result**  
- Status code is `200`
- Response contains `token`
- `token` is not empty
- Response time is under `1000ms`

---

### TC-LI-002 - Login - missing password

**Description**  
Verify that login fails when the password field is missing.

**Request**
- Method: `POST`
- Endpoint: `/api/login`
- Request Body:
```json
{
  "email": "eve.holt@reqres.in",
}
```

**Expected Result**
- Status code is `400`
- Response contains `error`
- `error` is not empty
- Response time is under `1000ms`

---

### TC-LI-003 - Login - missing email

**Description**  
Verify that login fails when the email field is missing.

**Request**
- Method: `POST`
- Endpoint: `/api/login`
- Request Body:
```json
{
  "password": "cityslicka"
}
```

**Expected Result**
- Status code is `400`
- Response contains `error`
- `error` is not empty
- Response time is under `1000ms`
