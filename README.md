# econ5200-lab07-bootstrapping
# Diagnosing Broken Confidence Intervals

## Objective
I studied when bootstrap confidence intervals fail and how to diagnose and fix those failures.

## Methodology
- I examined a degenerate bootstrap for the median of 32,561 integer ages.
- I measured the coverage of nominal 95% intervals on skewed simulated data.
- I compared parametric and bootstrap intervals for the mean and median.
- I tested an i.i.d. bootstrap on clustered wage data and repaired it with a cluster bootstrap.
- I used a `bootstrap_utils.py` module with percentile, i.i.d., and cluster bootstrap functions.
- I used AI to write a coverage function, revised the prompt, and checked the result against my own simulation.

## Key Findings
- The bootstrap SE for the median age was 0.000000, and BCa returned `nan`.
- For the mean, the parametric interval had 92.5% coverage and the bootstrap interval had 92.0% coverage.
- For the median, the parametric interval had 66.8% coverage and the bootstrap interval had 92.8% coverage.
- Treating workers from 25 firms as independent produced an interval 5.7x too narrow.
- The naive bootstrap had 19.5% coverage, while the cluster bootstrap improved coverage to 91.0%.
- The AI coverage function reproduced the same results: 19.5% for the naive interval and 91.0% for the clustered interval.
