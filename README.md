# Text Classification Guest Lecture

A 70-minute online guest lecture on **Text Classification** delivered online.

6/5/2026 - First run - for a subject at BINUS University, Indonesia, for the *Text Mining* course.
- The lecture builds, evaluates, and explains a sentiment classifier for Indonesian product reviews — using the [SmSA dataset from IndoNLU](https://github.com/IndoNLP/indonlu/tree/master/dataset/smsa_doc-sentiment-prosa).

## What's in this repo

| File | Description |
|---|---|
| `Text_Classification_BINUS_GuestLecture.pptx` | slide deck with speaker notes (16:9 widescreen) |
| `text_classification_indonesian.ipynb` | Live-walkthrough Jupyter notebook (the core artefact) |

## What the lecture covers

- Building a text classification system with `scikit-learn` (Pipeline + TF-IDF + Logistic Regression)
- Indonesian-specific preprocessing with [Sastrawi](https://github.com/har07/PySastrawi) (stemming + stopwords)
- Stratified K-fold cross-validation
- Reading model coefficients to find spurious correlations
- Hyperparameter tuning with `GridSearchCV`
- Local explanations with [LIME](https://github.com/marcotcr/lime), connecting to last week's coverage of Anchors

## Quick start

```bash
# 1. Clone and enter
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# 2. Create a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate          # macOS / Linux
# .venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install scikit-learn sastrawi lime matplotlib pandas seaborn jupyter

# 4. Launch the notebook
jupyter notebook text_classification_indonesian.ipynb
```

The notebook downloads the SmSA TSV files directly from the IndoNLU GitHub repo (no `datasets` library required). If your network blocks `raw.githubusercontent.com`, manually download the three TSVs from the [SmSA folder](https://github.com/IndoNLP/indonlu/tree/master/dataset/smsa_doc-sentiment-prosa) and point the `BASE` variable at your local path.

## Performance note

Sastrawi is pure-Python and slow. To avoid waiting 10+ minutes on `pipe.fit()`, the notebook caches stemming results with `joblib.Memory` so repeated runs are nearly instant.

## Learning outcomes

The lecture maps to three Bloom levels from the syllabus:

- **C2 (Comprehension)** — explain what each pipeline component does
- **C3 (Application)** — apply scikit-learn end-to-end on Indonesian text
- **C4 (Analysis)** — interpret confusion matrices, coefficients, and LIME outputs

## Acknowledgements

- **IndoNLU benchmark** — Wilie, B. et al. *"IndoNLU: Benchmark and Resources for Evaluating Indonesian Natural Language Understanding"*, AACL 2020. Dataset licensed under MIT.
- **Sastrawi** — Indonesian stemmer by Andy Librian and contributors.
- **LIME** — Ribeiro, M.T., Singh, S., Guestrin, C. *"Why Should I Trust You? Explaining the Predictions of Any Classifier"*, KDD 2016.
- **Anchors** — Ribeiro, M.T., Singh, S., Guestrin, C. *"Anchors: High-Precision Model-Agnostic Explanations"*, AAAI 2018.
- Original BINUS *Text Mining* course materials (Session 8–9) prepared by **Lili Ayu Wulandhari, S.Si., M.Sc., Ph.D.**
- contents (slide deck, accompanying jupyter notebook) are generated via Claude.ai agent, checked and tested by me. 

## License

The teaching materials in this repository are released under the **MIT License**. The SmSA dataset is licensed separately under MIT by IndoNLU.

---

*Lecture delivered May 2026 · BINUS University, Jakarta*
