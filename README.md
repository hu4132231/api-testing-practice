# Reqres API Testing Project

## Project Overview
This project is a simple API testing practice project using Reqres public API and Postman.

The purpose of this project is to practice:
- API request and response validation
- Status code checking
- Response structure validation
- Positive and negative test case design

## Tools Used
- Postman
- Reqres API
- Markdown

## APIs Covered
- GET /users?page=2
- GET /users/{id}
- POST /users
- POST /login

## Test Scenarios
This project includes both positive and negative test cases, such as:
- valid request
- missing required field
- empty request body
- non-existent resource

## How to Run
1. Open the Postman collection
2. Select the request you want to test
3. Click **Send**
4. Review response data and test results in the **Tests** tab

## Project Structure
- `postman/` → Postman collection
- `test-cases/` → API test case documents
- `README.md` → project summary

## Notes
This project uses Reqres demo API for practice purposes.
Some negative scenarios are based on actual observed API behavior from the demo service.
