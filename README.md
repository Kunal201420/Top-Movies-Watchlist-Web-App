# Top-Movies-Watchlist-Web-App

## Overview
A full-featured Flask web application for managing a personal movie collection with TMDB API integration. Users can search movies by title, auto-fetch details/posters, add to SQLite database, rate/review them, edit rankings, and delete entries. Features Bootstrap5 UI and comprehensive CRUD operations.

## Features
- Search movies via TMDB API and auto-populate details/posters
- Add movies with title, year, description, rating, review, image
- View ranked movie list (by rating) on home page
- Edit movie ratings and reviews
- Delete movies from collection
- Responsive Bootstrap5 design with form validation

## Tech Stack
- **Backend**: Flask, Flask-SQLAlchemy, Flask-WTF, Flask-Bootstrap5
- **API**: TMDB (The Movie Database) API v3
- **Database**: SQLite (`movies.db`) with ORM models
- **Frontend**: Bootstrap5, Jinja2 templates
- **HTTP**: requests.Session with Bearer auth headers

## Quick Setup
1. Install dependencies:
2. Run the app:
3. Open `http://localhost:5000`
4. Database `movies.db` created automatically with schema[attached_file:15]

## Routes
| Route | Description | Method |
|-------|-------------|--------|
| `/` | View all movies (ranked by rating) | GET |
| `/add` | Search & add new movie | GET/POST |
| `/find?id=<api_id>` | Fetch movie details from TMDB | GET |
| `/edit?id=<movie_id>` | Rate/review movie | GET/POST |
| `/delete?id=<movie_id>` | Delete movie | GET |[attached_file:15]

## Database Schema
Movie Table:

id (Integer, Primary Key)

title (String 250, Unique, Not Null)

year (Integer, Not Null)

description (String 500, Not Null)

rating (Float, Nullable)

ranking (Integer, Nullable)

review (String 250, Nullable)

imgurl (String 250, Not Null)


## File Structure
project/
├── main.py # Complete Flask app + TMDB integration
├── movies.db # SQLite database (auto-created)
├── templates/
│ ├── index.html # Movie list
│ ├── add.html # Search form
│ ├── select.html # Movie selection
│ └── edit.html # Rating form
└── README.md # This file

## API Integration
- TMDB Bearer token embedded (replace for production)
- Auto-fetches: title, release year, poster, overview
- Search endpoint: `/3/search/movie`
- Details endpoint: `/3/movie/{id}`
