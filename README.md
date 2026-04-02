# Age and gender distortion assignment — environment and data

## Environment

Use **Python 3** with a virtual environment, then install dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Packages included:

| Area | Packages |
|------|----------|
| Data | `pandas`, `numpy` |
| Plots | `matplotlib`, `seaborn`, `plotly` |
| Regression / inference | `statsmodels` (OLS with formula API), `scipy` |
| Pearson tables (r, CI, p, etc.) | `pingouin` (or use `scipy.stats` + manual CIs) |
| Notebook | `jupyter`, `ipykernel` |

For hover/interactive scatter plots, **Plotly** is configured; you can add **Bokeh** if you prefer (uncomment in `requirements.txt`).

## Data files (required next to the notebook)

The assignment expects these CSVs in the **same directory** as `age_gender_distortion_assignment.ipynb` (or adjust paths in your code):

| File | Used for |
|------|-----------|
| `GPT2-large-dimensions.csv` | GPT-2 Large age/gender dimensions, correlations, regression |
| `experiment_control.csv` | Image-search experiment (control) |
| `experiment_treatment.csv` | Image-search experiment (treatment) |

Those files are **not** stored in the authors’ GitHub repository; they are distributed with the paper’s replication materials.

### Option A — Google Drive (official replication bundle)

The authors’ README points to this folder for all raw data:

https://drive.google.com/drive/folders/1-4cy2gYDDRZ8tnZ6ZXES3jcwxNiNucG3

Download the folder (or the relevant CSVs inside it), then place the three files named above beside this notebook. Filenames must match what the notebook and the original R scripts use (`fig2_GPT2-large_analyses.R`, `fig3_experiment (main + SI).R` on the repo).

### Option B — Command-line download (Google Drive folder)

If you have [`gdown`](https://github.com/wkentaro/gdown) installed (`pip install gdown`), you can try mirroring the shared folder into `./data/` and copying the three CSVs up one level:

```bash
pip install gdown
gdown --folder "https://drive.google.com/drive/folders/1-4cy2gYDDRZ8tnZ6ZXES3jcwxNiNucG3" -O data
# Then copy GPT2-large-dimensions.csv, experiment_control.csv, experiment_treatment.csv
# into this directory (same folder as the notebook).
```

Large folders or permission prompts may require using the browser (Option A) instead.

### Replication code on GitHub (pinned commit)

R replication scripts (same analyses as the paper) live here; they document expected column names and file names:

- Repository: https://github.com/drguilbe/distortion_age_gender_online  
- **Pinned commit** (reproducible checkout): `757164b0301c9b353b86ba52f16e28cb6a62e1c4`

Fetch that snapshot without cloning `main`:

```bash
wget -O distortion_age_gender_online.zip \
  "https://github.com/drguilbe/distortion_age_gender_online/archive/757164b0301c9b353b86ba52f16e28cb6a62e1c4.zip"
unzip -q distortion_age_gender_online.zip
```

That archive contains the R scripts only; CSVs still come from Google Drive as above.

## Reference figures in this folder

SVG/HTML reference outputs (`correlation_heatmap_*.svg`, `age_gender_regression_plot.svg`, etc.) are for comparison; they are not a substitute for the CSVs.
