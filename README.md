# Solar anchoring of the Hindustani samay system

Code and data for the paper *"Solar Anchoring of the Hindustani Samay System:
An Astronomical Formalization and Feasibility Study for Context-Aware Raga
Selection"* (Sudipta Bhattacharya, IEM Kolkata).

Every figure and number in the paper regenerates from a single run of each
notebook. All randomness is seeded.

## Contents

| File | What it is |
| --- | --- |
| `raga_time_location_emotion.ipynb` | Part A: solar engine (Eqs. 1-6), straddling window arcs, fixed-clock vs solar divergence analysis, feasibility simulation with Bayes-optimal / rule-lookup baselines, bootstrap statistics. Self-contained; no data download; ~2 min on CPU. |
| `raga_saraga_real_data.ipynb` | Part B: Saraga Hindustani pipeline — unified table + IAST alias resolution, tonic-normalized cent-resolution pitch histograms from the official annotations, artist-disjoint raga identification (B1), svara-samay audibility probe (B2, preliminary), and the pre-submission analyses (NOAA validation, population-weighted divergence, allied-raga errors, PCD-12 baseline, ctonic checks). Runs in REAL mode on Colab (downloads Saraga 1.5, ~15 GB) and falls back to a synthetic SMOKE mode that validates the whole pipeline offline. |
| `unified_raga_samay.csv` | The 91-raga source-cited samay table: window, status (fixed / anytime / light / seasonal / imported), traditional time, sandhi-prakash flag, sources, dispute notes. |

## Key results (as in the paper)

- Fixed-clock vs solar window divergence: 11.6% of the day weighted by state
  population; 20.8% across 13 cities spanning the extremes; max 38.5% (Bhuj,
  February). Solar engine validated against the NOAA algorithm (0.9 min mean
  error).
- Raga identification on Saraga Hindustani (8 ragas, 28 recordings,
  artist-disjoint): 70.7% top-1 / 91.5% top-3, permutation p = 1e-4 per seed;
  +8.1 points over a 12-bin PCD baseline.
- The feasibility simulation is reported as recoverability of the paper's own
  formalization (the network matches the Bayes-optimal rule), never as
  evidence about music or listeners.

## How to run

Part A: open in Google Colab or Jupyter, Run All.
Part B: open in Google Colab, Run All; approve the Drive mount to cache
embeddings between sessions. `SEEDS_B = (7, 17, 27, 37, 47)` reproduces the
paper's statistics.

## License and citation

MIT. Citation entry will be added on publication.
