# Apple Case 4 and 5 revisions

- Original model: The unchanged uploaded notebook is archived in model_history. It constructs the five analyst states, discounts their payoffs, and validates CRR pricing.
- Improvement: The dashboard consumes the notebook-generated JSON instead of displaying embedded Asteron data. The model now also shows the selected American contract and the corresponding European lattice side by side across the five specified step counts.
- Module 5: Added analytic European benchmark Greeks, central finite differences and a half-bump check, contract-level exposure, full repricing under spot and combined shocks, and interactive Plotly Greek curves. The original Python cells and assertions remain in the extended notebook.
