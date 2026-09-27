# Phase 5: Project Development

## Project Setup Steps
1. Create a new folder named `AI-Weatherwise`.
2. Open the folder in Visual Studio Code.
3. Initialize the Node.js project:
   ```
   npm init -y
   ```
4. Install required dependencies:
   ```
   npm install express mongoose dotenv jsonwebtoken bcrypt cors @google/generative-ai
   ```
5. Install Nodemon for development:
   ```
   npm install --save-dev nodemon
   ```

## Files Created
- `index.js` – application entry point
- `.env` – environment variables (never committed to GitHub)
- `package.json` – project metadata and dependencies
- `.gitignore` – excludes `.env` and `node_modules`

## Folder Structure
```
AI-Weatherwise/
├── controllers/
├── models/
├── routes/
├── middleware/
├── services/
├── index.js
├── .env
├── .gitignore
└── package.json
```

## Environment Configuration (`.env`)
```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```
> ⚠️ Replace placeholder values with your own keys locally. Do **not** upload the real `.env` file to GitHub.

## Core Modules
- **index.js** – initializes the Express server, loads environment variables, configures middleware, connects to MongoDB, registers routes, and starts the server.
- **Auth Middleware** – validates JWT tokens and checks user roles.
- **Weather Service** – fetches live data from OpenWeatherMap.
- **AI Service** – sends weather data to Google Gemini (`@google/generative-ai`) and returns natural-language summaries/recommendations.
- **Models** – Mongoose schemas for `User` and `Location`.

## Key Features Implemented
- Role-based route guarding
- Secure JWT authentication + bcrypt password hashing
- CRUD for favorite locations
- Real-time weather fetch endpoint
- AI-generated weather summary & recommendation endpoint
- Centralized error handling and input sanitization

## Note
Follow the reference video step-by-step while writing the actual code, and commit regularly to GitHub so every team member's contribution is visible.
