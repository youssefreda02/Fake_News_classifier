# Fake News Classifier 📰🤖  

A high-accuracy Fake News Classifier (F1 score: **0.9913**) built using transformer models. This project enables **real-time classification** of news articles and supports **batch inference** through a script.
## 📌 Release Notes (v1.0.0)
This is the first official release of the **Fake News Classifier**. Key features:
- **Transformer-based classifier** with high accuracy (**F1 score: 0.9913**)
- **Supports real-time inference** for single news articles
- **Automated unit tests** for validation and reliability

## 📥 Input & 📤 Output

### ✅ Supported Inputs:
- **Single news article** as a `.txt` file (UTF-8 encoded).


### 🎯 Model Output
The classifier provides three possible outputs:
| Prediction | Meaning |
|------------|---------|
| **Real**, (Confidence: 0.95)  | The news article is classified as real with a confidence of 95%. |
| **Fake**, (Confidence: 0.97)  | The news article is classified as fake with a confidence of 97%. |
| **None**, (Confidence: 0.00)  | The article does not meet classification conditions (see below). |

### When Does the Model Return `None`?
- **Text is too short**: Fewer than **40 words**.
- **Excessive non-ASCII characters**: More than **20%** of characters are non-ASCII (e.g., special symbols or non-Latin scripts).
- **Low Confidence**: The model's confidence score is below **0.91**.

### ⚠️ Error Handling:
- The script handles the following errors gracefully:
  - Non-existent files.
  - Invalid file types (non-`.txt` files).
  - Permission issues when reading files.
  - Non-UTF-8 encoded files.

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
  - Using `cmd` for inference with a single `String` article in a `.txt` file.  
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
|                         | Predict non-English text (non-ASCII with 20%)                           | Returns `"None"` with confidence `0.0`                        |
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
#### ✅ Valid Text
```
python classify.py real_news.txt
Prediction: Real (Confidence: 0.95)
```
```
python classify.py fake_news.txt
Prediction: Fake (Confidence: 0.97)
```

#### ⚠️ Short Text
```
python classify.py short_text.txt
Prediction: None (Confidence: 0.00)
```

#### ⚠️ Non-ASCII Content
```
python classify.py mixed_language.txt
Prediction: None (Confidence: 0.00)
```

#### ⚠️ Low Confidence
```
python classify.py uncertain_news.txt
Prediction: None (Confidence: 0.00)
```

---

## 🖥 System Requirements
- Python 3.8+
- Torch and Transformers libraries
- (Optional) CUDA-compatible GPU for faster inference

---
## 🔥 Future Enhancements
- Expanding the dataset for better generalization.
