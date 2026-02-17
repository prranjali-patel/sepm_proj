# Customer Review Sentiment Analyzer (Python ML + NLP)

This project is a **Python-based ML/NLP app** that reads customer textual reviews and returns:
- **Sentiment**: Positive / Neutral / Negative
- **Numerical Rating**: 1 to 5

It uses a custom **Multinomial Naive Bayes** model (implemented from scratch) and a simple, clean web UI built with Python's built-in `http.server`.

## Features
- Clean and simple browser-based UI
- Text review input
- Sentiment output (positive / neutral / negative)
- Rating output (1–5)
- Confidence score
- Zero external dependencies

## Project files
- `app.py` - Web UI server
- `sentiment_model.py` - Training, model persistence, prediction logic, rating mapping
- `data/training_reviews.csv` - Labeled training data
- `model/sentiment_model.json` - Saved model file (auto-created)
- `requirements.txt` - Notes (no external packages needed)

## How to run

### 1) Go to project folder
```bash
cd /workspace/sepm_proj
```

### 2) (Optional) Train model manually
```bash
python sentiment_model.py
```

If the model file does not exist, it is automatically trained when you start the app.

### 3) Start the app
```bash
python app.py
```

### 4) Open in browser
Open:
```text
http://localhost:8501
```

## How to use
1. Enter a customer review in the text box.
2. Click **Analyze Review**.
3. See:
   - Sentiment: Positive/Neutral/Negative
   - Numerical rating: 1 to 5
   - Confidence percentage

## Rating mapping
- Positive sentiment:
  - confidence >= 80% -> 5
  - else -> 4
- Neutral sentiment -> 3
- Negative sentiment:
  - confidence >= 80% -> 1
  - else -> 2

## Example reviews
- `Absolutely loved this product, very useful and great quality.` -> likely Positive, 5/5
- `It is okay, nothing special.` -> likely Neutral, 3/5
- `Very disappointed, broke in one day.` -> likely Negative, 1/5
