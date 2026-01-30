# Spotify Listening Behaviour Analysis

This project analyses my personal Spotify streaming history (2017-2025) to explore my listening habits.

## Motivation

Spotify is a streaming platform for songs, podcasts, and audiobooks, and is likely my most used app. So, I expected it to have an enormous amount of data that describes who I am in terms of my interest in music, which it does. Spotify provides me with a summary of my listening habits, through Spotify Wrapped and some bespoke playlists. But, my curiosity is not fixed to the small set of questions they answer. I wanted to further explore my streaming history to learn more about my listening behaviour. My initial questions for my data evolved and continue to evolve during exploration since I learn new things worth investigating. Currently, I have analysed the following, which all concern data in the years 2023, 2024, and 2025:

1. Top 10 Artists by Hours Played
2. Skip-rate of these Top 10 Artists
3. Total Track Click Count of Top 10 Artists
4. Individual Track Click Count for a given Top 10 Artist
5. Hours Played over Month Years for a given Top 10 Artist
6. Hours Played over days in a given Month for a given Top 10 Artist

## Data

The raw data comes from a download of my personal Spotify Extended Streaming History, which includes track information, and when and how I streamed content. Due to size, the full processed dataset is not included in this repository. Instead, a random sample of the dataset is provided in `data/processed/processed_data_sample.csv`.

### Data stages

- **Raw**: Original files as provided by Spotify, left unchanged. These files are not included in this repository due to privacy constraints.
- **Anonymised**: Raw data with sensitive fields removed.
- **Processed**: Cleaned and merged data, ready for analysis and visualisation on Tableau.

### Key characteristics

- Multiple JSON files per data export
- Streaming history spans from 2017 to 2026
- Sensitive fields (e.g., IP addresses) were removed before analysis
- Full processed dataset: ~200,000 rows
- Sample dataset: 1000 rows
    - Random sample of full processed dataset
    - Has the same schema and column names as the full processed dataset

For detailed field definitions, see `docs/schema.md`

## Tools

- Python (Pandas, Google Colaboratory)
- Tableau
- Google Drive for project organisation
- GitHub for showcasing results

## Project structure

```
spotify-data-analysis/
├── data/
│   ├── anonymised/                     # Anonymised raw JSON files
│   └── processed/
│       └── processed_data_sample.csv   # Sample of cleaned, Tableau-ready data
├── docs/
│   └── schema.md                       # Schema detailing key fields used in the processed dataset
├── notebooks/
│   ├── anonymise.ipynb                 # Anonymises the raw JSON files
│   └── data_preparation.ipynb          # Cleans data, fixes data types, and creates new columns
├── tableau/
│   └── Listening Habits.twb            # Data visualisations
├── LICENSE
└── README.md
```

## Analysis overview

1. Read data from JSON files into their own tables
2. Looked at column names and their data types to understand the raw data and ensure consistency between the tables
3. Anonymised the raw data by removing IP addresses
4. Removed any podcast episodes and audiobooks
5. Removed irrelevant columns
6. Converted data types
7. Vertically stacked the segmented tables
8. Created derived fields
9. Visualised the data in bar and line graphs using Tableau for interesting insights

## Notes/Limitations

- The Tableau workbook was run on the full dataset
