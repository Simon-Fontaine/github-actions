# TP06 - Token leaked (GitLeaks échouera)

[![CI Pipeline](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml/badge.svg?branch=tp-06-demo-leak)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml)
[![CodeQL](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml/badge.svg?branch=tp-06-demo-leak)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml)

## 🎯 Objectif

Comprendre comment GitLeaks détecte les fuites de secrets et pourquoi ne jamais commiter de tokens.

## 🔴 Résultat attendu

Le workflow CI va **ÉCHOUER** à l'étape GitLeaks car un secret est détecté dans le code.

## 🔍 Comment analyser

1. Allez dans l'onglet **Actions**
2. Cliquez sur le workflow échoué (rouge)
3. Regardez les logs de l'étape "Security Scan"
4. GitLeaks indique le fichier et la ligne du secret

## ✅ Comment corriger

```javascript
// ❌ MAUVAIS
const API_KEY = "sk-prod-abc123def456ghi789jkl";

// ✅ BON
const API_KEY = process.env.API_KEY;
```

Ensuite, ajoutez votre clé dans **GitHub Secrets** :  
Settings > Secrets and variables > Actions

## 📚 Contenu

- `app.js` : Fonctions mathématiques
- `app.test.js` : Tests unitaires
- `config.js` : **⚠️ VERSION VULNÉRABLE avec secret exposé (pour démonstration)**
- `.env.example` : Template de configuration
- `.gitignore` : Exclusion des fichiers sensibles
- `.github/workflows/ci.yml` : Tests + GitLeaks
- `.github/workflows/codeql.yml` : Analyse CodeQL
