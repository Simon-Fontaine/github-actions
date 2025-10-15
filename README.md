# TP04 - Sécurité avancée avec CodeQL

[![CI Pipeline](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml/badge.svg?branch=tp-04-security-codeql)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml)
[![CodeQL](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml/badge.svg?branch=tp-04-security-codeql)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/codeql.yml)

## 🎯 Objectif

Ajouter une analyse statique de code pour détecter les vulnérabilités.

## 📦 Installation

```bash
npm install
```

## 🧪 Exécuter les tests

```bash
npm test
```

## 🔒 Sécurité

### Workflow CI (`ci.yml`)

1. **Tests automatisés**
2. **GitLeaks** : Détection de secrets exposés

### Workflow CodeQL (`codeql.yml`)

3. **CodeQL** : Analyse sémantique du code

### Qu'est-ce que CodeQL détecte ?

- Injections SQL, XSS, CSRF
- Utilisation de fonctions dangereuses
- Gestion incorrecte des erreurs
- Failles de sécurité connues (CVE)
- Mauvaises pratiques de sécurité

### Quand CodeQL s'exécute-t-il ?

- À chaque push sur `main`
- À chaque pull request
- **Tous les dimanches à minuit** (détection de nouvelles vulnérabilités)

### Où voir les résultats ?

Onglet **Security > Code scanning alerts** sur GitHub

## 📚 Contenu

- `app.js` : Fonctions mathématiques
- `app.test.js` : Tests unitaires
- `.github/workflows/ci.yml` : Tests + GitLeaks
- `.github/workflows/codeql.yml` : Analyse de sécurité CodeQL
