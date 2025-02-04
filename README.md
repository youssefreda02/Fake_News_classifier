# Fake News Classifier 📰🤖  

A high-accuracy Fake News Classifier (F1 score: **0.9913**) built using transformer models. This project enables **real-time classification** of news articles and supports **batch inference** through a script.

## 🚀 Features  
- **High Accuracy:** Achieves an **F1 score of 0.9913** using MPNET.  
- **Comprehensive Dataset:** Combines scraped real news, LLM-generated fake articles, and Kaggle datasets.  
- **Flexible Inference:**  
  - Classify a **single article** via command line or the Streamlit app.  
  - Process **multiple articles from a CSV file** and receive structured output.  
- **Automated Testing:** Includes **unit tests** for reliability.  

## 📊 Model & Approach  
- **Data Collection:**  
  - Scraped real news articles from verified sources.  
  - Generated news using **LLMs**.  
  - Integrated additional data from **two Kaggle datasets**.  
- **Model Training:**  
  - Compared **BERT** and **MPNET**, selecting MPNET for its superior performance.  
- **Deployment:**  
  - Website using `streamlit` app for inference with either a single article or a `.csv` file. 

## 🛠 Installation & Usage  

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/youssefreda02/Fake_News_classifier.git
cd Fake-News-Classifier
```

### 2️⃣ Running the Streamlit App  
To launch the web-based classifier, use:  
```bash
streamlit run run.py
```
This will open a web interface where you can input an article and receive classification results.  

### 3️⃣ Command Line Inference  
To classify news via the command line, run:  
```bash
python start.py
```
The script will prompt you to choose:
- `single` to classify one article interactively.
- `file` to classify articles from a CSV file.

#### Input Handling:
- If an invalid choice is entered, the script will re-prompt the user.
- If the article text is empty, an error message will be displayed.
- If the csv file is empty, an error message will be displayed.
- If the csv file is not found, an error message will be displayed.
- If the csv file doesn't contain `text` column, an error message will be displayed.

#### CSV File Processing:
- The CSV file should contain a `text` column.
- When a CSV file is provided, the script adds **two new columns**:
  - **`prediction`**: The classification result (Real/Fake)
  - **`confidence`**: The model’s confidence score

#### Example CSV Format (Before Processing):
| id | title               | text               |
|----|---------------------|--------------------|
| 1  | Example Headline 1 | Example article 1 |
| 2  | Example Headline 2 | Example article 2 |

#### Example CSV Output (After Processing):
| id | title               | text               | prediction | confidence |
|----|---------------------|--------------------|------------|------------|
| 1  | Example Headline 1 | Example article 1 | Fake       | 0.98       |
| 2  | Example Headline 2 | Example article 2 | Real       | 0.95       |

## 🖼️ Streamlit App Screenshot

## 🔥 Future Enhancements  
- Implementing a **confidence score visualization**.
- Expanding the dataset for better generalization.

## 🤝 Contributing  
Contributions are welcome! Please open an issue or submit a pull request.


