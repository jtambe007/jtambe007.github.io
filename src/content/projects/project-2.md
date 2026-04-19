---
title: 'Cameroon Public Data Pipeline'
description: 'End-to-end ETL from raw government source to live public dashboard — a reproducible pipeline pattern for any mid-market data consolidation engagement.'
image:
    url: '/images/laptop.webp'
    alt: 'Cameroon Public Data Pipeline'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Pipeline architecture diagram'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Live Streamlit dashboard with Cameroon trade indicators'
platform: Streamlit Community Cloud + GitHub Actions
stack: 'Python, Pandas, SQLite, Streamlit, GitHub Actions, BeautifulSoup'
github: https://github.com/jtambe007
---

One command from raw government CSV to live dashboard, updated weekly. This is the exact pattern I'd apply to your client's data consolidation project — swap the source, keep the skeleton.

## The Problem

Mid-market clients arrive with data scattered across five or more sources: spreadsheets, legacy databases, API exports, PDFs, and inconsistent CSVs with no schema and no documentation. Nobody has integrated it.

The deliverable an agency actually needs isn't the dashboard — it's the **pipeline pattern**: a reproducible, documented skeleton that ingests messy source data, cleans it reliably, stores it, and serves it. This project is proof I can ship that pattern end-to-end, without an engineering team behind me.

## The Approach

Using Cameroon government trade and economic indicators as the source data — real-world messy, inconsistent formats, encoding issues, broken URLs — the pipeline covers every stage:

1. **Ingest** — scrape or download from public government data URL
2. **Clean and normalize** — handle encoding errors, inconsistent date formats, missing values, and column name drift across annual releases
3. **Store** — load into SQLite (zero-infrastructure, version-controlled alongside code)
4. **Serve** — Streamlit dashboard with 2–3 views (trend lines, regional breakdown, year-over-year comparisons)
5. **Automate** — GitHub Action scheduled to re-run weekly, keeping the dashboard live without manual intervention

One-command rerun: `python pipeline.py` ingests, cleans, stores, and the dashboard picks up the updated data on next load.

Architecture diagram documents every deliberate scope decision so any engineer can extend or adapt it.

## Tech Stack

Python · Pandas · requests / BeautifulSoup · SQLite · Streamlit · GitHub Actions · Excalidraw (architecture diagram)

## Deliverables

- Public GitHub repo with one-command rerun script and full README
- Live dashboard on Streamlit Community Cloud, updated weekly via GitHub Actions
- Architecture diagram embedded in the case study
- 90-second Loom walking through one rerun cycle

## Outcome

The real signal is not Cameroon — it's *I can go from raw, ugly, untrusted data all the way to a live, auto-refreshing dashboard, by myself, repeatably.* This pattern scales to any multi-source client project. Swap the source, keep the skeleton.
