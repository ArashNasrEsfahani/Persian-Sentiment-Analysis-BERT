# Persian Sentiment Analysis: Comparing ParsBERT vs. Multilingual BERT 🤖📝

**📚 Course:** Natural Language Processing
**🏛️ Institution:** University of Tehran – Faculty of Mathematics, Statistics, and Computer Science

---

## 🔍 Project Overview

This project presents a comparative analysis of two transformer-based models for **sentiment analysis in Persian**:

*  **ParsBERT**: A Persian-specific language model.
*  **Multilingual BERT**: A general-purpose multilingual model.

The goal is to **demonstrate the advantage of using a domain-specific model** for tasks in a specific language. I also evaluate how ll each model generalizes to **out-of-domain data**.

📓 The full implementation is available in `Sentiment_Analysis_in_Persian.ipynb`.

---

## 🧪 Methodology

### 1️⃣ Models Used

Two pre-trained models from the 🤗 Hugging Face Hub:

* 🟣 **ParsBERT**: `HooshvareLab/bert-fa-base-uncased` — specifically trained on a massive Persian corpus.
* 🔵 **Multilingual BERT**: `bert-base-uncased` — trained on 104 languages.

### 2️⃣ Fine-Tuning 🔧

Both models were fine-tuned on the **Snappfood dataset** 🍔, which contains:

* **7,000 Persian user reviews**
* Binary labels: Positive (1) / Negative (0)

### 3️⃣ Generalization Test 🌍

To test robustness, both models are evaluated on a new, unseen dataset evaluated:

* 📦 **Digikala product reviews**
* **6,910 reviews**, different domain
* Tests each model’s ability to **generalize learned sentiment patterns**

---

## 📊 Results

### ✅ In-Domain: Snappfood Validation Set

ParsBERT outperformed the multilingual BERT across all metrics.

| 🧠 Model     | ✅ Accuracy | 🎯 F1-Score | 📈 AUC   |
| ------------ | ---------- | ----------- | -------- |
| **ParsBERT** | **86.01%** | **86.00%**  | **0.97** |
| BERT         | 82.36%     | 82.28%      | 0.90     |


---

### 🌐 Out-of-Domain: Digikala Test Set

The gap widened in the generalization test. ParsBERT’s Persian-specific knowledge proved essential.

| 🧠 Model     | ✅ Accuracy | 🎯 F1-Score | 📈 AUC    |
| ------------ | ---------- | ----------- | --------- |
| **ParsBERT** | **93.13%** | **93.11%**  | **0.976** |
| BERT         | 80.59%     | 81.22%      | 0.905     |


---

## 🧠 Conclusion

The experiments **strongly validate the effectiveness of domain-specific language models**:

> ✅ **ParsBERT significantly outperforms** the generic multilingual BERT in both in-domain and out-of-domain scenarios.

* 📌 Language-specific pre-training matters.
* 💡 ParsBERT generalizes better across domains.
* 🚀 For Persian NLP, ParsBERT is clearly the better choice for real-world applications.

---

## ⚙️ How to Run

### 🌀 Step 1: Clone the repository

```bash
git clone https://github.com/ArashNasrEsfahani/Persian-Sentiment-Analysis-BERT
cd Persian-Sentiment-Analysis-BERT
```

### 🧱 Step 2: Set up the environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 📒 Step 3: Launch the notebook

```bash
jupyter lab Sentiment_Analysis_in_Persian.ipynb
```

