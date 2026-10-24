# EDA Notebook: Task Breakdown (3 days)

Deliverable: ONE Jupyter notebook that (1) loads data + overview, (2) checks data quality with brief notes, (3) plots key distributions + correlation heatmap, (4) runs top-to-bottom with no edits.

The starter notebook has sections 0-6. Each has an "Owner" line to fill in.

## A. Repo and setup (do first, everyone depends on it)
1. Create the GitHub repo (SFU GitHub), add instructor + TAs as collaborators: `ester`, `aka400`, `jgd5`.
2. Push starter notebook, `README.md`, `.gitignore` (ignore `data/`), `requirements.txt`.
3. Agree on branch naming (`feature/<name>-<section>`), one PR per section, merge one at a time, pull main before opening a PR.
4. Confirm the final list of 20 features in the Section 0 config cell (currently a proposal), plus the leakage and dropped columns.
5. Confirm data loading works in Colab AND Kaggle with no edits (kagglehub downloads the 500k sample file).

## B. Notebook sections
**Section 1: Overview**
- shape, dtypes, memory, head(), describe(), time span
- table of the 20 features by type; list leakage columns

**Section 2: Target and class balance**
- binary target (severity 4 vs 1-3), counts and %
- original 4-level distribution
- positive rate by year (proposal says it shifts a lot)
- derive hour / day of week / month / year

**Section 3: Data quality**
- missing % per column (table + bar chart), missing features per row
- duplicates (ID, full row, features + time)
- constant columns, high-cardinality columns
- one short note per issue on how we'll handle it later

**Section 4: Distributions**
- histograms for numeric features, box plots split by target
- top categories (weather condition, state, day/night)
- boolean road features: % True and severity-4 rate when True vs False
- severity-4 rate by hour, day of week, month

**Section 5: Correlation**
- heatmap (numeric + boolean + time features + target)
- list pairs with |r| > 0.7
- correlation of each feature with the target

**Section 6: Key insights and challenges** (whole team, after merging)
- imbalance, missingness, leakage, correlated features, skew/outliers, implications for preprocessing

## C. Written notes (must be our own words, not LLM-written)
- Each owner writes the Notes cell of their own section AFTER looking at the real plots.
- Section 6 is written together.
- Code can be AI-assisted, prose cannot (GPTZero screening). If unsure whether notebook notes count, ask a TA.

## D. Integration and QA (Day 3)
1. Pull everything into main, resolve conflicts (edit different cells, avoid reformatting others' cells).
2. Restart kernel + Run All in a fresh Colab session (and Kaggle if possible). Fix any path or version errors.
3. Check: no hardcoded local paths, seed set, outputs kept (do NOT clear), notebook renders on GitHub.
4. README has clear run instructions for the TAs.
5. Everyone reviews the final notebook so each person can explain every section.
6. Submit with a buffer before the deadline.

## E. Rules to remember
- Every member must commit their own work (use your own branch and PRs).
- Keep cell outputs in the committed .ipynb.
- Select only essential charts; the later report should not include everything.

## F. Coming up next (so we plan ahead)
- Preprocessing: missing values + outliers, scaling, encoding, independent feature selection, PCA/t-SNE if needed
- Final delivery: clustering (1 algorithm per member), outlier detection (1 per member), feature selection, classification (1 per member, 80/20 split + CV, metrics, ROC/confusion matrix), hyperparameter tuning before/after
- Final report max 4 pages, in our own words
