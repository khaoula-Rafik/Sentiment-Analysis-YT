# YouTube Sentiment Analysis · by Khaoula Rafik

[![GitHub](https://img.shields.io/badge/GitHub-khaoulaRafik-blue)](https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Space-yellow)](https://huggingface.co/spaces/khaoula2026R/khaoula-youtube-sentiment-api)

## 📋 Description du Projet

Projet MLOps complet pour l'analyse de sentiment des commentaires YouTube. Le système combine un modèle de machine learning (TF-IDF + Logistic Regression), une API FastAPI, et une extension Chrome pour analyser les commentaires directement depuis YouTube.

**Fonctionnalités principales :**
- Analyse de sentiment en temps réel (Positif/Négatif/Neutre)
- Extension Chrome intégrée à YouTube
- API REST déployée sur Hugging Face Spaces
- Pipeline MLOps complet (data → model → deployment)

## 🏗️ Architecture Technique

```
┌─────────────────┐
│  YouTube Video  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Chrome Extension │ ◄─── Extract comments
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  FastAPI (HF)   │ ◄─── POST /predict_batch
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  ML Model       │ ◄─── TF-IDF + Logistic Regression
│  (joblib)       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Results        │ ◄─── Sentiment + Confidence
└─────────────────┘
```

**Stack technique :**
- **Backend** : FastAPI, Python 3.10+
- **ML** : scikit-learn (TF-IDF Vectorizer + Logistic Regression)
- **Deployment** : Docker, Hugging Face Spaces
- **Frontend** : Chrome Extension (JavaScript)

## 🚀 Installation

### Prérequis
- Python 3.10+
- Google Chrome
- Git

### Backend

```bash
# 1. Cloner le repository
git clone https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git
cd YouTube-Sentiment-Analysis

# 2. Créer l'environnement virtuel
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # macOS/Linux

# 3. Installer les dépendances
pip install -r requirements.txt

# 4. Préparer les données et entraîner le modèle
python src/data/download_data.py
python src/data/process_data.py
python src/models/train_model.py

# 5. Lancer l'API
uvicorn src.api.main:app --reload
```

L'API sera disponible sur `http://localhost:8000/docs`

### Extension Chrome

1. Ouvrir Chrome → `chrome://extensions/`
2. Activer le **Mode développeur**
3. Cliquer sur **Charger l'extension non empaquetée**
4. Sélectionner le dossier `chrome-extension`

## 💻 Utilisation

### Via l'Extension Chrome

1. Aller sur une vidéo YouTube
2. Faire défiler pour charger les commentaires
3. Cliquer sur l'icône de l'extension
4. Cliquer sur **Analyze Comments**
5. Voir les résultats : pourcentages (cercles) + liste détaillée

### Via l'API

```python
import requests

url = "https://khaoula2026r-khaoula-youtube-sentiment-api.hf.space/predict_batch"
payload = {
    "comments": [
        {"id": "0", "text": "I love this video!"},
        {"id": "1", "text": "This is terrible"}
    ]
}

response = requests.post(url, json=payload)
print(response.json())
```

## 📊 Démonstration

### Interface Extension
- **Bouton d'analyse** : Analyse jusqu'à 50 commentaires
- **Cercles de pourcentage** : Visualisation animée (Positif/Neutre/Négatif)
- **Liste détaillée** : Chaque commentaire avec sentiment et confiance

### Métriques du Modèle
- **Accuracy** : ~90%
- **Classes** : Positive (1), Neutral (0), Negative (-1)
- **Entraînement** : GridSearchCV avec validation croisée (3 folds)

### API Endpoints
- `GET /` : Status check
- `GET /health` : Health check avec statut du modèle
- `POST /predict` : Prédiction pour un seul texte
- `POST /predict_batch` : Prédiction pour plusieurs commentaires


## 📁 Structure du Projet

```
YouTube_Sentiment_Analysis/
├── src/
│   ├── data/          # Scripts de traitement des données
│   ├── models/         # Scripts d'entraînement
│   └── api/            # Application FastAPI
├── chrome-extension/   # Extension Chrome complète
├── models/             # Modèle entraîné (.joblib)
├── data/               # Données brutes et traitées
├── Dockerfile          # Configuration Docker
└── requirements.txt    # Dépendances Python
```

## 👤 Auteur

**Khaoula Rafik**
