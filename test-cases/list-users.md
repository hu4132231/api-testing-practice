# GET /users?page=2 – List Users API

## Objective
Verify that the List Users API returns a valid list of users with correct structure and performance.

## Endpoint
GET https://reqres.in/api/users?page=2

## Preconditions
- API base URL is reachable
- No authentication required

## Test Steps
1. Send GET request to `/users?page=2`
2. Observe response status, headers, and body

## Expected Results
- Status code is 200
- Response format is JSON
- `data` field exists and is a non-empty array
- Each user object contains:
  - id (number)
  - email (string, contains "@")
  - first_name (string)
  - last_name (string)
  - avatar (string, URL)
- Response time is under 800ms

## Actual Result
- All assertions passed in Postman

## Notes
- This API is used for user list display on frontend
