# Football-Data-Analysis
# Football Red Cards & Goal Scoring Analysis

An investigation into whether red cards lead to more goals in football matches,
using five seasons of European league data covering 20,370 matches.

## Overview

This project takes a multi-layered analytical approach to test the hypothesis
that red cards increase goal scoring. Rather than relying on a single metric,
the analysis is structured around three angles of increasing granularity —
from match-level totals to in-game timing to team-specific outcomes.

## Approach

**Part 1 — Total Goals: Matches With vs Without Red Cards**
A Poisson regression model comparing expected goal counts across matches,
controlling for competition and season. Red-card matches showed a statistically
significant 2.6% increase in expected goals (p = 0.027).

**Part 2 — Goal Rate Before vs After Red Card**
A time-adjusted Poisson model comparing scoring intensity within the same match,
before and after a red card is issued. The goal rate increased by approximately
50% after a red card (coefficient -0.366, p < 0.001).

**Part 3 — Which Team Benefits?**
An analysis of post-red card goal distribution and match outcomes. Teams with
11 players scored nearly three times as many goals as red-carded teams. A
logistic regression confirmed red-carded teams have roughly 24% of the odds
of winning the match.

## Key Results

- Red cards are associated with a ~2.6% increase in total match goals
- Scoring rate rises ~50% after a red card is issued
- The opposing team (11 players) scored 2,489 post-red card goals vs 864 for
  the reduced team
- Red-carded teams won 631 matches; opponents won 1,775

## Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Statsmodels

## Structure

- `football-analysis.ipynb` — Full analysis with EDA, modelling, and conclusions
- `data/events.csv` — Match events (goals, red cards) with minute and team side
- `data/games.csv` — Match metadata across European leagues (2019–2024)

## Dataset

57,750 match events across 20,370 fixtures from the English, French, German,
Italian, and Spanish league systems. Events include goals and red cards with
exact minute timestamps, capped at 45 and 90 for injury time.
