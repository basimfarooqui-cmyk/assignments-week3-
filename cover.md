# Assignment 3: Two Averages, One Argument

**Course:** Week 3 Descriptive Analytics
**Name:** Muhammad Basim Farooqui  **ID:** 37272
**Date:** 2026-11-18

## Data
`teaching_prices_clean.csv` (96 rows, 4 items, 2 cities, weekly 2026-01-01 to 2026-03-19).
SHA-256: `7698692cf19d4fbd7fe148361356ed7b56d231b4595b9f0c35de4c0b33d44802`

All data are **ILLUSTRATIVE TEACHING DATA - NOT ACTUAL PBS OBSERVATIONS**. Nothing here describes real prices.

## Contents
| File | What it holds |
|---|---|
| `0_cover.md` | This page |
| `1_attempt.md` | Referee's note draft with O/E/C labels, statistic choice per item, hash |
| `2_work.ipynb` | Mean, median, first-to-last change, with/without flagged value |
| `3_log_reflection.md` | AI interpretation audit table, confused-classmate excerpt, reflection |

## AI use statement
I used an AI tool for two steps only: (1) interpreting my statistics table (Section 2 of the brief) and (2) playing a confused classmate (Section 4). My note in `1_attempt.md` was written before I asked, and I did not replace it with AI text. Every number in the audit was recomputed in `2_work.ipynb`.

## Cleaning rules carried over from Week 2
Four rows have no `price_clean`: one missing price, one 1,250 outlier, one 9999 placeholder, one mislabelled `oil b` row. I excluded them and did not guess replacements.
