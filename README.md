# econ5200-lab02-deflation
Index Integrity — Deflation, Substitution Bias & Goodhart
Objective

Diagnosed a flawed price-deflation pipeline, quantified CPI substitution bias between CPI-U and C-CPI-U, and built a monitor that detects Goodhart's Law failures in engagement KPIs.

Methodology
Diagnosed and repaired four bugs in a nominal-to-real deflation pipeline, including a base-period mislabeling defect where output deflated to 1982–84 dollars was reported as 2020 dollars.
Quantified upper-level substitution bias by comparing annualized CPI-U and C-CPI-U growth rates over a fixed sample window, distinguishing this compounded percentage-point gap from the non-comparable raw index-point differential.
Identified a Goodhart's Law failure mode by tracking the rolling correlation between DAU/MAU and time-per-session, isolating the window in which the relationship inverted.
Packaged the corrected deflation logic into deflation_utils.py with a test suite validating deflate_series() against known base-period conversions.
Built an interactive index-integrity monitor (ipywidgets + Plotly) exposing the substitution-bias gap and correlation-flip detection as adjustable, auditable parameters rather than hard-coded constants.
Key Findings
CPI-U annualized: [YOUR VALUE]%/year; C-CPI-U annualized: [YOUR VALUE]%/year → substitution-bias gap of [YOUR VALUE] pp/year. This is distinct from the raw index-point differential of [YOUR VALUE] points/year, which is a level-unit slope, not an inflation rate, and should not be reported as one.
The rolling correlation between DAU/MAU and time-per-session inverted from [YOUR VALUE] to [YOUR VALUE], flagging a Goodhart's Law risk: optimizing DAU/MAU in isolation may no longer track genuine engagement.
