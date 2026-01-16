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

- [GET /users — List Users API](test-cases/list-users.md) (completed)
- [GET /users/{id} — Single User API](test-cases/get-single-user.md) (completed)
- POST /users — Create User (planned)
- POST /login — Login scenarios (planned)

## Tools

- **Postman** — Sending API requests and validating responses with test scripts
- **Git / GitHub** — Version control and project hosting
- **Markdown** — Test case documentation

## Notes
This project is continuously updated to practice manual API testing and demonstrate test case design skills for Junior QA / Testing Engineer roles.

Only test cases with explicit QA design and validation logic are documented under `/test-cases`.
Official API examples are kept in Postman as reference and are not duplicated as test documentation.
