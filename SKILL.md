---
name: highstory-blog-automation
description: Automates the integration of multilingual blog articles into a HighStory-style Astro application (syncs 16 languages, handles FAQs, JSON-LD, and smart scheduling).
---

# HighStory Blog Automation

Ce skill permet à un agent d'automatiser l'intégration massive d'articles de blog générés (par exemple par Claude ou d'autres flux) dans le fichier `articles.json` d'un projet Astro HighStory.

## Capacités

1. **Mapping Multilingue** : Gère les 16 langues supportées par High Story (FR, EN, ES, DE, IT, PT, NL, SV, JA, PL, TR, RU, VI, ZH-CN, AR-MA, RO).
2. **Design HighStory** : Convertit le Markdown en HTML premium et injecte automatiquement les sections FAQ dans des blocs `<div class="callout callout-info">`.
3. **SEO Avancé** : Injecte les scripts `application/ld+json` (HowTo, Article) dans le contenu.
4. **Planification Intelligente** : Permet de synchroniser la sortie d'un même article dans toutes les langues sur une date commune, avec une cadence configurable (par défaut 2 thématiques par semaine).

## Utilisation

### Étape 1 : Localisation des fichiers
L'agent doit chercher les fichiers suivants dans le dossier de téléchargements (`~/Downloads` ou un chemin spécifié) :
- `blog articles claude mcp - [LANG]` : Les briefs éditoriaux (JSON).
- `blog articles all languages content body` : Le corps des articles (JSON concaténé).
- `blog article omnipresence` : (Optionnel) Un batch d'articles à publier immédiatement.

### Étape 2 : Exécution de l'intégration
Utilisez le script Python fourni pour fusionner les données :

```bash
python3 scripts/integrate_articles.py [DOWNLOADS_DIR] [OMNIPRESENCE_FILE] [TARGET_JSON_FILE]
```

### Étape 3 : Vérification
- Vérifier que le formatage HTML (italiques `<em>`, gras `<strong>`, listes `<ul>`) est correct.
- S'assurer que les dates de publication sont synchronisées par ID d'article.

## Structure attendue du projet Astro
Le skill s'attend à trouver un fichier `src/articles.json` avec la structure suivante :
```json
[
  {
    "slug": "...",
    "title": "...",
    "date": "YYYY-MM-DD HH:MM:SS",
    "content": "...",
    "lang": "...",
    "featuredImageUrl": "..."
  }
]
```
