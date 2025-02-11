# Fake News Classifier 📰🤖  

A high-accuracy Fake News Classifier (F1 score: **0.9913**) built using transformer models. This project enables **real-time classification** of news articles and supports **batch inference** through a script.
## 📌 Release Notes (v1.0.0)
This is the first official release of the **Fake News Classifier**. Key features:
- **Transformer-based classifier** with high accuracy (**F1 score: 0.9913**)
- **Supports real-time inference** for single news articles
- **Automated unit tests** for validation and reliability

## 📥 Input & 📤 Output

### ✅ Supported Inputs:
- **Single news article** as a `.txt` file.

### 🔍 Output:
- **Prediction**: `"Real"`, `"Fake"`, or `None`
- **Confidence Score**: A probability value between `0.0` and `1.0`, indicating prediction confidence.

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
  - Website using `cmd` for inference with a single `String` article in a `.txt` file.  
## 📂 Files in the Repository

- `classify.py` – The main script for inference (single article).
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
Done test_empty_string passed!
.Done test_invalid_file_type passed!
.Done test_load_model_failure passed!
.Done test_non_existent_file passed!
.Done test_predict_fake passed!
.Done test_predict_real passed!
.Done test_predict_with_long_text passed!
.Done test_whitespace_string passed!
.
```

#### Input Handling:
##### 🧪 Test Cases  

### 🧪 Test Cases

| **Category**            | **Test Case**                                                  | **Expected Behavior**                                          |
|-------------------------|----------------------------------------------------------------|---------------------------------------------------------------|
| **Model Loading**       | Load a valid model                                             | Model loads successfully                                      |
|                         | Load a non-existent model directory                            | Prints error message and exits                                |
| **Text Classification** | Classify a real news article                                   | Returns `"Real"` label                                        |
|                         | Classify a fake news article                                   | Returns `"Fake"` label                                        |
|                         | Predict very short text (fewer than 40 words)                   | Returns `"None"` with confidence `0.0`                        |
|                         | Predict non-English text (non-ASCII with ration 20%)                           | Returns `"None"` with confidence `0.0`                        |
|                         | Predict punctuation/symbol-only input                          | Returns `"None"` with confidence `0.0`                        |
|                         | Predict an empty string                                        | Returns `"None"` with confidence `0.0`                        |
|                         | Predict a whitespace-only string                               | Returns `"None"` with confidence `0.0`                        |
|                         | Predict extremely long text                                    | Successfully processes and returns a valid label (`Real`, `Fake`, or `None`) |
| **File Handling**       | Provide a valid `.txt` file                                    | Returns expected classification                               |
|                         | Provide an empty `.txt` file                                   | Returns `"None"` with confidence `0.0`                        |
|                         | Provide a whitespace-only `.txt` file                          | Returns `"None"` with confidence `0.0`                        |
|                         | Provide a non-existent file                                    | Prints error message and exits                                |
|                         | Provide an unsupported file type (e.g., `.png`)                  | Prints error message and exits                                |


## 📝 Example Usage:
```bash
python classify.py text2.txt
```
#### output
```
Prediction: Real (Confidence: 1.00)
```

## 🔥 Future Enhancements
- Expanding the dataset for better generalization.

