---
title: 'Data Validation Streamlit App'
description: 'A reusable Streamlit app that catches data-quality errors before they hit production — drop it into any agency client workflow in an afternoon.'
image:
    url: '/images/GitHub.webp'
    alt: 'Data Validation Streamlit App'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Data health scorecard with color-coded findings'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Outlier distribution charts and schema drift report'
platform: Streamlit Community Cloud
stack: 'Python, Streamlit, Pandas, Plotly, YAML, ReportLab'
website: https://jtambe007.github.io
github: https://github.com/jtambe007
---

Upload any CSV. Get a data-health report in 30 seconds. Catches the top-10 most common issues. Configurable for a client's domain in an afternoon.

## The Problem

Clients ship messy CSVs and exports into dashboards constantly. Nulls, duplicates, schema drift, encoding errors, outliers — every project starts with the same painful cleanup cycle that consumes 30–50% of project time.

Most freelancers tell agencies *"I can clean your data."* A prebuilt, configurable tool that already does it is a fundamentally different sales position: faster delivery, more professional result, lower agency cost per project.

## The Approach

A hosted Streamlit app that accepts a CSV upload and runs a configurable suite of checks:

- **Null analysis** — column-level missing rate with threshold flags
- **Duplicate detection** — exact and near-duplicate rows
- **Type mismatches** — values that don't match declared or inferred schema
- **Outlier detection** — both IQR and z-score methods, configurable sensitivity
- **Schema drift** — comparison against a reference file to flag added, removed, or renamed columns

The rule set is **YAML-configurable** — an agency plugs in a client-specific config file and the app runs their validation profile without touching Python. Outputs a color-coded scorecard, charted distributions, and an exportable PDF report.

Hosted on Streamlit Community Cloud (free tier) so the demo is always live.

## Tech Stack

Python · Streamlit · Pandas · Plotly · YAML configuration · ReportLab (PDF export) · Streamlit Community Cloud

## Deliverables

- Live hosted app with public demo URL
- GitHub repo with README, architecture diagram, and sample YAML configs for retail, healthcare, and finance verticals
- One sample PDF report using a public messy dataset
- 2-minute Loom walkthrough: messy CSV in, full health report out

## Outcome

Any analytics agency can drop this into a client workflow on day one of a project. The validation step that used to take a half-day now takes 30 seconds and produces a client-ready report.
