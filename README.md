# BankMind Challenge — Track B (ML Engineer)

Predicting whether a bank customer will subscribe to a term deposit, using the UCI Bank Marketing dataset.

## What's in this repo

- `bankmind_track_b.ipynb` — the full notebook: EDA, encoding, training, evaluation, feature importance, and 5 sample predictions
- `model.pkl` — the trained Random Forest model (saved with `joblib`)
- `encoders.pkl` — the `LabelEncoder` objects used for each categorical column (needed to encode new data the same way)
- `target_encoder.pkl` — the encoder for the target column (`no`/`yes`)
- `EXPLANATION.md` — answers to the screening task's required questions
- `requirements.txt` — Python dependencies

## How to run it

1. Download `bank-full.csv` from the [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing) and place it in this folder (not included in the repo due to size/licensing — just drop it in next to the notebook).

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:
   ```bash
   jupyter notebook bankmind_track_b.ipynb
   ```
   Or run all cells from the command line:
   ```bash
   jupyter nbconvert --to notebook --execute bankmind_track_b.ipynb --output bankmind_track_b.ipynb
   ```

This will reproduce the EDA, retrain both models, regenerate all plots, and re-save `model.pkl`.

## Models trained

| Model | Accuracy | F1 (weighted) | Recall on "yes" |
|---|---|---|---|
| Logistic Regression (baseline) | 0.80 | 0.83 | 0.81 |
| Random Forest (main) | 0.85 | 0.87 | 0.83 |

Full classification reports and discussion are in the notebook and `EXPLANATION.md`.
