# Phase 6: Project Testing

## Testing Tool
Postman / Thunder Client

## Test Cases

| Test ID | Endpoint | Scenario | Input | Expected Output | Actual Output | Status |
|---|---|---|---|---|---|---|
| TC01 | POST /api/auth/register | Register new user | Valid name, email, password | 201 Created, user saved | | |
| TC02 | POST /api/auth/register | Duplicate email | Existing email | 400 Bad Request, "email exists" | | |
| TC03 | POST /api/auth/login | Valid login | Correct email/password | 200 OK, JWT token returned | | |
| TC04 | POST /api/auth/login | Invalid login | Wrong password | 401 Unauthorized | | |
| TC05 | POST /api/locations | Add favorite city (authenticated) | Valid JWT + city, country | 201 Created, location saved | | |
| TC06 | POST /api/locations | Add city without token | No JWT | 401 Unauthorized | | |
| TC07 | GET /api/weather?city=Chennai | Fetch weather for valid city | "Chennai" | 200 OK, weather JSON | | |
| TC08 | GET /api/weather?city=xyzxyz | Fetch weather for invalid city | Garbage city name | 404 Not Found / error message | | |
| TC09 | GET /api/recommendation?city=Chennai | Get AI recommendation | Valid city + JWT | 200 OK, Gemini-generated summary | | |
| TC10 | GET /api/weather | Missing required parameter | No city param | 400 Bad Request | | |

*(Fill in "Actual Output" and "Status" — Pass/Fail — after you run each test in Postman, and attach screenshots.)*

## Testing Checklist
- [ ] All authentication routes tested (register/login)
- [ ] JWT protection verified on protected routes
- [ ] CRUD operations on Location tested
- [ ] Weather API tested with valid and invalid cities
- [ ] Gemini AI recommendation endpoint tested
- [ ] Error handling tested (missing fields, invalid input, server errors)
- [ ] Postman screenshots captured for each test case
