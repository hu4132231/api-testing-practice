# 📂 QA Practice Project — API Testing (Reqres Public API)

This repository is a hands-on QA practice project focused on **manual API testing** using a public REST API.  
The project demonstrates structured test case design, API contract validation, and practical Postman testing workflows.

---

## 🎯 Project Goals

- Practice manual API testing workflows
- Design clear and structured test cases
- Validate API responses, including:
  - HTTP status codes
  - Response headers
  - Response body structure and field types
- Verify API behavior for both **happy paths and negative scenarios**
- Build QA thinking focused on **API contract stability and frontend safety**

---

## 🧪 API Under Test

**Reqres Public API**  
https://reqres.in

---

## 📁 Project Structure

```text
api-testing-practice/
├─ README.md
├─ postman/
│  └─ Reqres API Test.postman_collection.json
└─ test-cases/
   ├─ list-users.md
   └─ get-single-user.md
```

## Test Cases
- [GET List Users](test-cases/list-users.md) (completed with assertions)
- GET Single User (planned)
- POST Create User (planned)
- Login scenarios (planned)

## Tools
- Postman: Used for sending API requests and validating responses with assertions.
- GitHub: Version control and project hosting.
- Postman collection is included under `/postman` for API request execution and assertions.

## Notes
This project is continuously updated as I practice manual API testing
and improve my test case design skills for Junior QA / Testing Engineer roles.
