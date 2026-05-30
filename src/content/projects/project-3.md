---
title: 'Show Survival Playbook'
description: 'A cancellation prediction model for streaming content with an ML output turned into a segmented renewal decision framework a studio executive can act on.'
image:
    url: '/images/netflix-thumb.jpg'
    alt: 'Show Survival Playbook'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'SHAP feature importance chart'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Churn risk segmentation matrix'
platform: Jupyter Notebook
stack: 'Python, Pandas, scikit-learn, XGBoost, SHAP, Plotly'
github: https://github.com/jtambe007/netflix-cancellation-analysis
---

**An 0.871 AUC is not a renewal decision.**

Most churn projects stop at the model but studios don't know what to do with a confusion matrix. The gap between a cancellation score and an executable content strategy is exactly where consultants earn their rate and closing that gap publicly is a rate-raising move.


## The Problem

Streaming platforms face a recurring content question: *which shows are about to fail, and what do we do about each one?* Most ML solutions answer the first half. They return a ranked list of at-risk titles. Then the programming team asks *"so what do we greenlight, protect, or cut?"* and the project stalls.

The deliverable studios actually need isn't a model but a playbook that maps each title to a portfolio action.



## The Approach

Built on nearly 1,500 show records via the TMDB API, this project uses cancellation status as the prediction target. The model pipeline:


1. **Baseline**:  logistic regression to establish an interpretable floor (AUC 0.847)
2. **Champion model**: XGBoost with class-imbalance weighting (AUC 0.871, F1 0.58 on canceled class)
3. **Interpretability layer**: SHAP values to expose which features drive each prediction at the individual show level

The key addition over a standard classification model: **risk × engagement segmentation**. Every show is binned by predicted cancellation probability crossed with an engagement proxy (vote count + popularity + seasons). Each of the five quadrants maps to a specific portfolio action:

- **Low risk, High engagement → Green-light**: anchor title, protect and expand
- **Low risk, Low engagement → Renew Cautiously**: monitor; hold budget flat
- **Medium risk, either → Renew Cautiously**: watchlist; leave intervention window open
- **High risk, High engagement → Harvest and End**: strong finale, merchandising, spin-off evaluation
- **High risk, Low engagement → Sunset**: orderly wind-down, no renewal

*Note*: engagement is a composite proxy (vote count, popularity, seasons) and is labeled as such throughout. This is because this public dataset is at the show-level and not the subscriber-level.

The output includes a one-page portfolio playbook designed for an executive audience with a content action matrix that someone can walk into a greenlight meeting with, not a notebook they'll never open.

## Tech Stack

Python · Pandas · scikit-learn · XGBoost · SHAP · Plotly

## Outcome

Model achieves a 87.1% AUC. More importantly, every prediction maps to a portfolio segment with a named action and not just a probability. This pattern (Model + Playbook) is how every ML deliverable should ship.


> *This project uses TMDB data but is not endorsed or certified by TMDB.*