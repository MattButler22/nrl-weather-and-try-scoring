# NRL Weather and Try-Scoring

Does weather affect try-scoring in the NRL? An analysis of 1,599 matches (2019–2026), 
testing whether in-match rain and wind influence how many tries are scored.

## Data
- **Source:** Open-Meteo ERA5 reanalysis (weather) matched to NRL fixtures
- **Coverage:** 1,599 matches, 2019–2026
- **Variables:** in-match rainfall (mm), mean wind speed (kph), total tries per match

## Approach
- Grouped matches into rainfall buckets and compared mean try-scoring
- Collapsed to a dry-vs-wet split, with robustness checks across rainfall thresholds
- Tested significance with a Welch's t-test
- Fitted a Poisson regression (appropriate for count data) with rain and wind together, 
  to isolate each variable's effect

## Findings
- **Rain** has a small but statistically significant negative effect on try-scoring 
  (~2.5% fewer tries per mm; p = 0.008)
- **Wind** has a negligible effect, even controlling for rain
- Overall, weather explains almost none of the variation in tries (pseudo-R² ≈ 0.002) 
  — a real but minor factor

## Limitations
- The heaviest-rain effect rests on a small sample (19 games), so magnitude is uncertain
- Only in-match conditions are measured — rain before kickoff (a wet surface on a dry 
  evening) isn't captured
- League-wide averages may hide stronger effects at specific venues or in particular conditions

## Files
- `nrl_weather_analysis.ipynb` — full analysis
