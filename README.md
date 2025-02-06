# Fake News Classifier 📰🤖  

A high-accuracy Fake News Classifier (F1 score: **0.9913**) built using transformer models. This project enables **real-time classification** of news articles and supports **batch inference** through a script.
## 📌 Release Notes (v1.0.0)
This is the first official release of the **Fake News Classifier**. Key features:
- **Transformer-based classifier** with high accuracy (**F1 score: 0.9913**)
- **Supports real-time inference** for single news articles
- **Batch classification** using CSV files
- **Automated unit tests** for validation and reliability

## 📥 Input & 📤 Output
### ✅ Supported Inputs:
- **Single news article** (string)

### 🔍 Output:
- **Prediction**: `Real` or `Fake`
- **Confidence Score**: Probability of prediction accuracy (0.0 - 1.0)

## 🚀 Features  
- **High Accuracy:** Achieves an **F1 score of 0.9913** using MPNET.  
- **Comprehensive Dataset:** Combines scraped real news, LLM-generated fake articles, and Kaggle datasets.  
- **Flexible Inference:**  
  - Classify a **single article** via command line.  
- **Automated Testing:** Includes **unit tests** for reliability.  

## 📊 Model & Approach  
- **Data Collection:**  
  - Scraped real news articles from verified sources.  
  - Generated news using **LLMs**.  
  - Integrated additional data from **two Kaggle datasets**.  
- **Model Training:**  
  - Compared **BERT** and **MPNET**, selecting MPNET for its superior performance.  
- **Deployment:**  
  - Website using `cmd` for inference with either a single article or a `.csv` file.  
## 📂 Files in the Repository

- `start.py` – The main script for inference (single article).
- `unit_test.py` – Contains automated tests for model validation.
- `requirements.txt` – Lists all dependencies needed to run the project.
- `saved_model/` – Contains the trained model and tokenizer files.

## 🛠 Installation & Usage  

### 1️⃣ Install the requirements 
```bash
pip install -r requirements.txt
```
## 2️⃣ Running Unit Tests  
To verify the functionality and accuracy of the model, **unit tests** are included. Run them with:  
```bash
python -m unittest unit_test.py
```
After all tests are executed, a success message will be printed for each passed test.
Example output:
```bash
✅ test_predict_real passed!
✅ test_predict_fake passed!
✅ test_empty_string passed!
✅ test_whitespace_string passed!
✅ test_non_string_input passed!
✅ test_empty_csv_file passed!
✅ test_csv_without_text_column passed!
✅ test_invalid_csv_format passed!
✅ test_non_existent_csv_file passed!
```

### 3️⃣ Command Line Inference  
To classify news via the command line, run:  
```bash
python start.py
```
The script will prompt you to choose:
- `q` to Exit.
- (Any text) to be classified.

#### Input Handling:
##### 🧪 Test Cases

The following test scenarios are covered in the unit tests:

| **Category**           | **Test Case**                                             | **Expected Behavior** |
|-----------------------|--------------------------------------------------------|----------------------|
| **Model Loading**     | Load a valid model                                      | Model loads successfully |
|                      | Load a non-existent model                               | Raises `RuntimeError` |
| **Text Classification** | Classify real news                                   | Returns `"Real"` label |
|                      | Classify fake news                                    | Returns `"Fake"` label |
|                      | Predict empty string                                  | Returns `"Invalid input"` with confidence `0.0` |
|                      | Predict whitespace string                             | Returns `"Invalid input"` with confidence `0.0` |
|                      | Predict non-string input (e.g., integer)              | Raises `ValueError` |
|                      | Predict extremely long text                           | Successfully processes and classifies |


## 🔥 Future Enhancements
- Expanding the dataset for better generalization.

