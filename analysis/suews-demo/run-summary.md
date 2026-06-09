# SUEWS Demo Run Summary

This smoke test used the `suews@suews` Codex plugin and the bundled `simple-urban` KCL/London sample case. It confirms that the local SUEWS toolchain can initialise, inspect, validate, run, diagnose, and summarise a model case end to end.

## Toolchain

- SUEWS version: `2026.6.5`
- SuPy version: `2026.6.5`
- Schema version: `2026.5`
- SUEWS source commit reported by the tool: `9dae7a8`

## Run

- Config: `analysis/suews-demo/updated_sample_config.yml`
- Forcing: `analysis/suews-demo/Kc_2012_data_60.txt`
- Output: `analysis/suews-demo/Output/KCL1_2012_SUEWS_60.txt`
- Simulation period reported by SUEWS: `2012-01-01 00:05:00` to `2013-01-01 00:00:00`
- Timesteps summarised: `8784`

## Summary Variables

| Variable | Mean | Min | Max | NaN % |
| --- | ---: | ---: | ---: | ---: |
| QN | 44.76 | -83.80 | 646.98 | 0.0 |
| QH | 88.76 | -40.82 | 339.70 | 0.0 |
| QE | 27.58 | 1.70 | 195.34 | 0.0 |
| QS | 12.94 | -81.70 | 387.69 | 0.0 |
| T2 | 11.91 | -5.24 | 30.40 | 0.0 |
| RH2 | 69.33 | 18.75 | 98.16 | 0.0 |

## Diagnostics

`suews diagnose` found the output file and no NaNs in `QH`, `QE`, or `QN`. It also raised a closure warning: the mean closure residual was `5.731`, above the `0.10` diagnostic threshold.

This run is therefore a Level 1 demo: the toolchain works, but the sample result should not be interpreted as a site-specific hackathon analysis.
