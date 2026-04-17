# High Story Social Media Orchestrator (Skill)

This repository contains an **Agent Skill** for Claude (and other LLM agents) to autonomously manage social media strategies.

## 🚀 Purpose

Stop copy-pasting posts. This skill gives Claude the strategic framework and tool-set to:
- Generate platform-optimized content (Instagram, LinkedIn, X).
- Orchestrate image generation via High Story.
- **Publish directly** using the High Story MCP bridge.

## 🛠️ Step-by-Step Installation

### Étape 1 : Récupérer le Skill
1. Allez sur [https://github.com/7figures007/highstory-social-media-manager](https://github.com/7figures007/highstory-social-media-manager).
2. Cliquez sur le bouton vert **Code** puis sur **Download ZIP** (ou utilisez `git clone` si vous connaissez).
3. Décompressez le fichier et placez le dossier `highstory-social-media-manager` dans votre dossier habituel pour les skills Claude.

### Étape 2 : Configurer le Bridge (La Connexion)
1. Ouvrez votre terminal (Terminal sur Mac, PowerShell sur Windows).
2. Tapez la commande suivante et appuyez sur Entrée :
   ```bash
   npx highstory-mcp setup
   ```
3. Collez votre **Clé API permanente High Story** (que vous trouverez dans vos réglages High Story) quand cela est demandé.
4. Redémarrez complètement votre application Claude Desktop.

### Étape 3 : Utiliser Claude comme Manager RS
Demandez simplement à Claude :
> *"Utilise le skill High Story Social Media Orchestrator pour créer une campagne sur LinkedIn."*

## 🌐 Multilingual Support

Includes ready-to-use strategies for 16 languages, ensuring brand consistency from Paris to Tokyo.
