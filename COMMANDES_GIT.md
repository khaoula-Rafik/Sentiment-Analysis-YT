# Commandes Git rapides

Ce pense-bête liste les instructions que j’utilise dans PowerShell pour publier `YouTube-Sentiment-Analysis` sur mon compte GitHub `khaoulaRafik`. Copiez/collez les blocs selon vos besoins.

---

## 1. Préparer le dossier

```powershell
cd C:\Users\khaoula\Desktop\YouTube_Sentiment_Analysis
git init
git config --global user.name "Khaoula Rafik"
git config --global user.email "votre-email@example.com"
```

## 2. Créer le dépôt sur GitHub

- Ouvrez `https://github.com/new`.
- Nom : `YouTube-Sentiment-Analysis`.
- Laissez les cases README / .gitignore décochées.
- Cliquez sur **Create repository** et gardez l’URL.

## 3. Premier commit local

```powershell
git add .
git commit -m "Initialisation du projet YouTube Sentiment Analysis"
```

## 4. Relier et pousser vers GitHub

```powershell
git remote add origin https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git
git branch -M main
git push -u origin main
```

Lors du `push` :

- Username : `khaoulaRafik`
- Password : Personal Access Token (PAT) généré avec le scope `repo`.

## 5. Mise à jour quotidienne

```powershell
git status
git add .
git commit -m "Ce que vous avez changé"
git push
```

## 6. Problèmes connus

| Situation | Commandes |
|-----------|-----------|
| `remote origin already exists` | `git remote remove origin` puis `git remote add origin https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis.git` |
| `failed to push some refs` | `git pull origin main --allow-unrelated-histories` puis `git push` |
| Auth échoue | Générer un nouveau PAT, vérifier qu’il inclut `repo` |

## 7. Vérification finale

Après chaque publication, aller sur `https://github.com/khaoulaRafik/YouTube-Sentiment-Analysis` et confirmer que les derniers commits sont visibles.

---

Pour une version commentée de chaque étape, consultez `GUIDE_GIT.md`. Bonne contribution ! 🚀

