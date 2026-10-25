---
layout: post
title: "Pokémon Top Trumps Across All 9 Generations: 46,000 Simulated Games"
subtitle: "Which generations, types and Pokémon win when all 1,025 cards are in play"
date: 2026-10-25
categories:
- data-analysis
- simulation
- javascript
- data-visualization
---

My [Pokémon Top Trumps game](https://flaakira.github.io/pokemon-top-trumps/) started with the 151 Gen 1 Pokémon. It now includes all **1,025 Pokémon from Gen 1 (Kanto) to Gen 9 (Paldea)**, and before each match you choose which generations to play with. A bigger card pool raises new questions: Are newer generations stronger? Does Fire still dominate? Who replaces Mewtwo at the top? To answer them, I simulated **46,000 games (440,056 rounds)** with the same rules as the live game.

👉 **[Explore the interactive report](https://flaakira.github.io/pokemon-analysis-all-gens.html)**
👉 **[Play the game](https://flaakira.github.io/pokemon-top-trumps/)**

## The approach

1. **Collect:** pulled base stats, types and generation for all 1,025 Pokémon from PokeAPI. The Gen 1 data matched my original Databricks gold-layer data exactly.
2. **Simulate:** built a headless copy of the game engine: 6 v 6 knockout, a random stat each round, primary-type multipliers (1.2x / 0.8x) and the blocked-stat rule after a draw.
3. **Validate:** re-ran 10,000 Gen 1 games and compared them with my [original 10,000-game study](https://flaakira.github.io/pokemon-analysis.html): 50.3% vs 49.44% win rate, 9.56 vs 9.51 average rounds, Mewtwo 87.8% vs 87.2%.
4. **Test:** 1,000 games for each generation on its own (9,000), 1,000 for each of the 36 generation pairings (36,000), and 1,000 games with all generations together.

## What I found

- 🆕 **Newer generations are stronger.** Gen 9 wins **60.6%** of games against the other generations, with Gen 7 (59.3%) and Gen 4 (58.7%) close behind. Gens 1, 2 and 3 win only about 40%. A Gen 1 team beats a Gen 9 team only **33.7%** of the time.
- ⚖️ **Each generation on its own is fair.** When both teams come from the same generation, each side wins about half the time (46.6% to 52.6%, within normal random variation).
- ⚡ **Zekrom is the new champion.** It wins **89.6%** of its rounds, ahead of Arceus (88.5%), Reshiram (88.0%), Palkia (87.1%) and Rayquaza (85.6%). Mewtwo drops to 82.4% against the wider field. 25 Pokémon win more than 80% of their rounds.
- 🐉 **Dragon is the best type.** Dragon-type Pokémon win **63.7%** of their rounds, followed by Steel (58.6%). Bug (41.3%) and Normal (41.8%) are the weakest types.
- 🔥 **Fire still burns Bug.** At **85.7%**, Fire vs Bug is still the most one-sided matchup, followed by Flying vs Bug (83.9%) and Fire vs Grass (83.2%).
- ❌ **Baby and first-stage Pokémon are liabilities.** Igglybuff (2.8%), Wishiwashi (4.4%) and Azurill (4.6%) are the weakest cards. Pokémon with a stat total under 300 win only 23.6% of their rounds on average.
- 📈 **Stats decide the card.** A card's stat total predicts its win rate almost perfectly (correlation **0.98**). The average stat total explains the generation gap: about 380 for Gen 9 against about 340 for Gens 1 to 3.

## Recommendations

1. **For a fair match,** play a single generation or all generations: both sides draw from the same pool.
2. **For a challenge,** pit an older generation against a newer one, and expect to lose about two games out of three.
3. **Gens 1 to 3 are balanced with each other:** every pairing between them is within about 1.5 points of 50%.
4. **Build around Dragon and Steel types,** and avoid Bug and Normal types when the matchup doesn't help.

## Tools & skills

JavaScript (Node.js simulation engine) · PokeAPI GraphQL · Monte Carlo simulation · data validation · Chart.js dashboard · segmentation by generation and type · game balance analysis

*This study follows my [original Gen 1 Pokémon Top Trumps analysis](https://flaakira.github.io/pokemon-analysis.html). Pokémon data from PokeAPI, collected on October 25, 2026. This is an independent fan project, not affiliated with Nintendo, Game Freak or The Pokémon Company.*
