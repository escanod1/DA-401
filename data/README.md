# Breaking Through the Plateau: What Predicts Strength Recovery in Competitive Powerlifters?

DA 401 Seminar in Data Analytics, Denison University, Fall 2026
By: Dylan Escano

## Research Question
Once a competitive powerlifter's strength progression plateaus, what factors predict whether they break through it or remain stalled?

## Data 
- Source: OpenPowerlifting bulk CSV, version f231b4f6 (published 09-26-2026)
- Download: https://openpowerlifting.gitlab.io/opl-csv/bulk-csv.html
- The csv is not in the repo because it is too large for Github.
- OpenPowerlifting data is in the public domain.

## Methods
1. **Cleaning:** kept full-power (squat, bench, deadlift), raw, drug-tested meets with a completed total. Kept one row per lifter per meet and only lifters with 3 or more meets.
2. **Plateau:** confirmed on the date of the 2nd meet in a row where the lifter did not beat their personal best (PB).
3. **Outcome (Breakthrough):** 1 if the lifter set a new PB within the next 3 meets or 24 months (whichever came first), 0 if they competed in that window without a new PB. Lifters with no follow-up meet were excluded. Only each lifter's first plateau was used.
4. **Predictors (measured before the plateau):** age, sex, training age, competition frequency (meets in the prior 12 months), weight-class change, percent bodyweight change, and strength (DOTS at PB, per 10 points).
5. **Model:** logistic regression (statsmodels), reported as odds ratios with 95% confidence intervals.
