# Weather-App-Backend
# Weather App Backend

This repository contains the backend code for a weather web application.  The primary function of this backend is to act as a proxy between the frontend and a weather API, fetching and processing weather data before sending it to the client.  The frontend is responsible for displaying the weather information to the user.

## Project Overview

This backend handles:

* Interacting with a weather API (e.g., OpenWeatherMap, WeatherAPI, AccuWeather).
* Optionally processing and transforming the weather data.
* Caching weather data to improve performance.
* Providing an API endpoint for the frontend to retrieve weather information.
* Handling API errors gracefully.

## Features

* **Weather API Proxy:** Fetches weather data from a chosen weather API.
* **Data Transformation (Optional):**  Processes the raw API response to extract, format, and combine relevant weather information.
* **Caching:** Implements caching to reduce API calls and improve response times.
* **API Endpoint:** Provides a `/api/weather` endpoint for the frontend to request weather data.
* **Error Handling:** Handles potential errors from the weather API and returns appropriate error messages.
* **API Key Security:** Securely stores and manages the weather API key.

## Technologies Used

* Node.js
* Express.js 
* `node-fetch` or `axios` (for making HTTP requests)
* `node-cache` or Redis (for caching)

## Installation

1. Clone the repository: `git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git`
2. Navigate to the project directory: `cd YOUR_REPOSITORY`
3. Install dependencies: `npm install`

## Usage

1. **Configuration:**
    * Create a `.env` file (or use your preferred method for environment variables).
    * Add your weather API key: `WEATHER_API_KEY=YOUR_API_KEY`
2. Start the server: `npm start` (or the command specified in your `package.json`).
3. The backend will be running on the specified port (e.g., `http://localhost:3000`).

## API Endpoint

* `/api/weather`:

    * **Method:** `GET`
    * **Query Parameters:**
        * `lat`: Latitude (required)
        * `lon`: Longitude (required)
        * or
        * `city`: City name (required if `lat` and `lon` are not provided)

    * **Response:** Returns a JSON object containing weather data.  Example:

```json
{
  "temperature": 25.5,
  "conditions": "Sunny",
  "humidity": 60,
  // ... other weather data
}