# Update your GitHub Pages option pricer

1. Download and unzip `option-pricer-update.zip`.
2. Open your `farahkaram2-cloud/case4-` repository on GitHub.
3. Open the folder that currently contains the published `index.html` (usually the repository root, or `docs` if configured that way).
4. Choose **Add file → Upload files**. Upload the new `index.html` to that same folder, replacing the old one. Commit the change.
5. Keep all original notebooks, CSV files, workflows, and other repository files. The other files in this ZIP are reference documentation; they are not required for the page to run.
6. Wait for the GitHub Pages deployment to finish, then reload your site. If needed, hard-refresh to clear the old page.

Do not upload the ZIP itself as the website. Upload the extracted `index.html`.

## Preview before uploading

Open `index.html` in a desktop browser. Plotly and baseline data are embedded, so the dashboard needs no build, installation, server, API key, or internet connection. Outbound evidence links require internet. The file is roughly 4.6 MB because charting is bundled for offline use.

## Included improvements

- Original navy/teal styling, equity comparisons, analyst targets and five-state analysis retained.
- Editable stock, strike, maturity, volatility, rates, dividend yield, lattice steps, bid/ask, premium and European call/put.
- Editable scenario terminal prices and weights, with sum validation.
- Recalculated CRR model, comparison charts, payoff decomposition and conclusion.
- Payoff/profit toggle with premium and expiration break-even.
- Black–Scholes Greeks with explicit units, sensitivity heatmap and bear/base/bull comparison.
- Expandable bounds, parity, probability and convergence diagnostics.
- Save/load one calculated case in browser storage; CSV/JSON downloads and print/PDF.
- Baseline JSON and analyst-target CSV download buttons.
- U.S. currency formatting and responsive layout.

## Data and model scope

Baseline data were taken from the existing public `model_results.json`, dated 2026-10-16. Baseline spot $96, strike $105, maturity 1 year, risk-free rate 4.5%, continuous dividend yield 1.2%, volatility 28%, and 200 lattice steps reproduce the published CRR price $8.3323083247. All option amounts are per share.

Quotes are supplied case inputs, not live market data. Issuer identity and external source provenance have not been independently verified. The page states that limitation explicitly rather than inventing citations. Keep the original notebook/CSVs and add verified market/analyst source citations there when available.

Analyst targets have a one-year horizon. Changing option maturity does not rescale analyst targets or scenario terminal prices; the conclusion flags that mismatch. DCF, comps, and analyst target distribution stay fixed to the original case, while scenario prices and weights can be edited.

Rates are continuously compounded annual rates. CRR supports European options, constant volatility and constant continuous dividend yield. Greeks and heatmap use Black–Scholes as a labeled benchmark. At zero volatility or expiration, the pricing engine uses deterministic/intrinsic values and hides singular analytic Greeks. Invalid CRR probabilities produce an explanatory error.

The convergence check compares the selected lattice with 1,000 steps using max($0.01, 0.5% of model price) as a diagnostic tolerance; it is not proof of convergence. Narrow CRR admissibility can invalidate some comparison cases; these are not silently priced with another model.

## Important workflow note

The new HTML embeds a snapshot of the original baseline JSON. Updating the repository's `model_results.json` alone will not update this embedded baseline. Also, if an existing notebook/workflow regenerates `index.html`, it can overwrite this update; retain a copy and update that generation step before running it again. This download does not alter your original notebook pipeline.

## Checks completed

- Baseline CRR reproduced to better than $0.0000000001.
- Call/put parity, theoretical bounds and convergence diagnostics checked.
- Call and put pricing at zero volatility and zero maturity checked.
- Invalid weight total rejected.
- Black–Scholes benchmark and finite analytic Greeks checked.
- JavaScript syntax checked.

Full visual browser QA was unavailable because the remote preview could not access the local server. Preview the downloaded HTML before committing.

## Third-party component

The single HTML bundles Plotly.js v2.35.2, copyright Plotly, Inc., under the MIT license; its copyright/license notice is retained in the embedded bundle. See https://github.com/plotly/plotly.js/blob/v2.35.2/LICENSE for the upstream license.
