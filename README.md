# Reqres API Testing Project

## Project Overview

This is a simple API testing practice project built with **Postman** and the **Reqres public API**.

The goal of this project is to practice core API testing skills, including:

- API request and response validation
- Status code verification
- Response structure checking
- Positive and negative test case design
- Basic response time validation
- Test case documentation and organization

This project is organized as a small QA-style portfolio project to demonstrate test design thinking, request validation, and basic Postman test implementation.

---

## Tools Used

- **Postman** — for API request creation, test execution, and response validation
- **Reqres API** — as the public API for testing practice
- **GitHub** — for project version control and documentation
- **Markdown** — for writing test case documents

---

## API Endpoints Covered

This project currently covers the following API modules:

### 1. List Users
- Valid page request
- Different page values
- Non-existent page handling

### 2. Single User
- Valid user ID
- User not found scenario
- Invalid user ID scenario

### 3. Create User
- Valid request body
- Missing field scenario
- Empty body scenario

### 4. Login
- Successful login
- Negative login scenarios *(if included in collection)*

---

## Test Design Scope

The test cases in this project are designed to validate:

- Correct HTTP status codes
- Response body structure
- Required response fields
- Data type and value existence
- Positive and negative scenarios
- Boundary-style checks using invalid or uncommon inputs
- Basic response time expectations

Example validations include:

- `200 OK` for successful GET requests
- `201 Created` for successful POST requests
- `404 Not Found` for non-existent resources
- Presence of fields such as `page`, `data`, `id`, `name`, `job`, and `createdAt`
- Response time under an expected threshold

---

## Folder Structure

```bash
api-testing-practice/
├─ postman/
│  └─ Reqres API Test.postman_collection.json
├─ test-cases/
│  ├─ list-users.md
│  ├─ get-single-user.md
│  ├─ create-user.md
│  └─ ...
└─ README.md
```
