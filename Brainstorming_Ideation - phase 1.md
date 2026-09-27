# Phase 1: Brainstorming & Ideation

## Project Title
AI WeatherWise API

## Background / Case Study
Alex is a travel enthusiast who frequently visits different cities and needs a streamlined way to track local weather conditions and receive AI-driven activity suggestions based on current forecasts.

## Problem Statement
- Difficulty tracking and managing multiple favorite weather locations efficiently.
- Lack of personalized recommendations for outdoor activities or clothing based on weather.
- Need for natural language weather summaries rather than just raw data metrics.
- Absence of a secure system to store and sync location preferences across devices.

## Target Users
- **Registered User** – saves favorite cities, fetches weather, requests AI insights.
- **Admin** – manages user accounts, monitors API health and system logs.
- **Public/Weather App User** – can consume public weather endpoints without an account.

## Proposed Solution
Build a RESTful backend (AI WeatherWise) using Node.js, Express.js and MongoDB that:
- Lets users register/login securely (JWT authentication).
- Allows CRUD operations on favorite locations.
- Fetches real-time weather data (OpenWeatherMap).
- Uses Google Gemini AI to convert raw weather metrics into natural-language summaries and personalized recommendations (e.g., clothing/activity suggestions).

## Ideas Considered
| Idea | Why Selected / Rejected |
|---|---|
| Plain weather API wrapper (no AI) | Rejected – doesn't solve the "raw data is hard to interpret" problem |
| Weather + AI recommendation backend (AI WeatherWise) | **Selected** – directly solves personalization + natural language summary problem |
| Weather + social sharing app | Rejected – out of scope for backend track |

## Outcome / Expected Benefit
Users spend less time interpreting raw weather metrics and get context-aware, AI-generated advice, while their location data stays organized and secure.
