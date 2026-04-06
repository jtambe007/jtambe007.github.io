---
title: 'Learning Astro as a Data Person: What Surprised Me'
author: Jacobyne Tambe
date: '03-20-2025'
image:
    url: '/.netlify/images?url=/images/blog-post.webp'
    alt: 'Post Thumbnail'
---

I built this portfolio with Astro. I want to talk about what that was like coming from a data background with no traditional frontend background.

## Why Astro

I needed a portfolio site. I had two constraints: I didn't want to write a lot of JavaScript, and I wanted to write content in Markdown (which I already do for documentation and notes).

Astro fits both. It ships minimal JavaScript by default, and its content collections make Markdown a first-class citizen. The mental model clicked quickly for someone used to thinking in data pipelines!

## What Came Easily

The component model felt familiar. A `.astro` file has a frontmatter section (JavaScript/TypeScript) and a template section (HTML-ish). If you've written Python scripts that output HTML or reports, the separation of "compute here, render here" is already in your head.

Content collections where you define a schema for your Markdown files and Astro validates it felt like defining a DataFrame schema. Exact same concept: here are the fields, here are their types, here's what's required.

## What Took Adjustment

Styling. I've written CSS before but not seriously, and the gap between "it works" and "it looks intuitive" is wider than I expected. I spent a lot of time on spacing, color variables, and responsive breakpoints.

Also: understanding the difference between static rendering, server rendering, and client-side hydration in Astro. For this portfolio, I don't need any of that complexity — everything is static. But knowing why you're choosing static takes a minute to internalize.

## What I'd Tell Other Data People

If you've been putting off building a portfolio site because web development feels like a foreign language: Astro is a reasonable on-ramp. The learning curve is real but it doesn't require months of JavaScript before you can build something useful.

Start with the official Astro tutorial. It's legitimately good. Then pick a template close to what you want and modify it rather than starting from scratch.

You already know how to read documentation, debug with a search engine, and iterate on something until it works. That's most of what building a website requires.
