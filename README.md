# Document AI – Structured Data Extraction from Documents

Automated extraction of structured information from semi-structured documents using OCR, layout detection, and rule-based post-processing.

This project converts scanned documents into **machine-readable structured data**, enabling automation of document processing workflows.

---

# Project Overview

Many business processes rely on documents such as:

* vehicle registration documents
* invoices
* insurance forms
* certificates
* identification records

These documents contain valuable information but exist only as **images or PDFs**.

This project builds a **Document AI pipeline** that extracts key fields from such documents and converts them into structured output.

Example extracted fields include:

* License plate number
* Owner name
* Address
* Vehicle type
* Vehicle model
* VIN number
* Birth date
* Insurance company
* Color
* Registration number

---

# Example Result

Below is an example of the system extracting structured fields from a vehicle registration document.

![cover.png)

The pipeline identifies relevant regions, extracts text, and maps the information into structured fields.

---

# Pipeline Architecture

The system follows a multi-stage document intelligence workflow:

1️⃣ **Input Document**

* Scanned document or image

2️⃣ **Preprocessing**

* Image cleanup
* Noise reduction
* resizing / normalization
* preparing document for OCR

3️⃣ **OCR Extraction**

* text detection
* text recognition

4️⃣ **Field Detection**

* identifying key-value regions
* mapping extracted text to structured fields

5️⃣ **Post Processing**

* text normalization
* rule-based validation
* formatting corrections

6️⃣ **Structured Output**

Example output:

```json
{
  "license_plate": "ZH 569 737",
  "owner_name": "Pena Fraga Andres",
  "address": "Felsenkellerstrasse 23, 8636 Wald ZH",
  "vehicle_type": "Leichter Motorwagen",
  "vehicle_model": "FIAT LMC Liberty A 561 G",
  "vin": "ZFA 250 000 0103 0868",
  "birth_date": "1986-12-12",
  "insurance": "Zurich",
  "vehicle_color": "weiss / grau"
}
```

---

# Tech Stack

Python
OpenCV – image preprocessing
OCR – text recognition (Tesseract / EasyOCR / PaddleOCR)
NumPy / Pandas – data processing
Custom extraction logic – field detection & validation

---

# Project Structure

```
document-ai-extraction/
│
├── data/
│   ├── sample_documents
│
├── notebooks/
│   └── docAI.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── ocr_pipeline.py
│   ├── extraction_logic.py
│
├── assets/
│   └── doc_ai_example.png
│
├── requirements.txt
└── README.md
```

---

# Installation

Clone repository

```bash
git clone https://github.com/MuntahaShams/document-ai-extraction.git
cd document-ai-extraction
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# Running the Project

Run the notebook:

```
docAI.ipynb
```

Or run extraction on a document:

```bash
python extract.py --input sample_document.png
```

---

# Challenges in Document AI

Some challenges addressed in this project:

* noisy scans
* inconsistent document layouts
* OCR recognition errors
* multilingual fields
* varying formats across documents

---

# Possible Improvements

Future enhancements include:

* layout-aware models (LayoutLM / Donut)
* key-value detection models
* table extraction
* confidence scoring
* human-in-the-loop validation UI
* API deployment

---

# Author

Muntaha Shams
AI Engineer – LLMs | NLP | Computer Vision | Document AI

GitHub
[https://github.com/MuntahaShams](https://github.com/MuntahaShams)

Portfolio
[https://muntahashams.github.io/portfolio/projects](https://muntahashams.github.io/portfolio/projects)

---
