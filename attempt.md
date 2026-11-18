Data hash (SHA-256 of `teaching_prices_clean.csv`): `7698692cf19d4fbd7fe148361356ed7b56d231b4595b9f0c35de4c0b33d44802`
Data: ILLUSTRATIVE TEACHING DATA - NOT ACTUAL PBS OBSERVATIONS.
Labels: **O** = observation, **E** = possible explanation (labelled as such), **C** = causal claim.

## 1. Statistics (cleaned prices, PKR per kg, illustrative)

| Item | n | Mean | Median | Mean - median | First-to-last change |
|---|---|---|---|---|---|
| Staple A | 22 | 111.39 | 112.5 | -1.11 | +12.99% |
| Oil B | 24 | 324.83 | 324.0 | +0.83 | +15.28% |
| Pulse C | 23 | 205.91 | 206.0 | -0.09 | +3.07% |
| Sweetener D | 23 | 167.15 | 167.5 | -0.35 | +19.42% |

First-to-last change is computed within each item-city series, then averaged over the two cities. Pulse C City 2 has no price on 2026-01-01, so its series starts on 2026-01-08.

## 2. Which statistic I would report, and why

- **Staple A:** report the **first-to-last change** to answer "did it go up". Mean and median are within about 1 PKR, so they agree. The raw (uncleaned) mean is 160.89 because of one 1,250 value, so if the flagged value were left in, the mean would be wrong and the median (112.5) would be the safer figure.
- **Oil B:** first-to-last change (+15.28%). Mean and median differ by 0.83 PKR, so either average is fine, and I would quote the median.
- **Pulse C:** first-to-last change (+3.07%), with the median (206.0). This item is the flattest, and one missing value changes which start date is used, so I state the start date.
- **Sweetener D:** first-to-last change (+19.42%). A 9999 placeholder would have pushed the mean to 576.81 while the median stayed near 167.75, so the median is the safer figure to quote if cleaning is in doubt.

Reason overall: all four series rise over the period, so a mean or median over the whole period describes the middle of a moving series, not "the price now". For a question about whether a price went up, the first-to-last change within each city is the direct measure.

## 3. With and without a flagged value (Staple A)

| | n | Mean | Median |
|---|---|---|---|
| With 1,250 (City 2, 2026-01-15) | 23 | 160.89 | 112.5 |
| Without | 22 | 111.39 | 112.5 |
| Difference | | 49.50 | 0.00 |

The single value moves the mean by 49.50 PKR and the median by 0. The mean uses every value's size, so one extreme value pulls it. The median uses only the middle position, so the same value counts as one observation above the middle.

## 4. Draft referee's note

**Referee's note: did the price "really" go up?** (illustrative data)

1. **[O]** In the teaching file, all four items have a higher last price than first price in both cities, from 2026-01-01 (2026-01-08 for Pulse C City 2) to 2026-03-19.
2. **[O]** The first-to-last changes, averaged over the two cities, are +12.99% for Staple A, +15.28% for Oil B, +3.07% for Pulse C and +19.42% for Sweetener D.
3. **[O]** After removing four flagged rows, the mean and median of each item are within 1.2 PKR of each other.
4. **[O]** One flagged Staple A value, 1,250, would move the mean from 111.39 to 160.89 and leave the median at 112.5.
5. **[O]** The neighbour who quotes the median is right that the median is more stable when a value is wrong; the neighbour who quotes the mean is right that, once the data are clean, the mean tells the same story.
6. **[O]** Both averages describe the middle of the whole period, so neither answers "did it go up"; the first-to-last change does.
7. **[E]** The Staple A value of 1,250 may be a typing error, for example a price entered with an extra digit or in different units, but the file does not say, so this is a guess.
8. **[E]** The 9999 in Sweetener D looks like a placeholder for "no data", which is a common convention, but the source is not documented in the file.
9. **[E]** The row labelled `oil b` at 108.5 looks like a Staple A City 1 price, because it sits in the Staple A price range, but I could not confirm it.
10. **[O]** Four of the 96 rows were excluded, so each statistic uses 22 to 24 of the 24 possible weekly values for that item.
11. **[O]** The file covers 12 weeks and two cities, so these results describe this file only.
12. **[C]** None. I make no causal claim about why prices rose, because the file has no information on costs, supply or demand.

**Recommendation to Ms. Noor:** publish the first-to-last changes, say how many rows were excluded and why, and give the median beside the mean. The "mean vs median" argument is settled by the data: after cleaning, they agree.

*Note on sentence 3:* the largest gap is Staple A at 1.11 PKR.
