# Phase 2: Requirement Analysis

## 1. Software Requirements
- Operating System: Windows 10/11, macOS, or Linux
- Node.js (v16 or above)
- npm (v8 or above)
- Gemini AI SDK: `@google/generative-ai`
- MongoDB (NoSQL database)
- Postman (API testing)
- Code Editor: Visual Studio Code

## 2. Hardware Requirements
- Processor: Intel Core i5 (8th Gen or above) / AMD Ryzen 5 or equivalent
- RAM: 8 GB minimum (16 GB recommended)
- Storage: 1 GB available disk space

## 3. Functional Requirements
- User registration and login with JWT-based authentication
- Password hashing using bcrypt
- CRUD operations for favorite locations (city, country)
- Fetch real-time weather data for a given city
- Generate AI-based weather summaries and activity/clothing recommendations via Gemini
- Role-based access (Admin vs Registered User)
- Public endpoints for basic weather lookup without login

## 4. Non-Functional Requirements
- Security: JWT auth, bcrypt hashing, input sanitization against XSS/NoSQL injection
- Performance: fast API response for weather + AI insight requests
- Reliability: fallback mode so the API still functions if external API keys are missing
- Maintainability: modular MVC folder structure
- Scalability: stateless REST APIs that can handle multiple concurrent users

## 5. Data Requirements
**User Entity**
- `_id` (ObjectId, Primary Key)
- `name` (String, Required)
- `email` (String, Required, Unique)
- `password` (String, Hashed, Required)
- `role` (String, Default: "reader")

**Location Entity**
- `_id` (ObjectId, Primary Key)
- `user` (Foreign Key → User)
- `city` (String, Required)
- `country` (String, Required)
- `createdAt` (Date, Default: Now)

## 6. Tools for Development & Testing
- Postman / Thunder Client for API verification
- Git & GitHub for version control and submission
- Google Drive for demo video hosting
