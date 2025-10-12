# NLP-lab6

This workspace contains the Lab Report Extraction System for the Lab 6 assignment. It includes a Jupyter notebook that implements OCR, rule-based and ML-based extraction, a demo UI, and a sample Flask API for serving the extractor.

Files in this repository
- `2023A7PS0548P_Prachi_Garg.ipynb` - Main Jupyter notebook implementing the pipeline, Gradio UI, and API endpoint.
- `Lab_Report_Extraction_System.ipynb` - Alternative/earlier implementation of the extraction pipeline.
- `lab_report_api.py` - Flask-based REST API wrapper for the extractor (standalone server).
- `Medical report.xlsx` - Spreadsheet containing URLs to sample lab report files used for automated download.
- `captions_and_labels.csv` - Dataset used in earlier assignment sections.
- `reviewed_extractions.jsonl` - (Generated) newline-delimited JSON file storing user-reviewed extraction records for retraining.
- `PROJECT_REPORT.md` - Two-page project report with abstract and methodology.
- `requirements.txt` - Pinned Python package list for reproducibility.

Setup (recommended)
1. Create a virtual environment (optional but recommended):

```bash
python -m venv .venv
source .venv/bin/activate
```

2. Install dependencies (using pinned `requirements.txt`):

```bash
pip install -r requirements.txt
```

3. (Optional) Install the spaCy model if not present:

```bash
python -m spacy download en_core_web_sm
```

How to run the notebook
- Open `2023A7PS0548P_Prachi_Garg.ipynb` in JupyterLab or VS Code and run cells in order. Start with the cells that install/import packages, then the file-download cell, then the extraction cells, and finally the Gradio UI cells to launch the demo.

Run the Flask API (standalone)
- Start the API (ensure dependencies are installed):

```bash
python lab_report_api.py
```

The API will start on the configured host/port and accept file uploads to return JSON extractions.

Notes and caveats
- OCR quality affects extraction. For low-quality scans consider pre-processing images.
- The regex patterns may need tuning for new report formats; the notebook includes editable patterns and instructions on retraining the NER model with reviewed data.

Contact
- For questions about running the code, reply here or open an issue in the repository if it's hosted on GitHub.