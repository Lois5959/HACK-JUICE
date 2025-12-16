# Challenge : Forgotten Sales Backup
Catégorie : Sensitive Data Exposure  
Difficulté : 4  

---

## Description

**Énoncé du challenge :**  
Accéder au fichier de sauvegarde oublié d’un commercial.

Ce challenge illustre les risques liés à une mauvaise gestion des fichiers
sensibles, notamment des sauvegardes laissées accessibles publiquement.

---

## Méthodologie

1. Aller dans le dossier /ftp 
2. Cliquer le le ficher `coupons_2013.md.bak`
3. Faire une requête pour télécharger le fichier 
4. URL demandée : `/ftp/coupons_2013.md.bak%2500.md`

**Techniques utilisées :**
- Énumération de fichiers et répertoires
- Analyse d’exposition de données
- Test de configuration serveur

**Outils :**
- Navigateur web

---

## Vulnérabilités

- **Type :** Exposition de données sensibles
- **CWE :** CWE-200 (Exposure of Sensitive Information)
- **Composants affectés :** Serveur web / système de stockage des fichiers
- **Sévérité estimée :** Critique

---

## Risques

Cette vulnérabilité peut entraîner :
- Fuite d’informations commerciales sensibles
- Accès à des données internes (clients, ventes, stratégies)
- Avantage concurrentiel pour un attaquant
- Atteinte grave à la réputation de l’entreprise
- Risque légal et réglementaire

---

## Actions

### Atténuation
- Restreindre l’accès aux répertoires contenant des fichiers sensibles.
- Supprimer les fichiers de sauvegarde des environnements accessibles publiquement.

### Correction
- Mettre en place des règles de contrôle d’accès strictes côté serveur.
- Stocker les sauvegardes dans des emplacements non exposés au public.

### Bonnes pratiques
- Mettre en place des audits réguliers de configuration.
- Séparer clairement environnements de production et de sauvegarde.
