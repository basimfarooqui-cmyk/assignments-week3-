Data: ILLUSTRATIVE TEACHING DATA - NOT ACTUAL PBS OBSERVATIONS.
Data hash: `7698692cf19d4fbd7fe148361356ed7b56d231b4595b9f0c35de4c0b33d44802`

## A. Interpretation Auditor

### Prompt given to the AI
"Here is a statistics table of illustrative price data (PKR per kg). Interpret it for a newsroom reader."

| Item | n | Mean | Median | SD | First-to-last change |
|---|---|---|---|---|---|
| Staple A | 22 | 111.39 | 112.5 | 6.39 | +12.99% |
| Oil B | 24 | 324.83 | 324.0 | 14.53 | +15.28% |
| Pulse C | 23 | 205.91 | 206.0 | 3.91 | +3.07% |
| Sweetener D | 23 | 167.15 | 167.5 | 9.70 | +19.42% |

### AI interpretation (🟩 recomputable, 🟨 explanation, 🟥 causal or unseen data)

1. 🟩 Sweetener D shows the largest increase, about 19.4%.
2. 🟩 Pulse C is the most stable item, with a standard deviation of 3.91.
3. 🟩 Oil B rose about 15.3% from first to last observation.
4. 🟩 Pulse C rose by about 5.3% over the period.
5. 🟨 Oil B's mean (324.83) and median (324.0) are close, which suggests a roughly symmetric distribution.
6. 🟨 Staple A's mean is below its median, which suggests a few low prices are pulling the mean down.
7. 🟨 The mean is the best summary for all four items.
8. 🟥 Prices rose mainly because of inflation and higher input costs.
9. 🟥 Sweetener D climbed in January because of winter demand for sweet foods.
10. 🟥 The 1,250 value for Staple A was a data-entry error.
11. 🟥 Food prices across Pakistan are rising at roughly 12% per quarter.

### Audit table

| # | Claim | Colour | How I checked | Decision |
|---|---|---|---|---|
| 1 | Sweetener D largest increase, ~19.4% | Green | Notebook section 2: 19.80% (City 1) and 19.03% (City 2), average 19.42%. Largest of the four. | Accepted |
| 2 | Pulse C most stable, SD 3.91 | Green | `stats["sd"]`: 3.91 vs 6.39, 9.70, 14.53. Lowest SD. | Accepted |
| 3 | Oil B rose ~15.3% | Green | Per city 15.44% and 15.13%; average 15.28%. | Accepted |
| 4 | Pulse C rose ~5.3% | Green (checked, fails) | 5.25% comes from averaging both cities by date first, then comparing first and last. Pulse C City 2 has no price on 2026-01-01, so the start is City 1 alone (200.0). Within each city: +3.75% and +2.40%, average 3.07%. | **Rejected** (correct value 3.07%) |
| 5 | Oil B mean ~ median, so roughly symmetric | Amber | Mean - median = 0.83 PKR (true). But the series rises steadily over 12 weeks, so this says nothing about symmetry of a "typical price". | Accepted only as "mean and median are close"; symmetry claim rejected |
| 6 | Staple A mean below median because a few low prices pull it down | Amber | Mean 111.39 < median 112.5 (true, gap 1.11). Lowest value is 99.5 (2026-01-08). The gap is about 1% of the price and comes from the trend, not an outlier. | Fact accepted; explanation rejected as overstated |
| 7 | Mean is the best summary for all items | Amber | Mean-median gaps are all within 1.2 PKR, so for cleaned data both are fine. For uncleaned Staple A the mean (160.89) is wrong and the median (112.5) is not. | Rejected |
| 8 | Rose because of inflation and input costs | Red | The file has no cost, inflation or supply columns. Cannot be recomputed. | Rejected |
| 9 | Sweetener D climbed because of winter demand | Red | Refers to demand data I was not shown. D rose steadily January to March, not only in January. | Rejected |
| 10 | 1,250 was a data-entry error | Red | The flag says "outlier vs item/city median; excluded pending source". The source is not in the file. A possible explanation, not a finding. | Rejected as stated; kept as "possible" (label E) |
| 11 | Pakistan food prices rising ~12% per quarter | Red | Data are illustrative, cover 2 cities and 4 items for 12 weeks, and are not PBS observations. | Rejected |

**Score:** 11 claims: 3 accepted (1, 2, 3), 2 accepted in part (5, 6), 6 rejected (4, 7, 8, 9, 10, 11). One number (claim 4) was wrong, which I found only by recomputing.

## B. Confused Classmate (excerpt)

**Prompt:** "Play a classmate who believes 'the mean is always the typical price' and keeps asking 'but why?'."

**Classmate (AI):** The mean uses every number, so it must be the most typical price, right?

**Me:** It uses every number, but that includes wrong or extreme ones. Take Staple A. Without the bad value the mean is 111.39 and the median is 112.5. If one price of 1,250 sneaks in, the mean becomes 160.89 and the median is still 112.5.

**Classmate:** But why does the mean move so much? It's still an average.

**Me:** The mean adds up the sizes of all values. 1,250 is about eleven times the others, so it adds roughly 1,140 PKR to a total that is then divided by 23. The median only asks "which value sits in the middle after sorting?". 1,250 is just one value at the top of the list, so the middle barely shifts.

**Classmate:** So the median ignores the 1,250? That seems like throwing away information.

**Me:** It does not ignore it, it counts it as one observation at the top. It ignores *how far* above. If the 1,250 were a true price, that would matter and I would say so. If it is a typo, that is the information you want to ignore.

**Classmate:** Then when is the mean fine?

**Me:** When values are clean and fairly even, like the cleaned data here, where mean and median differ by at most 1.11 PKR. Then they agree and either is fine. The mean is not "always typical"; it is typical when nothing extreme is in the data.

**Classmate:** OK, but you said both are the "middle of the whole period". If prices go up all the time, what is the typical price?

**Me:** There is no single typical price of a rising series. The mean and median describe the middle of the period, not today. That is why the note reports the change from first to last observation as well: Oil B went from 298 to 344 in City 1, which is +15.44%, and neither average shows that.

**Classmate:** That makes sense. So the mean is not wrong, it just answers a different question.

*(The classmate stopped repeating "isn't the mean typical?" after the 1,250 example and the rising-series point.)*

## C. Reflection: where did my first draft say more than the data allowed?

1. **"Prices rose" without saying where.** My first draft said the staples went up. The file has 4 items, 2 cities and 12 weeks of illustrative data, so I can say it for those, not for prices in general.
2. **A causal tone in the explanation.** I first wrote that the 1,250 was "a typing error". The flag only says the value is an outlier pending source. I changed it to a possible explanation (E).
3. **Pooled change.** I first computed first-to-last change by averaging both cities by date, which gave Pulse C +5.25%. Because City 2 had no price on 2026-01-01, that compared different cities at the start and end. Within each city it is +3.07%.
4. **"Mean and median agree, so the argument is settled."** They agree after cleaning, but only because I excluded four rows. If the 1,250 stays in, the neighbours would disagree by almost 50 PKR. The note now says the result depends on the cleaning.
5. **Treating the average as "the price".** All four series trend upward, so a period mean or median is the middle of the period, not the current price. I added the first-to-last change as the direct answer.

What I would still not claim: any cause of the increases, any real-world price level, or that the excluded rows are errors rather than real prices.
