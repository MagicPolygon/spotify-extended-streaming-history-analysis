# Spotify Listening Behaviour Analysis

This project analyses my personal Spotify streaming history (2017-2025) to explore my listening habits.

## Motivation

Spotify is a streaming platform for songs, podcasts, and audiobooks, and is likely my most used app. So, I expected it to have an enormous amount of data that describes who I am in terms of my interest in music, which it does. Spotify provides me with a summary of my listening habits, through Spotify Wrapped and some bespoke playlists. But, my curiosity is not fixed to the small set of questions they answer. I wanted to further explore my streaming history to learn more about my listening behaviour. My initial quesions for my data evolved and continue to evolve during exploration since I learn new things worth investigating. Currently, I have analysed the following, which all concern data in the years 2023, 2024, and 2025:

1. Top 10 Artists by Hours Played
2. Skip-rate of these Top 10 Artists
3. Total Track Click Count of Top 10 Artists
4. Individual Track Click Count for a given Top 10 Artist
5. Hours Played over Month Years for a given Top 10 Artist
6. Hours Played over days in a given Month for a given Top 10 Artist

## Data

The raw data comes from a download of my personal Spotify Extended Streaming History, which includes track information, and when and how I streamed content.

The data moves through stages during the project:

- **Raw**: Original files as provided by Spotify, left unchanged. These files are not included in this repository.
- **Anonymised**: Raw data with sensitive fields removed.
- **Processed**: Cleaned and merged data, ready for analysis and visualisation on Tableau.

Key characteristics:

- Multiple JSON files per data expoert
- Streaming history spans from 2017 to 2026
- Sensitive fields (e.g., IP addresses) were removed before analysis

For detailed field definitions, see `docs/schema.md`
