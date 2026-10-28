# Machine Learning-Based Code Clone Detector

A student-project prototype combining:
- **Compiler Design:** Python Abstract Syntax Tree (AST) generation and normalization.
- **Machine Learning:** supervised Random Forest classification of code pairs.
- **Application domain:** Software Engineering.

## Requirements
- Python 3.10 or newer
- Internet connection for the first installation only (to install Python packages)

## Run on Windows
1. Extract this ZIP.
2. Open the extracted `code_clone_detector` folder.
3. In the folder address bar, type `cmd` and press Enter.
4. Run:

   ```bat
   python -m venv .venv
   .venv\Scripts\activate
   python -m pip install -r requirements.txt
   streamlit run app.py
   ```

5. Open the local URL printed in the terminal, usually `http://localhost:8501`.

## Run on macOS / Linux
Open Terminal and move into the extracted folder:

```bash
cd /path/to/code_clone_detector
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
streamlit run app.py
```

## How it works
1. Each code snippet is parsed with Python's built-in `ast` module.
2. AST structures are normalized to reduce sensitivity to identifier names.
3. Structural and lexical similarity features are extracted.
4. A Random Forest classifier is trained from the labeled rows in `sample_pairs.csv`.
5. The interface shows the predicted label, confidence, features, and AST representation.

## Important research limitation
The bundled CSV is a **small illustrative dataset created to demonstrate the full pipeline**. Its results must not be presented as scientifically validated performance. A real evaluation requires a larger documented dataset, careful train/test separation, duplicate/leakage checks, and reported precision, recall, F1-score, and confusion matrix. The model's displayed confidence is not a calibrated probability of semantic equivalence.

## Suggested next improvements
- Add a documented public code-clone dataset with appropriate licensing.
- Compare multiple classifiers and establish a held-out test set.
- Add a separate IR-generation component if required by the instructor.
- Add unit tests, a confusion-matrix view, and model evaluation on held-out data.
- Record limitations and the source of every dataset in the report.

## Academic integrity
Understand the code and be prepared to explain the AST, features, classifier, dataset, and evaluation. The report should describe the implementation and experiments actually performed.
