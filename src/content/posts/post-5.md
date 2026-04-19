---
title: '9 ML Models in a Regulated Bank — What It Means for Your Project'
author: Jacobyne Tambe
date: '04-10-2025'
image:
    url: '/images/blog-post.webp'
    alt: 'Post Thumbnail'
---

Most freelancers who say "I build ML models" learned in Jupyter notebooks on Kaggle datasets. I built mine inside Bank of America.

That difference matters. Here is what two years of shipping production ML in a regulated, Fortune 50 environment taught me — and why it applies directly to any data project you bring to me.

## Lesson 1: Governance Is Not Overhead — It's Insurance

In a bank, every model that touches a customer decision needs an audit trail. Not as a checkbox — as a genuine requirement. Who trained it, when, on what data, with what validation results, approved by whom, and what the fallback behavior is if it fails.

Most freelancers skip this entirely. The result is models that work until they don't, and nobody knows why they broke or how to fix them without the original developer.

When I build for clients, every deliverable ships with documentation that isn't an afterthought: data lineage, model card, validation results, and a defined failure path. Your team can maintain it without calling me. That's not overengineering — that's professional work.

## Lesson 2: Fallback Paths Are What Separate Production Code from Prototype Code

A model without a fallback is a liability. When a data feed fails, when an input schema changes unexpectedly, when a prediction confidence drops below a threshold — what happens? In a bank, "undefined behavior" is not an acceptable answer.

Nine ML models means nine times I had to answer: what does the system do when this breaks? The habit of designing fallback paths before shipping is now automatic for me. It's the difference between code that works in a demo and code that works on a Friday afternoon when nobody is watching.

## Lesson 3: SMB Work Is Where Enterprise Discipline Earns Its Rate

Here's what I've noticed doing SMB and agency engagements: most clients have never received a data deliverable with real documentation, a clear failure path, or a handoff package that their team can actually use. They've received notebooks and dashboards that depend entirely on the freelancer who built them.

That's not a high bar to clear. But it's the bar most people don't clear.

When I apply enterprise documentation standards to a $5,000 sprint — not in a way that adds bureaucratic weight, but in a way that makes the output genuinely maintainable — clients notice. It's what makes them come back for retainer work rather than hunting for a new contractor every quarter.

---

The nine models I shipped at BofA were not remarkable for their algorithms. What made them work in production was discipline: clean data contracts, documented assumptions, fallback logic, and thorough review. Those habits don't turn off when I'm working outside a regulated environment.

If you're evaluating whether to bring me onto a project: this is what you're buying. Not just Python — production-grade Python.

*Based in Charlotte, NC. Available for project work and agency subcontracts. [Get in touch.](/)*
