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
{
  "name": "John",
  "job": "QA Engineer"
}
