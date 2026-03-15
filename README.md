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

### List Users
- Valid page request
- Different page values
- Non-existent page handling

### Single User
- Valid user ID
- User not found scenario
- Invalid user ID scenario

### Create User
- Valid request body
- Missing field scenario
- Empty body scenario

### Login
- Successful login
- Negative login scenarios

---

## Folder Structure

```bash
api-testing-practice/
├─ postman/
│  └─ Reqres API Test.postman_collection.json
├─ test-cases/
│  ├─ create-user.md
│  ├─ get-single-user.md
│  ├─ list-users.md
│  └─ ...
└─ README.md
```

## Test Case Documentation

Each API module includes a separate markdown file under the `test-cases/` folder.

These documents typically include:

- API method and endpoint
- Test objective
- Test case ID
- Test description
- Request details
- Expected results

This helps keep the testing process organized and makes the project easier to review.

---

## Postman Test Coverage

In Postman, each request includes test scripts for validating:

- Status code
- Key fields in the response body
- Response structure
- Array existence
- Response time

Example checks include:

- Status code equals expected value
- Response contains required fields
- Returned data type matches expectation
- Response time is within acceptable range

---

## How to Run

### 1. Clone this repository

```bash
git clone <Reqres API Test.postman_collection.json>
```

### 2. Open Postman

Import the Postman collection file from the `postman/` folder.

### 3. Select a request

Choose any request from the collection, such as:

- `TC-LU-001 - List Users - page=2`
- `TC-SU-001 - Single User - id=2`
- `TC-CU-001 - Create User - valid name and job`

### 4. Send the request

Review:

- Request URL
- Response status
- Response body
- Test results in the **Tests** tab

### 5. Run the full collection (optional)

Use the **Collection Runner** in Postman to execute all test cases together.

---

## Example Test Scenarios

- **List Users**: valid page, different page values, non-existent page
- **Single User**: valid user ID, user not found, invalid user ID
- **Create User**: valid payload, missing field, empty body

---

## Notes / Limitations

- **Reqres is a public practice API**, so some endpoints simulate behavior rather than performing real database operations.
- Some POST requests may return mock success responses without actual persistence.
- This project focuses on API request/response validation, not full backend data verification.
- Certain negative cases may reflect the mock API design rather than production-level backend validation logic.

---

## What I Practiced in This Project

Through this project, I practiced:

- Writing structured API test cases
- Designing both positive and negative scenarios
- Organizing test cases in a readable format
- Using Postman for request validation
- Building a small but complete QA-style testing project for portfolio use

---

## Future Improvements

Possible next improvements for this project:

- Add more endpoints such as update user and delete user
- Add JSON schema validation
- Add environment variables in Postman
- Add automated collection run screenshots or reports
- Improve negative test coverage for request body validation

---

## Author

Jill Hu
