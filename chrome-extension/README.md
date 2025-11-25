# Extension Chrome - YouTube Sentiment Analysis

## 📦 Contenu du Package

Ce dossier contient l'extension Chrome complète pour l'analyse de sentiment des commentaires YouTube.

### Fichiers Principaux

- **manifest.json** : Configuration de l'extension (permissions, scripts)
- **popup.html** : Interface utilisateur de la popup
- **popup.js** : Logique de communication avec l'API
- **content.js** : Script d'extraction des commentaires YouTube
- **style.css** : Styles de l'interface

### Documentation

- **INSTALLATION.md** : Instructions détaillées d'installation
- **USER_GUIDE.md** : Guide utilisateur complet avec exemples

## 🚀 Installation Rapide

1. Téléchargez et décompressez `chrome-extension.zip` (si applicable)
2. Ouvrez Chrome et allez sur `chrome://extensions/`
3. Activez le **Mode développeur**
4. Cliquez sur **Charger l'extension non empaquetée**
5. Sélectionnez le dossier `chrome-extension`

## 📖 Documentation

Consultez les guides détaillés :

- [Guide d'Installation](INSTALLATION.md)
- [Guide Utilisateur](USER_GUIDE.md)

## 🔧 Configuration

L'extension est préconfigurée pour utiliser l'API déployée :

```
https://has1elb-youtube-sentiment-analysis.hf.space
```

Pour modifier l'URL de l'API, éditez `popup.js` ligne 47.

## ✨ Fonctionnalités

- ✅ Analyse jusqu'à 50 commentaires simultanément
- ✅ Statistiques en temps réel (Positif/Neutre/Négatif)
- ✅ Affichage de la confiance pour chaque prédiction
- ✅ Interface moderne et responsive
- ✅ Connexion à l'API cloud (pas d'installation locale requise)

## 📊 Exemple de Résultat

```
Positive: 45%    Neutral: 30%    Negative: 25%
Analyzed 20 comments

Comment 0: Positive (98.2%)
Comment 1: Neutral (92.7%)
Comment 2: Negative (96.0%)
...
```

## 🐛 Support

En cas de problème :

1. Vérifiez que l'API est en ligne : [Health Check](https://has1elb-youtube-sentiment-analysis.hf.space/health)
2. Actualisez la page YouTube
3. Rechargez l'extension dans Chrome

## 📝 Version

Version 1.0 - Novembre 2025

## 👤 Auteur

Khaoula Rafik
