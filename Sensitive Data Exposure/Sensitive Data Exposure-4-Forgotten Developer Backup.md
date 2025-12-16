# Challenge : Forgotten Developer Backup
Catégorie : Sensitive Data Exposure  
Difficulté : 4  

---

## Description

**Énoncé du challenge :**  
Accéder à un fichier de sauvegarde oublié par un développeur.

Ce challenge met en évidence une exposition de données sensibles due à la
présence de fichiers de sauvegarde ou de développement accessibles publiquement.

---

## Méthodologie

1. Aller dans le dossier /ftp 
2. Cliquer le le ficher `encrypt.pyc`
3. Faire une requête pour télécharger le fichier 
4. URL demandée : `/ftp/encrypt.pyc%2500.md` 


**Techniques utilisées :**
- Exploration de ressources
- Recherche de fichiers exposés
- Analyse de données sensibles

**Outils :**
- Navigateur web

---

## Vulnérabilités

- **Type :** Exposition de données sensibles (Sensitive Data Exposure)
- **CWE :** CWE-200 (Exposition d’informations sensibles)
- **Composants affectés :** Serveur web / fichiers de développement
- **Sévérité estimée :** Critique

---

## Risques

Cette vulnérabilité permet à un attaquant d’accéder à des données internes ou confidentielles, entraînant :
- Divulgation de code source ou de configurations
- Compromission de données sensibles
- Facilitation d’attaques ultérieures
- Risques juridiques et réputationnels

---

## Actions

### Atténuation
- Restreindre l’accès aux fichiers sensibles via des règles serveur.
- Surveiller l’exposition de fichiers non destinés à la production.

### Correction
- Mettre en place des contrôles d’accès stricts sur les ressources internes.

### Bonnes pratiques
- Effectuer des audits réguliers pour détecter les fichiers exposés.
