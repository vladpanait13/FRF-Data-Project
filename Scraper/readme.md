# Transfermarkt Player Data Scraper

A Python scraper to extract player information from Transfermarkt.com squad pages for Romanian League teams.

## What it does

Scrapes player data from 16 Romanian league team pages and exports to CSV with:

- Player Name (without diacritics)

- Age (extracted from birth date)

- Height

- Preferred Foot (Right/Left/Both)

## Prerequisites

`pip install requests beautifulsoup4 pandas`

## Usage 

### Google Colab

1. Install dependencies:

   `!pip install requests beautifulsoup4 pandas`
   
3. Copy and run the script
   
4. CSV file will be automatically generated with timestamp

### Local Python

`python transfermarkt_scraper.py`

## Features

- Rate Limiting: 8-15 second delays between requests

- Timeout Protection: 30-second timeout with progressive retry delays

- Diacritic Removal: Converts "Ștefan" to "Stefan" automatically

- Progress Tracking: Shows scraping progress and team summaries

## Teams Covered

All 16 Romanian League teams including FCSB, CFR Cluj, Rapid, Dinamo, Universitatea Craiova, and others.

## Output

Creates CSV file: 

`transfermarkt_players.csv`

Example output:

`Player,Age,Height,Foot

Stefan Tarnovanu,24,1.90m,Right

Florinel Coman,26,1.80m,Right

Razvan Marin,28,1.82m,Right`

## Error Handling

- 503 Errors: Waits 20 seconds before retry

- Timeouts: Progressive delays (15-35 seconds)

- Missing Data: Uses "N/A" for unavailable information

## Notes

- Respectful scraping with proper delays

- Handles Transfermarkt's anti-bot measures

- Works with current Transfermarkt page structure (2024/25 season)

- Total execution time: ~5 minutes for all teams

