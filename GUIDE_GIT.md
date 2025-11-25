# Guide Git : Publication du projet

Ce document décrit ma façon de mettre en ligne ce dépôt sur GitHub sous le compte `khaoulaRafik`. Les étapes sont rédigées pour Windows PowerShell mais fonctionnent aussi sous macOS/Linux.

---

## 1. Préparer l'environnement

- Avoir un compte GitHub actif.
- Installer Git : [https://git-scm.com/downloads](https://git-scm.com/downloads).
- Ouvrir un terminal positionné à la racine du projet (ex. `C:\Users\khaoula\Desktop\YouTube_Sentiment_Analysis`).

Vérifiez que Git répond :
```bash
git --version
```

---

## 2. Créer le dépôt distant

1. Connectez-vous sur GitHub et cliquez sur **New repository**.
2. Renseignez :
   - Repository name : `YouTube-Sentiment-Analysis`
   - Description : « Sentiment analysis with FastAPI + Chrome extension »
   - Laissez vide les cases *Add README* et *.gitignore*.
3. Validez avec **Create repository** et gardez l’URL affichée, elle sera utilisée plus loin.

---

## 3. Initialiser et configurer Git en local

```bash
git init
git config --global user.name "Khaoula Rafik"
git config --global user.email "votre-email@example.com"
git status
```

---

## 4. Ajouter les fichiers et créer le premier commit

```bash
git add .
git commit -m "Premier commit : pipeline YouTube Sentiment Analysis"
```

Astuce : le `.gitignore` fourni exclut déjà `venv/`, `data/`, `models/*.joblib`, etc.

---

## 5. Lier le dépôt local au dépôt GitHub

```bash
git remote add origin https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git
git branch -M main
git push -u origin main
```

Lors du `push`, GitHub demande un identifiant et un mot de passe :

- Username : `khaoulaRafik`
- Password : un **Personal Access Token** (PAT). Créez-le depuis `Settings > Developer settings > Tokens (classic)` avec les droits `repo`.

---

## 6. Vérifier en ligne

Rendez-vous sur `https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis` et contrôlez que les fichiers (API, extension, modèles) sont présents.

---

## 7. Mettre à jour le dépôt plus tard

```bash
git status
git add .
git commit -m "Description claire de vos modifications"
git push
```

Pour consulter l’historique :
```bash
git log --oneline
```

Pour annuler un `remote origin` déjà défini :
```bash
git remote remove origin
git remote add origin https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git
```

---

## 8. Dépannage express

- **Échec du push (refs rejetées)** : `git pull origin main --allow-unrelated-histories`, résolvez les conflits puis `git push`.
- **Erreur d’authentification** : régénérez le PAT et vérifiez les scopes `repo`.
- **Branche incorrecte** : `git branch -M main` pour renommer la branche active.

---

## Ressources utiles

- Documentation officielle Git : https://git-scm.com/doc  
- Centre d’aide GitHub : https://docs.github.com  
- Questions rapides ? Ouvrez une issue sur votre dépôt ou contactez-moi.

Bon déploiement ! 🚀

