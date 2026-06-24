# API Testing & QA Documentation Practice Project

## Project Overview

This is an API testing and QA documentation practice project built with **Postman** and the **Reqres public API**.

The goal of this project is to practice core API testing and documentation skills, including:

* API request and response validation
* HTTP status code verification
* Response body and data structure checking
* Positive and negative test case design
* Basic response time validation
* Test case documentation and organization
* Validation record organization and issue traceability

This project is organized as a small QA-style portfolio project to demonstrate test case design, request validation, testing documentation, and structured validation records.

It also focuses on presenting test cases in a clear and traceable format, which is useful for QA documentation, issue tracking, technical document handling, and validation process support.

---

## Tools Used

* **Postman** — API request creation, test execution, and response validation
* **Reqres API** — Public API used for testing practice
* **GitHub** — Version control and project documentation
* **Markdown** — Test case and project documentation

---

## API Endpoints Covered

This project currently covers the following API modules:

### List Users

* Valid page 2
* Valid page 1
* Page beyond total pages

### Single User

* Valid existing user ID
* Another valid existing user ID
* Non-existing user ID

### Create User

* Valid name and job
* Missing job
* Empty request body

### Login

* Valid email and password
* Missing password
* Missing email

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

The test case documents typically include:

* API method and endpoint
* Test objective
* Test case ID
* Test description
* Request details
* Expected results
* Validation points

This helps keep the testing process organized and makes the project easier to review, maintain, and trace.

---

## Postman Test Coverage

In Postman, each request includes test scripts for validating key response conditions such as:

* Status code
* Required fields in the response body
* Basic response structure
* Array existence where applicable
* Basic response time checks
* Value matching between request and response where applicable

Example validation checks include:

* Status code equals the expected value
* Response contains required fields
* Returned data type matches expectation
* Response time is within an acceptable range
* Error response appears when required input is missing

---

## Validation Approach

The project uses a basic QA validation approach:

1. Understand the API endpoint and expected behavior
2. Define positive and negative test scenarios
3. Create test cases with clear expected results
4. Execute requests in Postman
5. Verify status code, response body, and key fields
6. Record test logic and validation points in documentation

This approach helps build a clear connection between test scenarios, expected outcomes, and actual API responses.

---

## How to Use

### 1. Review the Repository

Open this repository on GitHub and review:

* Project structure
* README file
* Test case documents under the `test-cases/` folder
* Postman collection under the `postman/` folder

### 2. Open Postman

Import the Postman collection file from the `postman/` folder:

```bash
Reqres API Test.postman_collection.json
```

### 3. Select a Request

Choose any request from the collection, such as:

* `TC-LU-001 - List Users - valid page 2`
* `TC-SU-001 - Single User - valid existing user ID`
* `TC-CU-001 - Create User - valid name and job`
* `TC-LI-001 - Login - valid email and password`

### 4. Send the Request

Review the following items in Postman:

* Request method and URL
* Request body, if applicable
* Response status code
* Response body
* Test results in the **Tests** tab

### 5. Run the Full Collection

Use the **Collection Runner** in Postman to execute all test cases together and review the overall test results.

---

## Example Test Scenarios

| Module      | Scenario                 | Expected Focus                             |
| ----------- | ------------------------ | ------------------------------------------ |
| List Users  | Valid page 2             | Status code, user list, response structure |
| List Users  | Page beyond total pages  | Empty data handling                        |
| Single User | Valid user ID            | User data and required fields              |
| Single User | Non-existing user ID     | Error handling and status code             |
| Create User | Valid name and job       | Created user response validation           |
| Create User | Empty request body       | API behavior with missing input            |
| Login       | Valid email and password | Token response validation                  |
| Login       | Missing password         | Error response validation                  |

---

## Notes and Limitations

* **Reqres is a public practice API**, so some endpoints simulate behavior rather than performing real database operations.
* Some POST requests may return mock success responses without actual data persistence.
* This project focuses on API request and response validation, not full backend database verification.
* Certain negative cases may reflect the mock API design rather than production-level backend validation logic.
* This project is intended as a practice portfolio project for API testing, QA documentation, and validation process learning.

---

## What I Practiced in This Project

Through this project, I practiced:

* Writing structured API test cases
* Designing positive and negative test scenarios
* Using Postman to validate API responses
* Checking HTTP status codes and response fields
* Organizing test cases in a readable documentation format
* Recording validation logic clearly
* Building a small but complete QA-style testing project for portfolio use

---

## Future Improvements

Possible next improvements for this project include:

* Add more endpoints, such as update user and delete user
* Add Postman environment variables
* Add JSON schema validation
* Add test execution summary reports
* Add automated collection run screenshots or exported reports
* Improve negative test coverage for request body validation
* Add issue tracking examples for failed or unexpected test results

---

## Author

Jill Hu
