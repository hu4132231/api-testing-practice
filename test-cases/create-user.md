# 🧪 Create User API Test Cases

## Endpoint
**POST** `/users`

## API
Reqres Public API

---

## 📌 API Description

Create a new user with provided name and job information.  
This API simulates user creation and returns a generated `id` and `createdAt` timestamp.

---

## 📥 Request Specification

### Method
POST

### Endpoint
`/users`

### Headers
```http
Content-Type: application/json
```

---

### Request Body (Example)
```json
{
  "name": "John",
  "job": "QA Engineer"
}
```

---

## 📤 Expected Response (Success)
### Status Code
### 201 Created

###Response Body
```json
{
  "name": "John",
  "job": "QA Engineer",
  "id": "123",
  "createdAt": "2026-01-15T08:00:00.000Z"
}
```

---

## ✅ Test Cases
### TC-CU-001 — Create user successfully (valid request)

### Request
name: valid string
job: valid string

### Expected Result
Status code is 201
Response format is JSON
Response contains:
  name (string)
  job (string)
  id (string, auto-generated)
  createdAt (ISO 8601 timestamp)
Response time is within acceptable range

##Notes
id and createdAt are system-generated
Do not assert fixed values
