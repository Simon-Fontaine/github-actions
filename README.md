# TP05 - Configuration sécurisée avec variables d'environnement

[![CI Pipeline](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml/badge.svg)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml)
[![CodeQL](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml/badge.svg)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml)

## 🎯 Objectif

Apprendre à gérer les secrets de manière sécurisée avec les variables d'environnement.

## 📦 Installation

```bash
npm install
```

## 🔐 Configuration

### Localement (développement)

1. Copier `.env.example` vers `.env` :

```bash
cp .env.example .env
```

2. Modifier `.env` avec vos vraies valeurs :

```bash
API_KEY="votre_vraie_clé_api"
```

⚠️ Le fichier `.env` est dans `.gitignore` et ne sera JAMAIS commité !

### GitHub Actions (CI/CD)

1. Aller dans **Settings > Secrets and variables > Actions**
2. Cliquer sur **New repository secret**
3. Nom : `API_KEY`
4. Valeur : votre clé API réelle

### Dans le workflow

```yaml
- name: Run app
  run: npm start
  env:
    API_KEY: ${{ secrets.API_KEY }}
```

## 🧪 Exécuter les tests

```bash
npm test
```

## 🔒 Sécurité

### ✅ Bonnes pratiques appliquées

- Variables d'environnement pour tous les secrets
- `.gitignore` configuré pour exclure les fichiers `.env`
- `.env.example` comme template (sans valeurs sensibles)
- Aucun secret en clair dans le code source

### ❌ À ne JAMAIS faire

```javascript
// ❌ DANGER !
const API_KEY = "sk-prod-abc123def456";
```

### Pourquoi c'est dangereux ?

1. Le token reste dans l'historique Git (PERMANENT)
2. Visible par tous ceux qui ont accès au dépôt
3. GitLeaks détectera cette faille
4. Impossible à révoquer sans modifier le code

## 📚 Contenu

- `app.js` : Fonctions mathématiques
- `app.test.js` : Tests unitaires
- `config.js` : **Configuration sécurisée avec variables d'environnement**
- `.env.example` : Template de configuration
- `.gitignore` : Exclusion des fichiers sensibles
- `.github/workflows/ci.yml` : Tests + GitLeaks
- `.github/workflows/codeql.yml` : Analyse CodeQL
