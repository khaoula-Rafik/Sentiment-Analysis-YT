# YouTube Sentiment Analysis · by Khaoula Rafik

[![GitHub](https://img.shields.io/badge/GitHub-khaoulaRafik-blue)](https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis)

## Project Overview

I built this repository to explore an end-to-end workflow for classifying the sentiment of YouTube comments. The stack combines:

- **Data & Modeling** – Reddit comments are downloaded, cleaned, and fed into a TF-IDF + Logistic Regression pipeline tuned with GridSearchCV.
- **Serving Layer** – FastAPI wraps the model and exposes synchronous prediction endpoints.
- **User Experience** – A Chrome extension extracts comments directly on YouTube and talks to the API.
- **Deployment Target** – Everything ships inside a Docker image, making it easy to host on Hugging Face Spaces.

## Quickstart

1. **Clone & enter the repo**
   ```bash
   git clone https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git
   cd YouTube-Sentiment-Analysis
   ```
2. **Create a virtual environment**
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # macOS / Linux
   source venv/bin/activate
   ```
3. **Install the backend dependencies**
   ```bash
   pip install -r requirements.txt
   ```
4. **Prepare the dataset and model once**
   ```bash
   python src/data/download_data.py
   python src/data/process_data.py
   python src/models/train_model.py
   ```
5. **Launch the API**
   ```bash
   uvicorn src.api.main:app --reload
   ```
   Interactive docs are available at `http://localhost:8000/docs`.

## Chrome Extension in 3 Steps

1. Visit `chrome://extensions` and switch on **Developer mode**.
2. Click **Load unpacked** and select the `chrome-extension` folder.
3. Open a YouTube video, scroll through comments, then press **Analyze Comments** in the extension popup.

## Deploying on Hugging Face Spaces

1. Create a Space using the **Docker** SDK option.
2. Upload the full repository, making sure `models/sentiment_model.joblib` is present.
3. Spaces automatically builds the Dockerfile and starts the FastAPI app.
4. Update `chrome-extension/popup.js` with the Space URL so the extension hits the hosted API.

## What You Can Do Next

- Swap datasets or retrain the model with your own labels.
- Extend the API with batch analytics, logging, or monitoring.
- Customize the Chrome extension UI to match your branding.

## Author

Khaoula Rafik

