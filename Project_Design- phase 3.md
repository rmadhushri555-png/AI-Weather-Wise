# Phase 3: Project Design

## Architecture Pattern
The AI WeatherWise application follows the **MVC (Model-View-Controller)** pattern to decouple business logic from data management.

- **Model Layer** – Mongoose schemas defining User and Location entities, validation rules, and defaults.
- **Controller Layer** – Captures requests, validates input, calls weather/Gemini services, and returns JSON responses.
- **View Layer** – Since this is a headless backend, the "view" is the API Routing Layer that maps HTTP endpoints to controllers.

## System Architecture Diagram (Text Representation)

```
Client (Postman / Frontend)
        |
        v
Express Server Gateway (routes, CORS, JSON parsing)
        |
        v
Auth & Role Middleware (JWT validation, role check)
        |
        v
Controllers (business logic)
   |            |
   v            v
Weather Service   Gemini AI Service
(OpenWeatherMap)   (@google/generative-ai)
   |            |
   v            v
        Mongoose Models
              |
              v
          MongoDB
```

## Entity-Relationship (ER) Diagram Description
- **User (1) → Location (Many)**: one registered user can save multiple favorite locations.

```
User                     Location
----                     --------
_id  ────────────────►  user (FK)
name                     city
email                    country
password                 createdAt
role
```

## User Flow
1. User registers or logs in.
2. User saves a favorite city via the API.
3. User fetches current weather metrics for that city.
4. User requests AI-driven insights (summary/recommendation) based on the weather data.
5. System validates the JWT and returns the requested information.

## Key Components
- **Express Server Gateway** – handles ports, HTTP methods, JSON payloads, CORS.
- **Authentication & Role Matrix Middleware** – validates tokens and role-based access.
- **Granular Service/Logic Modules** – isolated domain rules for weather + recommendation logic.
- **Database Interface Layer (Mongoose)** – translates app logic into MongoDB queries.
- **AI Service Integration** – Gemini generates natural-language summaries and recommendations.

## UI / Interface Note
This is a pure backend service — there is no UI. All interaction happens through REST API endpoints tested via Postman/Thunder Client.
