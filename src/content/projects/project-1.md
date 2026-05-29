---
title: 'Streamlit QA Validation App'
description: 'A change request validation tool that eliminated a manual rework cycle. A process the team had accepted as permanent, eliminated. 20 hours saved per release cycle.'
image:
    url: '/images/laptop.webp'
    alt: 'Streamlit QA Validation App'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Validation dashboard with color-coded findings by severity'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Before/after comparison report output'
platform: Streamlit
stack: 'Python, Streamlit, Pandas, Plotly, YAML, ReportLab'
github: https://github.com/jtambe007
---

A process the team had accepted as permanent, eliminated. 20 hours saved per release cycle.

## The Problem

In a regulated data environment, every model change goes through a change request process — a structured review that ensures production systems behave exactly as documented. The QA validation step in that process was entirely manual: a team member would compare the incoming change against the existing system state, flag discrepancies, and log findings by hand.

This wasn't a one-off task. It happened every release cycle. The manual nature meant:

- Findings were inconsistent depending on who ran the check
- Errors were sometimes caught late, triggering rework after review had already closed
- The process consumed an entire afternoon per cycle, reliably

The team had accepted this as structural overhead. It wasn't.

## The Build

A Streamlit app that automates the validation step end-to-end. The tool ingests the change request documentation and the current system state, runs a configurable suite of checks, and outputs a structured findings report — color-coded by severity, with a PDF export for the audit trail.

The rule set is **YAML-configurable**, so the checks can be updated without touching Python code. New validation requirements get added in a config file, not a deployment.

Key checks:
- **Schema drift detection** — flags any column added, removed, or renamed against the documented spec
- **Threshold validation** — ensures value ranges match approved bounds
- **Null and completeness checks** — column-level missing rate against configured tolerances
- **Cross-field consistency** — validates relationships between fields that should move together

Outputs a color-coded scorecard, a summary of findings by severity, and an exportable PDF report formatted for the review record.

## Tech Stack

Python · Streamlit · Pandas · Plotly · YAML configuration · ReportLab (PDF export)

## Outcome

The manual afternoon is gone. The tool runs the full validation suite in under two minutes and produces a report the review team can act on directly — no interpretation required, no inconsistency between runs.

**20 hours saved per release cycle.** The tool is still running.

The more durable outcome: the validation step is now auditable. Every run produces the same format, logged with a timestamp. That consistency matters in a regulated environment where the question isn't just "did it pass" but "how do we know it passed."
