# A&R Analyst Portfolio Project

Analyzing 60 years of Billboard Hot 100 chart data and Spotify audio features to understand what characterizes commercial hit songs — and how those characteristics have evolved over time. Built as a demonstration of data-driven A&R scouting methodology.

## Overview

This project explores whether audio characteristics (danceability, energy, tempo, valence) meaningfully differentiate hit songs from lower-charting ones, and how that relationship has changed across decades. The analysis reveals that while audio traits once served as a meaningful signal of hit potential, that differentiation has weakened significantly in the streaming era — motivating a shift toward momentum-based scouting signals (in progress, see Roadmap below).

## Key Findings

- Danceability's role in separating Top 10 hits from lower-charting songs has shrunk from a 0.067 gap in the 2000s to just 0.005 in the 2020s
- Valence (musical positivity) dropped notably after the 2000s and has remained lower since, reflecting a broader shift toward moodier mainstream production
- Static audio characteristics alone are no longer sufficient to predict hit potential — modern scouting requires momentum and playlist-placement signals

## Tech Stack

- **Python** (pandas, numpy) — data cleaning and analysis
- **SQL** (SQLite via SQLAlchemy) — structured querying
- **Jupyter Notebook** — analysis and documentation
- **Kaggle API** — historical Billboard Hot 100 + Spotify audio feature dataset

## Project Structure
ar-analyst-project/
├── 01_billboard-hot-100.ipynb   # Main analysis notebook
├── data/                         # Generated datasets (not tracked in Git)
├── requirements.txt              # Python dependencies
└── README.md

## How to Run

1. Clone this repo
2. Create a virtual environment and install dependencies: `pip install -r requirements.txt`
3. Set up Kaggle API credentials (see [Kaggle API docs](https://www.kaggle.com/docs/api))
4. Open `01_billboard-hot-100.ipynb` and run all cells

## Roadmap

- [ ] Part 2: Live Spotify data pull for emerging artist scouting
- [ ] Part 3: Hit-potential scoring model
- [ ] Part 4: Interactive dashboard

## Author

Manav Desai