# Sentiment Analysis Pipeline

## Setup

### Option 1: Python venv
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt

### Option 2: Conda
conda create -n sentiment-env python=3.11 -y
conda activate sentiment-env
pip install -r requirements.txt

## How it works

The training script reads labeled text data from `data/train.csv`, vectorizes the text, trains a classifier, and saves the fitted model to `models/sentiment.joblib`.  
The prediction script loads this model and returns a sentiment label and probability for each input sentence passed on the command line.

## Train
python src/train.py --data data/train.csv --out models/sentiment.joblib

## Predict
python src/predict.py "I absolutely loved it" "That was awful"
# Output format: label  probability  text
# Example:
# 1    0.982    I absolutely loved it
# 0    0.015    That was awful
