# Project Title

## Overview

Moodsight is a simple web app that helps users log their daily moods and track patterns over time. The app integrates with the OpenWeather API to automatically fetch the weather conditions at the time of each entry. Users can view their past moods and trends in a visually simple and accessible format.

### Problem Space

Many people want to track their moods but find traditional journaling overwhelming. Moodsight provides a quick and easy way to log emotions, helping users reflect on their mental well-being over time without unnecessary complexity.

### User Profile

People who want a low-effort way to track their emotions.
-Select a mood from a simple list (Happy, Neutral, Sad, etc.).
-View past moods in a history log.
-See weather conditions alongside their moods.

### Features

Log Moods → Users select their mood from predefined options.
Mood History → View past mood entries in a simple list.
Edit & Delete Entries → Users can modify or remove past entries.
Weather API Integration → Fetches real-time weather at the time of logging.
Basic Trends Visualization → A simple chart to see mood patterns over time. (optional)

## Implementation

### Tech Stack

Frontend: React.js
Backend: Express.js (for API handling)
Database: JSON storage for simplicity
Libraries: Chart.js (for data visualization -> optional)

### APIs

OpenWeather API → Fetches real-time weather data for mood entries. (https://openweathermap.org/api) 
1,000 API calls per day for free

### Sitemap

Home Page → Displays a summary of recent mood entries and trends.
New Entry Page → Allows users to log a new mood.
History Page → Lists past moods with filtering options.

### Mockups

***Provide visuals of your app's screens. You can use pictures of hand-drawn sketches, or wireframing tools like Figma.

### Data

{
  "id": "uuid",
  "date": "2025-03-06",
  "mood": "Happy",
  "weather": "Sunny, 18°C"
}
 

### Endpoints

List endpoints that your server will implement, including HTTP methods, parameters, and example responses.



1. GET	    /moods	      Fetch all mood entries
2. POST	    /moods	      Create a new mood entry
3. PUT	    /moods/:id	  Edit an existing entry
4. DELETE	/moods/:id	  Delete a mood entry

## Roadmap

Week 1: Set up project structure and integrate the OpenWeather API.
Week 2: Implement mood logging (CRUD operations).
Week 3: Build mood trends visualization.
Week 4: Testing, UI polish, and deployment.

---

## Future Implementations
Allows multiple users to track their moods separately so will have to build out authentication 


