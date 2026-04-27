# Spotify Frontend Clone

This repository currently contains a **Spotify-plus-Verizon integration demo**, not just a static Spotify UI clone.

The repo name comes from the original presentation, but the actual project is a **Flask-based music discovery and message-sharing workflow** that connects Spotify search with Verizon messaging flows.

## What problem this project solves

Music apps are good at discovery, but sharing content across external communication flows is usually disconnected. This project explores a simple product idea:

- search for an artist
- inspect top tracks
- preview songs in the browser
- send the selected track list through a Verizon-connected messaging flow

Instead of stopping at “play music in the UI,” the project demonstrates **cross-service orchestration** between content discovery and delivery.

## What this project does

The application allows a user to:

1. search for an artist with Spotify
2. browse matching results
3. open the artist's top tracks
4. preview tracks when Spotify preview URLs are available
5. select a Verizon-connected device
6. send the track list to a friend

## Why this project is interesting

- It shows multi-step API orchestration instead of a one-page demo.
- It combines third-party content APIs with messaging workflows.
- It uses a real user journey rather than isolated endpoints.
- It demonstrates how a Flask application can coordinate multiple external services cleanly.

## Visual preview

![Spotify-Verizon home flow](docs/screenshots/home-preview.png)

![Spotify-Verizon top tracks flow](docs/screenshots/tracks-preview.png)

## Repository contents

- `app.py`: main Flask application
- `spotify_utils.py`: Spotify API helper logic
- `verizon_utils.py`: Verizon API helper logic
- `index.html`, `search_results.html`, `top_tracks.html`, `devices.html`, `success.html`, `error.html`: UI templates
- `.env.example`: sample environment configuration
- `18.04.2025_21.41.52_REC.mp4`: local walkthrough recording

## Tech stack

- Backend: Flask
- APIs: Spotify API, Verizon API
- Frontend: HTML, Bootstrap 5, JavaScript
- Config: `.env`-based credentials

## Setup

```bash
git clone https://github.com/abubakarshahid16/Spotify-Frontend-Clone.git
cd Spotify-Frontend-Clone
pip install -r requirements.txt
```

Create a `.env` file from `.env.example` and configure:

```text
SPOTIFY_CLIENT_ID=your-spotify-client-id
SPOTIFY_CLIENT_SECRET=your-spotify-client-secret
VERIZON_API_KEY=your-verizon-api-key
```

Run locally:

```bash
flask run
```

Then open:

```text
http://127.0.0.1:5000
```

## Development note

For testing without a live Verizon key:

```text
SIMULATE_VERIZON_SUCCESS=true
```

## Industrial positioning

A production-ready version of this idea would likely need:

- stronger auth and session handling
- retries and error recovery for API failures
- better state management across the multi-step flow
- audit logging for outbound sharing actions
- rate-limit awareness for external APIs
- a cleaner mobile-friendly product interface

That makes this repo more than a clone exercise. It is best understood as a **cross-platform media-sharing workflow prototype**.
