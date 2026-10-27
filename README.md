# Alibi Explainability for Retail Banking

## Project
**Evaluating Alibi-based explanations for retail banking campaign predictions**

The project uses the UCI Bank Marketing dataset to predict whether a customer subscribed to a term deposit. It demonstrates:
1. A Random Forest baseline and held-out evaluation.
2. Alibi `AnchorTabular` local rule explanations.
3. A constraint-aware nearest-observed-example counterfactual baseline.
4. Permutation feature importance as a global diagnostic.

## Dataset
Download `bank-full.csv` from the official [UCI Bank Marketing dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing). Place it at `data/bank-full.csv` (semicolon-separated). If the file is not present, the script attempts to download the official UCI archive automatically.

The script excludes `duration` because it is only known after a marketing call and can leak information about the outcome. The dataset is marketing campaign data; it is not a credit-scoring dataset.

## Run
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
python alibi_retail_banking.py
```

Outputs are written to `artifacts/`:
- `confusion_matrix.png`
- `permutation_importance.png`
- `test_metrics.csv`
- `permutation_importance.csv`

## Important implementation note
Alibi's `AnchorTabular` explainer is used for model-agnostic local rules. The counterfactual component is deliberately implemented as a transparent, constraint-aware search over observed training examples. It is **not** Alibi's built-in `CounterfactualRLTabular` algorithm. This makes the demo easier to reproduce and allows explicit immutability constraints, while keeping the distinction honest.

## Responsible-use notes
- Use explanations for analysis, not as automatic customer decisions.
- The dataset reflects a specific historical Portuguese bank marketing campaign.
- Do not interpret predictive patterns as causal effects.
- Never recommend changing immutable personal attributes.
- Evaluate group performance and fairness before any real deployment.
