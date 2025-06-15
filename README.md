# IMDB-Sentiment-BiLSTM-DistilBERT
Comparative analysis of BiLSTM and Transformer (DistilBERT) models for sentiment classification on the IMDB movie review dataset. Includes model training, evaluation, explainability (LIME, SHAP), and a conflict score analysis for high-confidence errors.

# Sentiment Classification: BiLSTM vs Transformer (DistilBERT)
This project compares two deep learning models for binary sentiment classification on the IMDB movie reviews dataset:
- A Bidirectional LSTM (BiLSTM)
- A Transformer-based model (DistilBERT)

It includes full training, evaluation, visualization, and explainability techniques.

---

## Models Explored

### 1. BiLSTM
- Built using Keras
- Embedding + Bidirectional LSTM layers
- Trained from scratch

### 2. DistilBERT (Transformer)
- Fine-tuned from Hugging Face Transformers library
- Pretrained on a large corpus
- Faster and more memory efficient than BERT

---

## Evaluation Metrics

- **Accuracy**
- **Confusion Matrix**
- **Classification Report (Precision, Recall, F1)**
- **Confidence vs Correctness Visualization**
- **Conflict Score Analysis**

---

##  Explainability Tools

###  LIME
- Local explanations on random reviews
- Shows which words contribute to predictions

###  SHAP
- Global view of model behavior
- Feature impact visualization

---

## Conflict Score 

We define a "Conflict Score" as:

Conflict_Score = abs(Predicted_Probability - Correct_Label)

This helps identify high-confidence incorrect predictions that could be risky in real-world deployment.

Top 10 high-risk predictions are saved and visualized.

---

##  Project Structure
```
Dl_project/
├── person_a_lstm/
│ ├── bilstm.keras
│ ├── bilstm_predictions.csv
│ └── withinput.ipynb
├── person_b_bert/
│ ├── DistilBERT.ipynb
│ └── DistilBERT_Predictions.csv
└── person_c/
└── conflict_analyzer_v1.ipynb
```

---


## Outcomes
- DistilBERT performed better in accuracy and confidence.
- BiLSTM showed overconfidence in some wrong predictions.
- Conflict score and explainability tools helped identify failure modes.

---

##  How to Run
1. Run the Notebooks in Order
person_a_lstm/withinput.ipynb → Trains and evaluates the BiLSTM model
person_b_bert/DistilBERT.ipynb → Fine-tunes the DistilBERT Transformer model
person_c/conflict_analyzer_v1.ipynb → Performs model comparison, confidence analysis, and explainability using LIME & SHAP



