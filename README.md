<div align="center">

# 📊 Sentelligence

### Multi-Source Sentiment Intelligence System with Shock Detection

**A Big Data Analytics pipeline using Apache Spark, TF-IDF NLP, and 4 ML models + LSTM Deep Learning for real-time sentiment analysis across Amazon, Twitter & Financial News**

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Apache Spark](https://img.shields.io/badge/Apache_Spark-PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)](https://spark.apache.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-LSTM-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

## 🔍 Overview

**Sentelligence** is a full-stack Big Data sentiment analytics platform that processes **2M+ text records** from three diverse sources using a **Medallion Architecture** (Bronze → Silver → Gold) powered by Apache Spark. It combines traditional ML models with LSTM deep learning to classify sentiment and detect sentiment shocks across domains.

### Data Sources

| Source | Records | Type |
|--------|---------|------|
| 🛒 **Amazon Fine Food Reviews** | ~568K | Product reviews (1-5 stars) |
| 🐦 **Twitter Sentiment140** | 1.6M (sampled 200K) | Social media tweets |
| 📰 **Financial Phrase Bank** | ~4.8K | Financial news sentences |

---

## ✨ Key Features

- 🏗️ **Medallion Architecture** — Bronze (raw CSV) → Silver (Spark cleaning + TF-IDF) → Gold (ML models + analytics)
- ⚡ **Apache Spark (PySpark)** — Distributed processing with Hive-compatible SQL queries
- 🧮 **TF-IDF NLP Pipeline** — Tokenize → Stopwords Removal → CountVectorize → IDF
- 🤖 **4 ML Models** — Logistic Regression, Naive Bayes, SVM, Random Forest
- 🧠 **LSTM Deep Learning** — Keras sequential model with embedding + dropout
- 📈 **Sentiment Shock Detection** — Identifies sudden sentiment shifts across data sources
- 🖥️ **Interactive Dashboard** — Beautiful web-based analytics visualization with Chart.js

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────┐
│                   BRONZE LAYER                       │
│         Google Drive (Raw CSV Storage)               │
│   Amazon Reviews │ Twitter │ Financial Phrase Bank   │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│                   SILVER LAYER                       │
│              Apache Spark (PySpark)                  │
│   Text Cleaning │ Label Creation │ TF-IDF Features  │
│   Tokenize → Stopwords → CountVectorize → IDF      │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│                    GOLD LAYER                        │
│                                                      │
│   Spark SQL (Hive)     ML Models        LSTM         │
│   ┌──────────────┐   ┌───────────┐   ┌──────────┐  │
│   │ Analytical   │   │ LR │ NB   │   │ Embedding│  │
│   │ Queries      │   │ SVM │ RF  │   │ + LSTM   │  │
│   │ + Shock Det. │   │ (TF-IDF)  │   │ + Dense  │  │
│   └──────────────┘   └───────────┘   └──────────┘  │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│              VISUALIZATION LAYER                     │
│   Interactive Dashboard │ Charts │ Shock Detection  │
└─────────────────────────────────────────────────────┘
```

---

## 🤖 Models & Results

### Traditional ML Models (Spark MLlib + TF-IDF)

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | ~87% | ~87% | ~87% | ~87% |
| Naive Bayes | ~82% | ~83% | ~82% | ~82% |
| SVM (LinearSVC) | ~87% | ~87% | ~87% | ~87% |
| Random Forest | ~84% | ~84% | ~84% | ~84% |

### LSTM Deep Learning (Keras)

| Metric | Value |
|--------|-------|
| Architecture | Embedding → LSTM → Dropout → Dense |
| Test Accuracy | ~86% |
| Training Data | Combined multi-source corpus |

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| **Big Data Engine** | Apache Spark (PySpark) |
| **SQL Analytics** | Spark SQL (Hive-compatible) |
| **NLP Pipeline** | TF-IDF (Tokenizer + CountVectorizer + IDF) |
| **ML Models** | Spark MLlib (LR, NB, SVM, RF) |
| **Deep Learning** | TensorFlow / Keras (LSTM) |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Chart.js, Matplotlib, Seaborn |
| **Dashboard** | HTML / CSS / JavaScript |
| **Storage** | Google Drive (Bronze layer) |

---

## 📁 Project Structure

```
Sentelligence/
├── Sentelligence_Pipeline.py         # Full PySpark + ML + LSTM pipeline
├── sentelligence.html                # Interactive web dashboard
├── README.md
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pyspark tensorflow pandas numpy matplotlib seaborn
```

### Running the Pipeline

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Arnavs10/Sentelligence.git
   cd Sentelligence
   ```

2. **Run the pipeline** (designed for Google Colab):
   - Upload `Sentelligence_Pipeline.py` to [Google Colab](https://colab.research.google.com)
   - Upload the datasets to Google Drive under `/BDA_Project/`
   - Run all cells

### Viewing the Dashboard

Simply open `sentelligence.html` in any modern browser — no server required!

Or visit the live version: [**arnavs10.github.io/Sentelligence**](https://arnavs10.github.io/Sentelligence/)

---

## 📊 Datasets Used

| Dataset | Source | Size |
|---------|--------|------|
| [Amazon Fine Food Reviews](https://www.kaggle.com/snap/amazon-fine-food-reviews) | Kaggle | ~568K reviews |
| [Twitter Sentiment140](https://www.kaggle.com/kazanova/sentiment140) | Kaggle | 1.6M tweets |
| [Financial Phrase Bank](https://www.kaggle.com/ankurzing/sentiment-analysis-for-financial-news) | Kaggle | ~4.8K sentences |

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Arnav Shukla**  
GitHub: [@Arnavs10](https://github.com/Arnavs10)

---

*Built as part of Big Data Analytics & Business Intelligence (CSET-340)*
