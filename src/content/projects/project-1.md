---
title: 'Subscription Churn Playbook'
description: 'A churn prediction model bundled with a segmented retention playbook — ML output turned into a business action plan an executive can use on Monday.'
image:
    url: '/images/netflix-thumb.jpg'
    alt: 'Subscription Churn Playbook'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'SHAP feature importance chart'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Churn risk segmentation matrix'
platform: Jupyter Notebook
stack: 'Python, Pandas, scikit-learn, XGBoost, SHAP, Plotly, ReportLab'
github: https://github.com/jtambe007/netflix-cancellation-analysis
---

**A 0.87 AUC is not a business plan.**

Most churn portfolio projects stop at the model. Businesses don't know what to do with a confusion matrix. The gap between a model and an executable retention plan is exactly where consultants earn their rate — and closing that gap publicly is a rate-raising move.

## The Problem

Subscription businesses arrive with a recurring question: *who is about to leave, and what do we do about it?* Most ML solutions answer the first half. They hand back a score or a ranked list. Then the client asks "so what do we do?" and the project stalls.

The deliverable businesses actually need isn't the model — it's the playbook that tells each team what action to take for each customer segment.

## The Approach

Built on 500+ Netflix show records from the TMDB API, this project uses the churn/cancellation signal as a proxy for subscription disengagement. The model pipeline:

1. **Baseline** — logistic regression to establish an interpretable floor
2. **Champion model** — XGBoost with cross-validated hyperparameter tuning
3. **Interpretability layer** — SHAP values to expose which features drive each prediction at the individual level, not just globally

The key addition over a standard churn model: **risk-LTV segmentation**. Users (or shows) are binned by predicted churn probability crossed with estimated lifetime value. Each quadrant maps to a specific retention tactic:

- **High risk, high LTV** → white-glove outreach, price protection offer
- **High risk, low LTV** → automated win-back email, feature activation nudge
- **Low risk, high LTV** → loyalty reward, upsell window
- **Low risk, low LTV** → no intervention (protect margin)

Output includes a one-page executive summary PDF — the segmented playbook an executive can action Monday morning, not a notebook they'll never open.

## Tech Stack

Python · Pandas · scikit-learn · XGBoost · SHAP · Plotly · ReportLab (PDF export)

## Outcome

Model achieves 87% AUC. More importantly, every prediction maps to a segmented action — not just a score. The pattern (Model + Playbook) is how every ML deliverable should ship.

> *This project uses TMDB data but is not endorsed or certified by TMDB.*
