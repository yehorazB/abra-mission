# Abra mission

A Junior Data Analyst assignment on factory images. The task is to understand the labeled data, measure a few simple image features, and flag images that may show a defective part.

## Files

- `starter.ipynb` — the analysis, in Parts A–E
- `train.csv` — 168 images with an inspector label
- `test.csv` — 72 images without a label
- `images/` — the 240 images
- `predictions.csv` — test predictions from the submitted model
- `sample_predictions.csv` — an example of the output format only
- `Junior Data Analyst.md` — the assignment brief

## How to run

Open `starter.ipynb` in this folder and run every cell from top to bottom. The folder must contain `train.csv`, `test.csv`, and `images/`.

The notebook uses pandas, NumPy, Matplotlib, Pillow, and scikit-learn. Running it writes `predictions.csv`.

## Model

The submitted model is a logistic regression on one score: how far a cropped plate is from the median normal plate at the same exposure. The threshold is 0.5. The model is fit on the 126 development images only.

An earlier logistic regression on mean brightness, contrast, and maximum local contrast is a baseline. It is not the submission.

On the 42 validation images, the submitted model detects 6 of 14 defects, with precision 54.5% and recall 42.9%. A plate that is simply brighter than its reference can cross the threshold.
