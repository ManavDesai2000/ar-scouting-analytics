# A&R Analyst Portfolio Project

Analyzing 60 years of Billboard Hot 100 chart data and Spotify audio features to understand what characterizes commercial hit songs — and how those characteristics have evolved over time. Built as a demonstration of data-driven A&R scouting methodology.

## Overview

This project explores whether audio characteristics (danceability, energy, tempo, valence) meaningfully differentiate hit songs from lower-charting ones, and how that relationship has changed across decades. Part 1 reveals that while audio traits once served as a meaningful signal of hit potential, that differentiation has weakened significantly in the streaming era. Part 2 builds on this by using live momentum signals — Spotify search combined with Last.fm listener/engagement data — to identify emerging artists worth scouting today.


## Key Findings

**Part 1 — Historical Analysis:**
- Danceability's role in separating Top 10 hits from lower-charting songs has shrunk from a 0.067 gap in the 2000s to just 0.005 in the 2020s
- Valence (musical positivity) dropped notably after the 2000s and has remained lower since, reflecting a broader shift toward moodier mainstream production
- Static audio characteristics alone are no longer sufficient to predict hit potential — modern scouting requires momentum and playlist-placement signals

**Part 2 — Live Momentum Analysis:**
- Spotify's Developer API restricts popularity, follower, and genre data for standard developer access (as of 2026) — this project adapted by integrating Last.fm as a substitute momentum data source
- Classified 33 current artists across 8 genres into Established (15) / Emerging (13) / Early-Stage (5) tiers based on Last.fm listener counts
- Identified an engagement-ratio signal (plays per listener) that surfaces high-loyalty artists — e.g., an Emerging-tier artist outperforming several Established acts in fan engagement despite a smaller audience

**Part 3 — Scoring Model:**
- Built a weighted Scouting Score (60% engagement / 40% reach) to rank Emerging-tier artists
- Top recommendation: Motionless In White, ranking #1 on both audience reach and fan engagement — a result that held up after expanding the artist pool from 7 to 13
- Demonstrated that raw popularity and the weighted score produce different rankings — e.g., HUGEL, despite the 3rd-highest listener count in its tier, dropped to 4th once engagement was factored in
- Added an Early-Stage Watchlist (5 artists, under 100K listeners) tracked separately from the main model due to smaller sample sizes; honestav stands out with engagement comparable to established Emerging-tier artists

## Tech Stack

- **Python** (pandas, numpy) — data cleaning and analysis
- **SQL** (SQLite via SQLAlchemy) — structured querying
- **Jupyter Notebook** — analysis and documentation
- **Kaggle API** — historical Billboard Hot 100 + Spotify audio feature dataset
- **Spotify API** (spotipy) — live track/artist discovery
- **Last.fm API** — artist momentum signals (listener counts, play counts)

## Project Structure

```
ar-analyst-project/
├── 01_billboard-hot-100.ipynb      # Part 1: Historical hit analysis
├── 02_live_spotify_data.ipynb      # Part 2: Live emerging artist scouting
├── 03_scoring_model.ipynb          # Part 3: Combined scoring model
├── data/                            # Generated datasets (not tracked in Git)
├── requirements.txt                 # Python dependencies
└── README.md
```

## How to Run

1. Clone this repo
2. Create a virtual environment and install dependencies: `pip install -r requirements.txt`
3. Set up API credentials:
   - **Kaggle**: create an API token (see [Kaggle API docs](https://www.kaggle.com/docs/api)) and place `kaggle.json` in `~/.kaggle/`
   - **Spotify**: create a developer app at [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard) to get a Client ID and Client Secret
   - **Last.fm**: create an API account at [last.fm/api/account/create](https://www.last.fm/api/account/create) to get an API key
4. Create a `.env` file in the project root with:
```
   SPOTIFY_CLIENT_ID=your_client_id
   SPOTIFY_CLIENT_SECRET=your_client_secret
   LASTFM_API_KEY=your_api_key
```
5. Run the notebooks in order:
   - `01_billboard-hot-100.ipynb` — historical hit analysis
   - `02_live_spotify_data.ipynb` — live emerging artist scouting
   - `03_scoring_model.ipynb` — combined scoring model (requires Part 2's output CSV)

## Data Source

- [Billboard Hot 100 + Audio Features](https://www.kaggle.com/datasets/thedevastator/billboard-hot-100-audio-features) — historical chart data (1965–present) combined with Spotify audio features, sourced from Kaggle

## Roadmap

- [x] Part 1: Historical hit analysis
- [x] Part 2: Live Spotify + Last.fm emerging artist scouting
- [x] Part 3: Combined hit-potential scoring model
- [ ] Part 4: Interactive dashboard

## Author

Manav Desai