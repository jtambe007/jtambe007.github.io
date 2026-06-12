---
title: 'Predictive Churn & Content Spend Optimization Playbook'
description: 'A predictive renewal framework designed to help media and strategy agencies forecast asset longevity and optimize client ad spend allocation across fluctuating digital portfolios. Built to close the gap between model output and business decision.'
image:
    url: '/images/netflix-thumb.jpg'
    alt: 'Netflix Show Survival Analysis'
worksImage1:
    url: '/images/netflix-matrix.png'
    alt: 'Content Portfolio Playbook matrix with five portfolio actions mapped by risk and engagement'
worksImage2:
    url: '/images/netflix-shap.png'
    alt: 'SHAP feature importance of top cancellation risk drivers'
platform: 'Jupyter / ReportLab'
stack: 'Python · Pandas · scikit-learn · XGBoost · SHAP · Matplotlib · ReportLab'
github: 'https://github.com/jtambe007/netflix-cancellation-analysis'
---

**A model performance metric is not a business plan.**

Most machine learning projects stop at the model but that leaves a gap between a cancellation score and an executable content strategy.


## The Problem

Streaming platforms face a recurring content question: *which shows are about to fail, and what do we do about each one?*. 

The deliverable that studios actually need isn't a model but a playbook that maps each title to a portfolio action.

Comparing cancelled vs. non-cancelled shows for nearly 1,500 shows revealed four patterns that shaped the entire model:

- **Quality barely matters.** Cancelled shows rated 1.8% lower which was statistically real but practically meaningless.
- **Volume signals survival.** Cancelled shows had 39% fewer episodes with 18.3% fewer seasons and 16.4% lower popularity.
- **Age predicts cancellation.** Canceled shows are 22% older on average which was not surprising, since  older shows are more likely to have been canceled.
- **Genre count predicts nothing.** It had a 0% difference across both groups and was dropped from the model.
- **Genre-level analysis added texture.** Sci-Fi & Fantasy shows (22.7%) and Comedy shows (21.8%) are cancelled most. Documentaries (4.4%) are cancelled least.

## The Approach

Built on nearly 1,500 show records via the TMDB API, this project uses cancellation status as the prediction target. Two models were built and compared.


1. **Logistic Regression was more aggressive:** It caught more cancellations (81% recall) but raised nearly twice as many false alarms (37% precision). It assumed a linear relationship between features and risk.
2. **XGBoost found non-linear thresholds automatically and captured feature interactions:** It recognized that a show being recent AND having low episode count matters more than either factor alone. This produced better-calibrated probabilities, which is critical for the segmentation layer that follows.


**The Champion model is XGBoost.** ROC-AUC 0.871 · Precision 0.53 · Recall 0.65. Not because the numbers win in isolation, but because the goal was a probability score that places every show on a risk spectrum.

## What the Model Found

SHAP analysis answered a specific question: for a single show's prediction, how much did each feature push the probability up or down from the 14.4% baseline?

The top predictor was not episode count, popularity, or ratings.

**It was whether the show was a miniseries.** Format outranked volume and with shorter, self-contained runs, miniseries either ended as planned or got cut before completing their arc. 

English-language shows also appeared in the top 5, encoding something real about how Netflix evaluates shows differently across its international portfolio.

**The highest-risk show in the dataset was The Crew.** The model assigned it a 96.9% cancellation probability. It was correct as Netflix cancelled The Crew in May 2021 after one season. The model never saw the show's name or reviews. It only saw a single-season comedy with 10 episodes and low engagement across every dimension. Every feature pushed the score toward certainty.

## The Playbook Layer

Risk scores alone are not a decision framework.

The key addition over a standard classification model is **the risk × engagement segmentation**. 

**The cancellation risk** is the XGBoost probability (0–1).

**Engagement** is a normalized proxy built from vote count, popularity, and number of seasons and is labeled as such throughout. This is because this public dataset is at the show-level and not the subscriber-level. It contains three dimensions of audience health: historical depth, current breadth, and sustained platform investment.


Unique combinations of these two signals map to a specific portfolio action:

- **Low risk and High engagement → Green-light** Expand budget and order the next season. *ex. Stranger Things.*
- **Medium risk and High engagement → Renew Aggressively** The audience is real but the risk signal says not to wait. *ex. Arcane.*
- **Low or Medium risk and Low engagement → Renew Cautiously** Shows here are stable but unproven. Tighten the budget and KPIs.
- **High risk and High engagement → Harvest-and-End** There is a genuine audience but the show is running out of runway. Conclude the story intentionally. *ex. Alice in Borderland.*
- **High risk and Low engagement → Sunset** There is no meaningful audience signal. Do not renew. *ex. The Waterfront.*

529 shows landed in Green-Light, 98 got flagged for Sunset and 148 in Harvest-and-End.

The output includes a one-page portfolio playbook designed for an executive audience with a content action matrix that can be the starting point for a conversation a content team can have Monday morning.

## Tech Stack

Python · Pandas · scikit-learn · XGBoost · SHAP · Matplotlib · ReportLab

## The Closing Argument

Stopping at the model leaves a gap between output and decision. That gap is where this project focused.

The model achieved a 87.1% AUC. More importantly, every prediction maps to a portfolio segment with a named action and not just a probability.

**Model + Playbook is how every Machine Learning deliverable should ship.** The model answers which shows are at risk and the playbook answers what to do about it.

The analyst delivers the AUC. The consultant delivers the framework that makes the AUC useful. The data doesn't make the decision. It makes the decision easier to defend.


> *This project uses TMDB data but is not endorsed or certified by TMDB.*