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

This project is organized as a small QA-style portfolio project to demonstrate test case design, request validation, and basic Postman test implementation.

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
- Valid page 2
- Valid page 1
- Page beyond total pages

### Single User
- Valid existing user ID
- Another valid user ID
- Non-existing user ID

### Create User
- Valid name and job
- Missing job
- Empty request body

### Login
- Valid email and password
- Missing password
- Missing email

---

## Folder Structure

```bash
api-testing-practice/
├─ postman/
│  └─ Reqres API Test.postman_collection.json
├─ test-cases/
│  ├─ create-user.md
│  ├─ single-user.md
│  ├─ list-users.md
│  ├─ login.md
│  └─ ...
└─ README.md
```

---

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

In Postman, each request includes test scripts for validating key response conditions such as:

- Status code
- Required fields in the response body
- Basic response structure
- Array existence where applicable
- Basic response time checks
- Value matching between request and response where applicable

Example checks include:

- Status code equals expected value
- Response contains required fields
- Returned data type matches expectation
- Response time is within acceptable range

---

## How to Use

### 1. Open this repository on GitHub

Review the project structure, README, and test case documents under the `test-cases/` folder.

### 2. Open Postman

Import the Postman collection file from the `postman/` folder.

### 3. Select a request

Choose any request from the collection, such as:

- `TC-LU-001 - List Users - valid page 2`
- `TC-SU-001 - Single User - valid existing user ID`
- `TC-CU-001 - Create User - valid name and job`
- `TC-LI-001 - Login - valid email and password`

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

- **List Users**: valid page 1, valid page 2, page beyond total pages
- **Single User**: valid existing user ID, another valid existing user ID, non-existing user ID
- **Create User**: valid name and job, missing job, empty request body
- **Login**: valid email and password, missing password, missing email

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
