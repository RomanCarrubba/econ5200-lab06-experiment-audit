# econ5200-lab06-experiment-audit
# Experiment Design Audit — Power, Selection & Weighting

## Objective
I audited an underpowered A/B test and a biased observational comparison to show how sample size and selection affect what an estimate can tell you.

## Methodology
- Audited an A/B test that ran on 2% of traffic, with 1,000 users in the treatment group, and calculated its power to detect a 0.8 percentage point lift.
- Calculated the number of users per group needed to reach 80% power for the same lift.
- Wrote my own `power_check` function and compared its output against statsmodels.
- Used `power_check` to find the power the same 50,000 users would have had if split evenly between the two groups.
- Compared participants and non-participants in a wellness program to show how selection bias distorts the naive estimate.
- Used inverse probability weighting to correct for that selection.
- (Extension) Computed Meng's data defect correlation to compare biased poll responses with random ones.

## Key Findings
- The original A/B test had only 19.8% power to detect a 0.8pp lift. Reaching 80% power would have required 7,172 users per group.
- My `power_check` function matched statsmodels. With the same 50,000 users split evenly, power would have been 97.7%.
- The naive wellness-program estimate was -$1,396, against a true effect of -$500. Selection bias was the cause.
- Inverse probability weighting brought the estimate to -$522.
