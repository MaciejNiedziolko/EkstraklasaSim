# EkstraklasaSim
Monte-Carlo probabilistic simulator for final league positions in the Polish Ekstraklasa. Estimates probabilities of finishing positions, chances for European places and relegation, and generates distribution plots.
Overview
This tool takes the current standings (points, goals for/against, matches played) and the remaining fixtures, estimates offensive/defensive strengths for each team, then simulates the remainder of the season using Poisson scoring models. Outputs include a CSV of simulation results and PNG plots of position distributions.

# Features
-Estimate team attack/defense strengths from the standings.
-Simulate matches (home/away) using Poisson goal models with configurable home advantage.
-Compute probabilities: P(champion), P(top-2/3/4/5), P(Europe), P(relegation), expected points, mean/median position, std dev.
-Per-team distribution plots and a combined probability plot.
-Robust CSV reading (multiple encodings) and tolerant to small input inconsistencies.

# Repo structure (suggested)

EkstraSim/
├─ data/
│  ├─ standings.csv        # current table
│  └─ fixtures.csv         # remaining fixtures
├─ src/
│  └─ ekstrasim.py         # main script
├─ outputs/
│  ├─ simulation_results.csv
│  └─ distribution_<team>.png
├─ requirements.txt
├─ README.md
└─ LICENSE

# Requirements
Python 3.8+

Required packages (see requirements.txt)
Input file formats

standings.csv — required columns:
team — team name (string)
played — matches played (int)
points — current points (int)
gf — goals for (int)
ga — goals against (int)

fixtures.csv — required columns:
home — home team name (string)
away — away team name (string)
Team names must match between the two files.
