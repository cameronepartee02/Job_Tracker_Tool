# Job Posting Skill-Gap Analysis

*A data cleaning and normalization project that started as prep work and turned into something worth sharing.*

## The origin story

This wasn't planned as a standalone project. I was scoping out ideas for my second data portfolio piece and wanted to answer two practical questions for myself:

1. How does my current skillset actually stack up against the roles I'm targeting?
2. What should my next portfolio project focus on to close the biggest gaps?

To answer that, I pulled metadata from 16 LinkedIn job postings at my target companies (Accenture, Deloitte, IBM, ShopMy, Amazon, and Jump Trading) into a spreadsheet, then brought it into Python for cleaning. The exploratory work ended up being a solid demonstration of data wrangling on its own — so here it is.

## What's in this repo

- **`/raw`** — the original tracker, scraped directly from LinkedIn postings, unprocessed
- **`/processed`** — three analysis-ready tables built from the raw data:
  - `job_metadata_clean.csv` — one row per posting, with standardized salary ranges, seniority categories, location, industry, and benefits fields
  - `skills_long.csv` — one row per individual skill mention, exploded and categorized into Technical / Business Acumen / Soft Skills
  - `seniority_mix_long.csv` — one row per posting-level candidate seniority breakdown
- **`Job_Metadata_Analysis.ipynb`** — the full Python/pandas cleaning workflow

## The process

The raw data was messy in the usual ways: salary ranges bundled with RSU/sign-on bonus text, seniority levels described inconsistently across companies, skills listed as compound comma-separated strings, and location fields mixing city, state, and remote/hybrid notes. The notebook walks through:

- Parsing and splitting salary ranges into low/high bounds plus separate flags for equity, sign-on bonuses, and other compensation notes
- Standardizing seniority levels into consistent categories with mapped years-of-experience ranges
- Cleaning and simplifying location and work-arrangement fields
- Exploding multi-skill strings into individual rows and categorizing each into a skill bucket
- Parsing candidate seniority mix percentages into a clean long-format table
