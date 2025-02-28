# Daily Pennsylvanian Opinion Scraper

This script scrapes the main headline from the *Opinion* section of *The Daily Pennsylvanian* website and saves it in a JSON file to track headlines over time. It logs each run and handles errors gracefully.

## Features

- Scrapes the main headline from *The Daily Pennsylvanian* Opinion section.
- Uses an `h3` tag with class `standard-link` instead of an `a` tag and the frontpage-link.
- Logs requests and responses for debugging.
- Saves extracted headlines in a JSON file for historical tracking.
- The script targets the *Opinion* section (`https://www.thedp.com/section/opinion`) instead of the main page.

## Usage

Run the scraper with:

```sh
python scraper.py
```

The script will log each run and store the latest scraped headline in `data/daily_pennsylvanian_headlines.json`.

## Logging

The scraper uses `loguru` for structured logging. Logs are saved in `scrape.log` and include request details, errors, and data extraction results.

## Notes

- The scraper respects `robots.txt`, so ensure compliance with website policies.
- If the website structure changes, update the HTML parsing logic accordingly.
- The scraper depends on `daily_event_monitor` for JSON data handling; ensure it's available.

## Cron Syntax

The initial cron expression `0 20 * * *` means the workflow runs every day at exactly 8:00 PM UTC. 0 → At the 0th minute  20 → At the 20th hour `*` → Any day of the month `*` → Any month `*` → Any day of the week
