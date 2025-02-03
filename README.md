# Fake News Classifier 📰🤖  

A high-accuracy Fake News Classifier (F1 score: **0.9913**) built using transformer models and deployed within **PostgreSQL** via the `pgml` extension. This project enables **real-time classification** of news articles and supports **batch inference** through a script.

## 🚀 Features  
- **High Accuracy:** Achieves an **F1 score of 0.9913** using MPNET.  
- **Comprehensive Dataset:** Combines scraped real news, LLM-generated fake articles, and Kaggle datasets.  
- **Efficient Deployment:** Runs directly within **PostgreSQL** using `pgml` for seamless inference.  
- **Flexible Inference:**  
  - Classify a **single article** via script.  
  - Process **multiple articles from a CSV file**.  
- **Automated Testing:** Includes **unit tests** for reliability.  

## 📊 Model & Approach  
- **Data Collection:**  
  - Scraped real news articles from verified sources.  
  - Generated fake news using **LLMs**.  
  - Integrated additional data from **two Kaggle datasets**.  
- **Model Training:**  
  - Compared **BERT** and **MPNET**, selecting MPNET for its superior performance.  
- **Deployment:**  
  - Hosted directly inside **PostgreSQL** using the `pgml` extension for efficient **in-database inference**.  

## 🛠 Installation & Usage  

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/YOUR_USERNAME/Fake-News-Classifier.git
cd Fake-News-Classifier
```
