# TP02 - Premier workflow CI

[![CI Pipeline](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml/badge.svg)](https://github.com/Simon-Fontaine/github-actions/actions/workflows/ci.yml)

## 🎯 Objectif

Ajouter un scan de sécurité pour détecter les secrets exposés dans le code.

## 📦 Installation

```bash
npm install
```

## 🧪 Exécuter les tests

```bash
npm test
```

## 🔒 Sécurité

Le workflow CI inclut maintenant :

1. **Tests automatisés** : Vérification du code
2. **GitLeaks** : Détection de secrets exposés (clés API, tokens, mots de passe)

### Qu'est-ce que GitLeaks détecte ?

- Clés API (AWS, Google, Azure, etc.)
- Tokens d'authentification
- Mots de passe en clair
- Clés privées SSH/RSA
- Tokens GitHub/GitLab

### Ordre d'exécution

```bash
Tests → GitLeaks (seulement si tests OK)
```

## 📚 Contenu

- `app.js` : Fonctions mathématiques
- `app.test.js` : Tests unitaires
- `.github/workflows/ci.yml` : Tests + Scan de sécurité
