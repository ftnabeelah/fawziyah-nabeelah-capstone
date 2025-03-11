# Moodsight – A Minimalist Mood Tracker

## Overview

Moodsight is a web application that allows users to log their daily moods and track patterns over time. The app integrates with the OpenWeather API to fetch the weather conditions at the time of each entry. Users can view their past moods and trends, with options to filter by date ranges and edit past entries.

### Problem Space

Many people want to track their moods but find traditional journaling overwhelming. Moodsight provides a low-effort solution where users can quickly log their moods, view past trends, and see how weather conditions might correlate with their emotions.

### User Profile

People who prefer a quick, structured way to track moods without full journaling.

How will they use it?

1. Open the app and see a simple mood submission form.
2. Select a mood (Happy, Neutral, Sad, etc.), and the app automatically fetches the current weather.
3. Submit the mood entry.
4. View past moods on a dashboard, where they can see trends over time.[optional, could be a simple list]
5. Filter mood history by date range (e.g., last week, last month).[optiona]
6. Edit or delete past entries if needed.

### Features

1. Log Mood Entries: Users select a mood from a predefined set and submit it.
2. Weather API Integration: Automatically fetches weather conditions at the time of submission.
3. Mood History Dashboard: Displays past moods and weather correlations.
4. Edit & Delete Entries: Users can modify or remove past mood logs.
5. Filter by Date Range: Users can view mood history within specific periods (e.g., last 7 days, last month). [optiona]
6. Basic Data Visualization: Simple charts to show mood trends over time. [optional]

## Implementation

### Tech Stack

1. Frontend: React.js (for UI)
2. Backend: Express.js (Node.js server for handling API requests)
3. Database: SQL database (for storing mood logs)
4. Chart.js (for mood trend visualizations) [option]

### APIs

OpenWeather API → Fetches real-time weather data for mood entries. (https://openweathermap.org/api) 1,000 API calls per day for free

### Sitemap

1. Home Page (Mood Submission Form)
- Users see a dropdown to select a mood.
- Weather is auto-fetched and displayed.
- Clicking "Submit" saves the entry.

2. Dashboard Page
- Displays a list of past mood entries.
- Shows a simple trend chart (last 5 moods).
- Allows filtering entries by date range.

3. Edit Entry Page
- Users can modify a past mood entry.
- Saves updates to the database.

4. Delete Entry (Confirmation Modal)
- Users can remove unwanted mood logs.


### Mockups

Low fidelity Wireframes
![Mockup Screenshot](images/mockup.png)

### Data

The application will use a SQL database with the following structure:

| Column | Data Type | Description |
|--------|------|-------------|
| id | PRIMARY KEY | Unique identifier for each mood entry |
| date | DATE NOT NULL | The date of the mood entry |
| mood | VARCHAR(20) NOT NULL | Mood selected by user (e.g., Happy, Neutral, Sad) |
| temperature | FLOAT | Temperature at the time of entry |
| weather_condition | VARCHAR(50) | Description of the weather (e.g., Sunny, Cloudy) |

Data Flow Example
1. User submits a mood entry.
2. Frontend calls OpenWeather API → Fetches real-time weather data.
3. Frontend sends data (mood + weather) to backend via a POST request.
4. Backend saves entry into the SQL database (logs table).
5. Dashboard fetches mood history using a GET request.
6. Users can update or delete entries through PUT or DELETE requests.

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /logs | Fetch all mood logs |
| GET | /logs/:id | Fetch a single mood entry by ID |
| GET | /logs?startDate=YYYY-MM-DD&endDate=YYYY-MM-DD | Fetch logs within a date range |
| POST | /logs | Add a new mood entry (includes weather data) |
| PUT | /logs/:id | Edit an existing mood entry |
| DELETE | /logs/:id | Delete a mood entry |

#### Example Requests and Responses

**Example POST Request (Adding a New Mood Entry):**
```json
{
  "date": "2025-03-06",
  "mood": "Happy",
  "temperature": 18.5,
  "weather_condition": "Sunny"
}
```

**Example GET Request (Fetching Logs for a Date Range):**
```
GET /logs?startDate=2025-03-01&endDate=2025-03-07
```

**Example Response:**
```json
[
  {
    "id": 1,
    "date": "2025-03-01",
    "mood": "Happy",
    "temperature": 20.5,
    "weather_condition": "Sunny"
  },
  {
    "id": 2,
    "date": "2025-03-03",
    "mood": "Neutral",
    "temperature": 15.2,
    "weather_condition": "Cloudy"
  }
]
```

## Roadmap

### Week 1: Backend & API Setup
- [ ] Set up PostgreSQL database
- [ ] Implement Express.js API with CRUD endpoints
- [ ] Integrate OpenWeather API
- [ ] Test data retrieval

### Week 2: Frontend & UI Development
- [ ] Build React UI (Home Page & Dashboard)
- [ ] Connect frontend to API (Fetch & Display Data)
- [ ] Implement Mood Trends Chart
- [ ] Final Testing & Deployment

---

## Future Implementations

- Authentication → Allow multiple users with personal mood logs.
- Mood Analytics → Provide insights on mood trends over months.
- Dashboard and filtering if I don't complete them