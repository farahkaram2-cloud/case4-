# FIN 450 Case 4 — Apple option-pricing lab

## Upload instructions
Unzip and upload the CONTENTS of this package to the GitHub repository root, preserving `docs/`, `data/`, `original/`, and the notebook. Do not upload the ZIP itself. GitHub Pages must publish `docs/`. Existing deployment workflow must not regenerate or overwrite `docs/index.html`.

## What is complete
- Dated Apple close and listed option quote (Nov 9 2026), 8 dated analyst targets, CRR American call pricing, convergence, parity benchmark, Greek finite-difference checks, Plotly charts, Greek calculator, documented source CSV and executed notebook.
- Original classroom notebook and validation infrastructure are retained without edits. Previous fictional results preserved in `original/`.

## Unresolved / material warnings
1. $97.20 student DCF is from an earlier assignment and **not** an equity-per-diluted-share value independently reconciled as of Nov 9 2026. A valid DCF-date bridge is required.
2. 4% annual continuously compounded rate is an illustrative assumption, not a dated term-matched Treasury observation.
3. 24.8% volatility is expiration-level chain IV, not verified contract-specific IV.
4. Analyst targets use an assumed 12-month convention, whereas the option expires in two days. No valid horizon mapping exists in this package; do not interpret the analyst payoff diagnostic as fair value.
5. The selected listed AAPL option is American; analytic Greeks are a **European benchmark**, not American CRR derivatives.
6. Dividend yield is estimated; the next ex-dividend date is after the option expiration.
7. The previous comparables valuation was fictional and has been left missing, not fabricated.

These issues are explicitly flagged. The package is **not a claim of full instructor acceptance**.

## Run
`pip install -r requirements-module5.txt` then `jupyter nbconvert --execute --to notebook --inplace aapl_module5_greeks.ipynb` from the repository root. The executed notebook is already included.

## Sources
- Apple historical stock close: https://investor.apple.com/stock-price/default.aspx
- Option chain: https://www.optionistics.com/quotes/stock-option-chains/AAPL?date=2026-11-09&expirations=0&expiry=2026-11-11&greeks=0&nonstd=-1&putcall=all&range=ntm
- Analyst targets: https://www.marketbeat.com/stocks/NASDAQ/AAPL/forecast/ and https://www.google.com/finance/quote/AAPL:NASDAQ

See `data/source_documentation.csv` for each input.
