# TP02 - Premier workflow CI

[![CI Pipeline](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml/badge.svg?branch=tp-02-workflow-tests)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml)

## 🎯 Objectif

Mettre en place un workflow GitHub Actions pour automatiser les tests.

## 📦 Installation

```bash
npm install
```

## 🧪 Exécuter les tests

```bash
npm test
```

## 🚀 CI/CD

Le workflow CI s'exécute automatiquement :

- À chaque push sur `main`
- À chaque pull request vers `main`

Il vérifie que tous les tests passent avant de merger du code.

## 📚 Contenu

- `app.js` : Fonctions mathématiques
- `app.test.js` : Tests unitaires
- `.github/workflows/ci.yml` : Workflow de tests automatisés
