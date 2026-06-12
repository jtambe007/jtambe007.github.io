---
title: 'Automated Data Quality Validator (Saving 3.5+ Hours Per Audit)'
description: 'A configurable data validation app that scores CSV and Excel quality across five dimensions and exports a branded PDF report, turning a half-day manual audit into a 10-second automated check. Built to eliminate manual spreadsheet audits, allowing account teams to instantly validate messy, multi-source client data before it hits production dashboards.'
image:
    url: '/images/data-validator-scorecard.png'
    alt: 'Data Health Validator scorecard showing Grade D result'
worksImage1:
    url: '/images/data-validator-scorecard.png'
    alt: 'Scorecard with health score, grade, and null rate chart'
worksImage2:
    url: '/images/data-validator-pdf.png'
    alt: 'PDF report with failed checks and summary table'
platform: Streamlit
stack: 'Python, Streamlit, Pandas, Plotly, ReportLab, PyYAML'
github: https://github.com/jtambe007/streamlit-data-validation-starter-kit
---

A half-day manual data audit, replaced by a 10-second automated check with a client-ready PDF.

## The Problem

Analytics teams spend 30–50% of every project on data validation before any real work begins. Every engagement starts with the same thing: a client sends a CSV, and someone has to manually find the nulls, the duplicates, the columns that should be numeric but aren't, the outliers that will break a downstream model.

On fixed-price work, that time doesn't disappear. Instead, it comes out of margin.

The process is also inconsistent. Different team members catch different things. When there is no audit trail, there is nothing a client can sign off on.

## The Build

A Streamlit app that runs five validation checks against any uploaded CSV and produces a scored report in under 10 seconds.

**The five checks:**
- **Null rate** which flags columns exceeding a configurable threshold
- **Duplicates** which detects full-row or key-column violations
- **Type mismatches** which identifies values that fail numeric or date coercion
- **Outliers** which uses IQR or z-score depending on the domain
- **Schema drift** which compares column structure against a reference CSV

Results feed into a 0–100 health score with a letter grade. Errors deduct 5 points each and warnings deduct 1. The full findings export as a PDF in one click.

The app ships with three industry presets for Retail, Healthcare, and Finance, each with domain-appropriate thresholds. A missing patient DOB is a compliance issue (0.1% null tolerance). A high-revenue retail order probably isn't an error (IQR × 2.0). The same CSV, scored against different standards, produces different results.

**Demo:** upload a deliberately messy 503-row retail file, select the Retail profile, get Grade D / 69.92 — 3 duplicate order IDs, a region column at 25% nulls, two revenue outliers surfaced and explained.

**[Live App](https://data--validator.streamlit.app)**

## Tech Stack

Python · Streamlit · Pandas · Plotly · ReportLab · PyYAML

## Outcome

What used to be a manual half-day process now runs in under 10 seconds and produces a structured, repeatable output the team can act on directly or hand to a client as documentation.

**The business case is straightforward:** a $15k engagement that previously burned $5k on manual cleaning ships that $5k as margin, or as faster delivery that wins the next contract.

The pattern works for any team ingesting third-party data. The thresholds are configurable and the audit trail is automatic.