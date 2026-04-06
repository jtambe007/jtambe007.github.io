---
title: 'Spotify Music Trends Analysis'
description: 'Exploring what makes songs trend on Spotify — analyzing audio features, release timing, and playlist placement patterns across 10,000+ tracks'
tags: ["Python", "Spotify API", "Pandas", "Seaborn", "Data Analysis"]
image:
    url: '/images/GitHub.webp'
    alt: 'Music data visualization'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Audio features correlation heatmap'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Trending tracks by release day and genre'
platform: Jupyter Notebook
stack: 'Python, Spotipy, Pandas, Matplotlib/Seaborn'
website: https://jtambe007.github.io
github: https://github.com/jtambe007
---

This project uses the Spotify Web API to analyze audio features and metadata across 10,000+ tracks to identify patterns that correlate with chart performance and playlist placement.

**Objectives**
- Identify which audio features (energy, danceability, valence, tempo) correlate with trending performance
- Analyze release timing patterns across genres — does day of week or season matter?
- Compare independently released tracks vs. label-backed tracks
- Visualize feature clusters to find "hit formulas" by genre

**Key Findings**

The analysis revealed that tracks added to editorial playlists within the first 48 hours of release have significantly higher streaming velocity than those added later — regardless of audio features. Timing and playlist access appear to be stronger predictors of trending performance than the music itself.

Across pop and hip-hop genres, danceability and energy together explained roughly 40% of variance in 30-day streaming totals. Acoustic and indie genres showed much weaker correlations, suggesting those audiences respond to different signals.

**Methodology**

Data was collected via the Spotipy Python library, pulling track audio features, artist metadata, and chart history. Playlist data was supplemented with manual lookups for editorial playlist inclusion dates.
