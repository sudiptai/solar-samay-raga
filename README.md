# Sun versus Clock: a solar formalization of the Hindustani samay system

Code and data for the paper *"Sun versus Clock: Formalizing the Hindustani
Samay System on Solar Phase and Measuring Its Divergence from the Fixed-Clock
Convention"* (Sudipta Bhattacharya, IEM Kolkata). Paper A of a two-part
program; the manuscript source lives in `latex/`.

Every figure and number in the paper regenerates from a single run of each
notebook. All randomness is seeded.

## Contents

| File | What it is |
| --- | --- |
| `raga_time_location_emotion.ipynb` | Part A: solar engine (Eqs. 1-3), straddling window arcs, exact (breakpoint-integrated) fixed-clock vs solar divergence with boundary-sensitivity analysis, and the identifiability simulation with closed-form Bayes-optimal / rule-lookup references and Monte-Carlo SE reporting over 5 seeds. Self-contained; no data download; a few minutes on CPU. |
| `raga_saraga_real_data.ipynb` | Part B: Saraga Hindustani pipeline — unified table + IAST alias resolution, tonic-normalized cent-resolution pitch histograms from the official annotations, leave-one-artist-out raga identification with recording-level majority vote and recording-level permutation tests (B1), svara-samay audibility probe (B2, preliminary), and the pre-submission analyses (NOAA validation, exact population-weighted divergence by state capitals and by WorldPop 1-km raster, allied-raga errors, PCD-12 and voicing ablations, ctonic checks). Runs in REAL mode on Colab (downloads Saraga 1.5) and falls back to a synthetic SMOKE mode that validates the whole pipeline offline. |
| `unified_raga_samay.csv` | The 91-raga source-cited samay table: window, status (fixed / anytime / light / seasonal / imported), traditional time, sandhi-prakash flag, sources, dispute notes. |
| `latex/` | Manuscript source (`main.tex`), compiled PDF, and the figures extracted from the executed notebook runs of 12 Nov 2026. |

## Key results (runs of 12 Nov 2026)

- Fixed-clock vs solar window divergence, by exact breakpoint integration:
  15.7% of the day weighted by state population (Census 2011, state
  capitals); 15.9% under the WorldPop 1-km raster; 18.8% mean across 13
  cities spanning the extremes; max 35.9% (Bhuj, February); boundary
  sensitivity 17.3-20.7%. Solar engine validated against the NOAA algorithm
  (0.9 min mean error, max 3.7).
- Raga identification on Saraga Hindustani (8 ragas, 28 recordings, 8
  artists, leave-one-artist-out): 89.3% +/- 5.1 recording-level majority
  vote, recording-level permutation p <= 1e-4 on every seed; +13.1 points
  over a 12-bin PCD baseline under the same protocol; 41% of segment errors
  fall in scale-sharing allied pairs.
- The identifiability simulation is reported as recoverability of the
  paper's own formalization (the network matches the Bayes-optimal rule;
  lookup and Bayes are tie-breaking variants of one optimal family), never
  as evidence about music or listeners.

Earlier grid-sampled divergence figures (11.6% / 20.8% / 38.5%) were
inflated by boundary-aligned sampling and are superseded by the exact
values above.

## How to run

Part A: open in Google Colab or Jupyter, Run All.
Part B: open in Google Colab, Run All; approve the Drive mount to cache
features between sessions. The raster cell downloads the WorldPop India
1-km GeoTIFF (~60 MB).

## License and citation

MIT. Citation entry will be added on publication.
