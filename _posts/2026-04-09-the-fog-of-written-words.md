---
layout: blog-post
title: "The Fog of Written Words"
date: 2026-04-09
categories: [data, botswana, fuel]
medium_url: "https://medium.com/@samuelkabelo1/the-fog-of-written-words-ba0ed0f0f9e7"
thumbnail: "/assets/images/leokwane.png"
excerpt: "Why 65 million liters is an abstraction, but a dashboard is intuition."
---

![BERA Press Release](https://miro.medium.com/v2/resize:fit:640/format:webp/1*BYOGHnZ_zvp7z5IlcIypPA.png)
<!-- ![Logo of my app ](/assets/images/leokwane.png) -->

When the government tells you there are 65 million liters of fuel and 20.8 days of cover, they are speaking the language of those in the inner sanctum. I saw a story to be told.

## Why this matters

To the average citizen, this is an abstraction and loses its meaning. Botswana does not drill or refine fuel. Every litre comes across borders, subject to geopolitical wobbles we can't control. Batswana only discover fuel price changes when they pull up to the pump or with impromptu press releases and by then, it's too late to budget, too late to adjust.

The 65 million forces the brain to perform "cognitive gymnastics." You must read the number, hold it in your working memory, find the second number (the daily consumption rate, which isn't even in the text), and perform a mental division to realize that 20.8 days isn't "nearly three weeks"; it is a razor-thin margin between a functioning economy and a stationary one.

In the absence of a visual trend, "38%" is just a digit. But in a simulation, that 38% is the angle of a slope, a steep, daunting climb that tells your gut exactly what your wallet is about to feel.

The reason why I created this dashboard was so that I could give a perspective that press releases do not give. A dashboard doesn't just "show" data; it translates statistics into intuition. When you see a gauge dipping into a red sector, or a 3D graph showing the "Supply Chain" of the Middle East constricting, you don't need a PhD in Economics to understand the gravity of the situation. You see the system.

## The Architecture

For flexibility, I chose the below even though Streamlit gave me challenges I found workarounds:

1. **FastAPI** handles the logic: simulation calculations, price triage formulas, data validation.
2. **Streamlit** renders the interface: gauges, charts, interactive sliders.
3. **JSON** for storing historical data for trend analysis.
4. **Docker** for packaging and Render for a simple push-to-deploy workflow.

### FASTAPI: The Gotchas
I wanted custom gauges matching the Tailwind design. Streamlit's `st.markdown(…, unsafe_allow_html=True)` works until quotes break your f-strings. Nested quotes in f-strings + HTML = SyntaxError hell. This was before finding out there is `st.html()` 🤣.

### The Socio-Economic Layer
I didn't stop at supply numbers. A P8.77 diesel increase doesn't hit everyone equally. This is the data that drives policy conversations. For the final dashboards, I wanted to show 3 layers of insights: from a more executive numbers dashboard to a graph that can be interpreted easily, and finally a look into the actual impact.

## What I'd Do Differently
*   Start with MongoDB from Day 1 – JSON works for MVP but scales poorly.
*   Add authentication earlier – Admin endpoints were public for a few days on the first version 😂.
*   Add export functionality – Users want to download charts for presentations.

## What's Next
*   Historical trend analysis – 6-months forecast if I can get more data.
*   Check out similar trends in Namibia, Zambia, Zimbabwe, SA to see if they have similar challenges.

> Data without context is noise. Context without action is academic. By translating BERA's data into interactive visuals, I have provided the public with a tool to understand the true cost of this current war.
