---
title: 'Employee Retention Survival Analysis'
description: 'Kaplan-Meier and Cox regression applied to HR attrition data — time-to-churn modeling that gives HR teams the when, not just the who.'
image:
    url: '/images/laptop.webp'
    alt: 'Employee Retention Survival Analysis'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Kaplan-Meier survival curves by department'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Cox regression hazard ratios with confidence intervals'
platform: Jupyter Notebook + Streamlit
stack: 'Python, Pandas, lifelines, Plotly, Streamlit, scikit-learn'
github: https://github.com/jtambe007
---

<!-- TODO: Replace placeholder images with real screenshots before launch -->

Most attrition models tell you *who* is likely to leave. This one tells you *when* — and which factors accelerate the clock.

## The Problem

Standard classification models (logistic regression, random forest) predict whether an employee will leave. They don't capture time. An HR team needs to know: of the employees flagged at risk, who is leaving in 30 days versus 18 months? The intervention for each is completely different.

Survival analysis is the right tool for this question and it's underused in HR analytics precisely because most data practitioners don't know it.

## The Approach

Applied survival analysis methods to the IBM HR Attrition dataset (1,470 employees, 35 features):

1. **Kaplan-Meier curves** — non-parametric survival estimates by department, job role, and tenure band; visual answer to "what does attrition look like over time for each group?"
2. **Log-rank tests** — statistical validation that survival curves differ meaningfully across groups (not just noise)
3. **Cox Proportional Hazards model** — multivariate regression producing hazard ratios: which factors (overtime, salary band, manager tenure) independently accelerate departure risk
4. **Segment prioritization** — employees ranked by 90-day risk score, mapped to intervention tier (manager conversation, compensation review, exit risk flag)

## Tech Stack

Python · Pandas · lifelines (Kaplan-Meier, Cox PH) · Plotly · Streamlit · scikit-learn

## Deliverables

- Jupyter notebook with full analysis and annotated outputs
- Streamlit dashboard: upload any HR CSV, get survival curves and ranked risk list
- One-page executive summary: top 3 findings and recommended interventions
- GitHub repo with README and sample dataset

## Outcome

<!-- TODO: Update with real model metrics once complete -->

Cox model identifies overtime and low salary band as the two strongest predictors of 90-day departure (hazard ratios TBD on final dataset). The Streamlit dashboard lets an HR generalist run the analysis without touching Python.
