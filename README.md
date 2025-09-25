# Project Overview

Central banks communicate through official statements and minutes that significantly affect financial markets and economic expectations. This project applies **NLP-based sentiment analysis** to FOMC documents in order to:

- Extract and preprocess textual data from such PDF files  
- Identify and clean economic terminology using domain-specific corrections  
- Apply **Loughran–McDonald financial sentiment dictionary** for accurate sentiment classification  
- Compute n-gram level sentiment (unigrams, bigrams, trigrams)  
- Visualize sentiment trends alongside macroeconomic shocks (e.g., recessions)  

---

# Tools & Libraries

- **Python**  
- **NLP & Preprocessing:** `nltk`, `re`, `PyPDF2`  
- **Data Analysis:** `pandas`, `collections`, `datetime`  
- **Parallel Processing:** `concurrent.futures`  
- **Visualization:** `matplotlib`  
- **Domain Dictionary:** Loughran–McDonald Master Dictionary  

---

# Workflow

### 1. Data Extraction
- Parse raw FOMC PDF documents  
- Extract text and map each file to its publication date  

### 2. Text Preprocessing
- Sentence & word tokenization  
- Stopword removal and punctuation filtering  
- Domain-specific word corrections (e.g., `econ` → `economic`)  

### 3. Sentiment Scoring
- Generate unigrams, bigrams, trigrams  
- Match against Loughran–McDonald sentiment categories  
- Apply inclusion–exclusion principle for overlapping n-grams  
- Scale and standardize sentiment values  

### 4. Visualization
- Plot sentiment dynamics of selected n-grams over time  
- Overlay recession periods for macroeconomic context  

---

# Example Output

- **Excel File:** `sentiment_scores.xlsx` (standardized sentiment scores)  
- **Plots:** Time-series of selected economic terms (e.g., *credit*, *oil prices*) with shaded recession periods  

---

# 📂 Repository Structure
```
MacroShocksAnalysis-NLP/
│── test_docs/ # a very small subset of 20 out of 452 FOMC PDF documents
│── LoughranMcDonald.csv # Master dictionary
│── MacroShocks_NLP.ipynb # Main Jupyter Notebook
│── sentiment_scores.xlsx # Example output file
│── README.md # Project documentation
```
**Note:** Not all raw PDF files are not uploaded due to size and licensing constraints.
You can access them directly from the official [FOMC website](https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm).

---

# Getting Started
Clone this repository:

```bash
git clone https://github.com/hargunkour/MacroShocksAnalysis-NLP.git
cd MacroShocksAnalysis-NLP
```
Install dependencies:
```bash
pip install pandas nltk PyPDF2 matplotlib
```
Download NLTK resources (run inside Python):
```bash
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```
Place your FOMC PDF files in the data/ folder.
Open the Jupyter notebook and run all cells:
```bash
jupyter notebook MacroShocks_NLP.ipynb
```
Results will be saved as:

- sentiment_scores.xlsx (Excel file)
- Time-series plots

---

# Why this project and future improvements
By quantifying the tone of FOMC communication, this project helps researchers and analysts understand how central bank narratives evolve across macroeconomic shocks.
To further improve this project:
- Optimise fully to cut down preproceesing time for handling larger documents sets.
- Incorporate machine learning classifiers for predictive tasks for incoming years.
- Expand analysis to other central banks (ECB, BoE, etc.)  

