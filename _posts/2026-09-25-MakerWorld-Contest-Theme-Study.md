---
layout: post
title: "What Makes a 3D Design Contest Succeed? A Theme Study of 158 MakerWorld Contests"
subtitle: "Composite scoring, S/A/B/C tiers and the best and worst contests across six theme categories"
date: 2026-09-25
categories:
- business-analysis
- data-analysis
- python
- data-visualization
---

MakerWorld, Bambu Lab's 3D model platform, runs a new design contest almost every week: Halloween decorations, garden tools, RC battleships, board games. Since October 2023 these contests have received **131,899 models** and **43.7 million views**. As a business analyst, I wanted to find out which themes activate the community, which ones don't, and what a contest planner should do with that information.

👉 **[Explore the interactive report](https://flaakira.github.io/makerworld-contest-analysis.html)**
👉 **[See the Python notebook](https://github.com/flaakira/makerworld-contest-analysis/blob/main/makerworld_contest_analysis.ipynb)**

## The approach

1. **Collect:** gathered all 158 contests from the public contests page, plus each contest's detail page (prizes and winners).
2. **Classify:** put every contest into one of six theme categories: Seasonal & Holidays, Home & Functional, Toys & Games, Art/Décor & Fashion, Engineering & Tech, and Education & Social Good.
3. **Score:** built a Composite Performance Score (40% participants, 30% models per day, 30% views, each converted to a percentile) and ranked the 150 finished contests into S/A/B/C tiers.
4. **Analyze:** compared the categories, host types (official vs. creator-hosted) and seasonality, and looked at how prize size relates to participation.

## What I found

- 🎃 **Holidays rule.** Twelve Halloween, Christmas, Valentine's and Easter contests brought in **33.7% of all models submitted**, with **4.4x** the median participation of other contests. The best contest overall was *Cozy Christmas 2024* (6,254 models, 3,362 participants).
- 🗓️ **Holiday cannibalization.** Regular contests launched from September to December get **34% fewer participants** (median 347 vs. 526).
- ⚙️ **Engineering gets viewers but few entries.** Engineering & Tech contests get about as many views as other categories but have the lowest participation (288 median participants). Only 7% of them reach Tier S/A. The worst contest overall, *Automobile*, got just 42 models.
- 🏠 **Home & Functional is the reliable workhorse.** It's the biggest category (40 contests), and everyday-problem themes like *Gardening Tool* consistently draw 500+ makers.
- 🧸 **Toys & Games produce the most-loved winners,** with about 2,300 likes per winning model, the highest of any category.
- 🤝 **Creator-hosted and brand-sponsored contests lag,** mostly because of visibility (about 159k median views vs. 283k for official contests). **Prize size doesn't predict participation** (ρ = −0.18).

## Recommendations

1. Build the calendar around the four holiday flagship contests.
2. Protect regular contests from September to December: run fewer of them, use easier briefs, or extend their deadlines.
3. Fill the rest of the year with Home & Functional problems.
4. Lower the barrier for engineering contests with starter templates and beginner prize tracks.
5. Give creator-hosted and brand contests more promotion instead of bigger prizes.

## Tools & skills

Python (pandas, matplotlib) · JavaScript for data collection · Chart.js dashboard · KPI design and weighted scoring · segmentation · seasonality analysis · business recommendations

*This is the second project in my "game and community analytics" series. The first was a [Pokémon Top Trumps competitive analysis](https://flaakira.github.io/pokemon-analysis.html).*

*Data collected from public MakerWorld pages on September 25, 2026. This is an independent study, not affiliated with Bambu Lab or MakerWorld.*
