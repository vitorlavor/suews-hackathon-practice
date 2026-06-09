# SUEWS Community Hackathon Practice Setup

This practice repository was created from the hackathon template and used to check that the SUEWS workflow runs end to end before the event.

## Setup Status

- Repository: public practice repo under `vitorlavor`.
- Task brief: read locally from `TASK_BRIEF.md`.
- SUEWS agent: installed as the Codex plugin `suews@suews 0.2.0`.
- Pages source: `main` branch, `/docs`.

## Smoke Test

The smoke test used the bundled `simple-urban` KCL/London sample case. This is a toolchain check, not a site-specific heat-risk result.

| Step | Result |
| --- | --- |
| Create case | `suews init --template simple-urban` succeeded |
| Inspect config | KCL sample site, London; forcing file detected |
| Validate config | Phases A and C passed; phase B returned demo-case warnings |
| Run model | SUEWS wrote `KCL1_2012_SUEWS_60.txt` |
| Diagnose output | Output present; no NaNs in `QH`, `QE`, or `QN`; closure warning retained |

Selected summary values from the run:

| Variable | Mean | Min | Max | NaN % |
| --- | ---: | ---: | ---: | ---: |
| QN | 44.76 | -83.80 | 646.98 | 0.0 |
| QH | 88.76 | -40.82 | 339.70 | 0.0 |
| QE | 27.58 | 1.70 | 195.34 | 0.0 |
| QS | 12.94 | -81.70 | 387.69 | 0.0 |
| T2 | 11.91 | -5.24 | 30.40 | 0.0 |
| RH2 | 69.33 | 18.75 | 98.16 | 0.0 |

## Caveats

This practice run is a Level 1 demo. It uses sample London/KCL inputs and sample forcing, so it proves that the local SUEWS toolchain works but does not answer the hackathon city question. The diagnostic closure warning should be reviewed before using any run as scientific evidence.

For the judged hackathon repository, replace this page with the focus-city heat-hazard layer, heat-to-risk bridge, indicator result, scientific caveats, and correct SUEWS citations.
