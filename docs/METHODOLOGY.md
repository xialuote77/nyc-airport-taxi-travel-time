# Methodology and limitations

April: train on January-March; screen four models. May: train through April; validate Gamma GLR and GBT and compare with/without weather. June: train through May; final holdout evaluation. Feature transformers are fitted only on each training split.

The model buffer is the approximate 95th percentile of pooled April/May out-of-sample residuals. June coverage is the fraction with actual duration <= prediction + buffer, not a formal conditional coverage guarantee.

- Results cover yellow taxis to two airports in the first half of 2024. Other seasons and populations require validation.
- Weather is observed and rounded/aggregated by hour; it can include observations unavailable at departure. These retrospective results do not establish real-time forecasting performance.
- Weather-feature comparisons show predictive associations, not causal effects.
- Filtering and weather-completeness requirements change the analysed population; see preprocessing for inclusion rules.
- The original notebook counts exact duplicates but continues from the cleaned dataset rather than the deduplicated variable. This edition preserves that behaviour and reported results. Changing it requires rerunning downstream analysis.
- Aggregate buffer coverage can conceal differences between airports, zones, hours and weather groups.
- Live traffic, flights, check-in and security times are not included.

## Portfolio verification

Code cells were checked for Python syntax and headline numbers checked against the supplied LaTeX tables. Previews were extracted from original notebook figures. The full download/Spark pipeline was not rerun. Dependency ranges are not an environment lockfile.
