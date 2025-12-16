# Challenge : Poison Null Byte
Catégorie : Improper Input Validation  
Difficulté : 4  

---

## Description

**Énoncé du challenge :**  
Contourner un contrôle de sécurité en utilisant un Poison Null Byte afin
d’accéder à un fichier qui ne devrait pas être accessible.

Ce challenge met en évidence une validation insuffisante des entrées utilisateur,
permettant de contourner des restrictions d’accès aux fichiers.

---

## Méthodologie

1. Aller dans le dossier /ftp 
2. Faire une requête pour télécharger le fichier en ajoutant un "Null Byte" (%00) suivi d'une extension valide.
3. URL demandée : `/ftp/package.json.bak%2500.md` (le %2500 est le double encodage de %00 nécessaire via l'URL).
4. Le serveur vérifie l'extension (.md = valide) mais le système de fichier s'arrête au caractère Null, lisant le fichier `.bak`.

**Techniques utilisées :**
- Test de validation des entrées
- Contournement de contrôles de sécurité
- Analyse de traitements de chaînes

**Outils :**
- Navigateur web

---

## Vulnérabilités

- **Type :** Validation incorrecte des entrées (Improper Input Validation)
- **CWE :** CWE-20 (Validation incorrecte des entrées) / CWE-158 (Gestion incorrecte des caractères nuls)
- **Composants affectés :** Système d’accès aux fichiers
- **Sévérité estimée :** Critique

---

## Risques

Cette vulnérabilité permet à un attaquant de contourner des contrôles de sécurité
et d’accéder à des fichiers sensibles, entraînant :
- Divulgation d’informations confidentielles
- Compromission de données internes
- Facilitation d’attaques ultérieures
- Impact critique sur la sécurité de l’application

---

## Actions

### Atténuation
- Ajouter des contrôles supplémentaires sur les accès aux ressources sensibles.

### Correction
- Rejeter toute entrée contenant des caractères inattendus ou dangereux.

### Bonnes pratiques
- Appliquer une validation stricte et centralisée des données.
- Tester régulièrement les mécanismes de validation des entrées.
