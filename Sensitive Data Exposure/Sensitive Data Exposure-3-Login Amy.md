# Challenge : Login Amy
Catégorie : Sensitive Data Exposure  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Se connecter avec les identifiants d’origine d’Amy.  
(Il serait irréaliste de brute-forcer ces identifiants, mais une mauvaise gestion des données sensibles permet de les retrouver.)

Ce challenge met en évidence une exposition de données sensibles due à une
mauvaise gestion ou protection des informations d’authentification.

---

## Méthodologie

1. Recherche d'informations sur l'organisation et l'employée Amy. Découverte d'un lien avec le documentaire "93 Million Miles".
2. Identification de l'animal favori d'Amy via les réseaux sociaux ou le site : un lémurien nommé "Kif".
3. Tentative de connexion par devinette de mot de passe (Guessing).
    * Essai initial avec "Kif" ou "Kif...".
    * Application d'une variation de sécurité courante (Leet Speak) suggérée par le contexte : remplacement du "i" par un "1".
    * Le mot de passe final `K1f...!` permet la connexion.
4. Accès validé au compte utilisateur d'Amy.

**Techniques utilisées :**
- Analyse de données exposées
- Recherche d’informations sensibles
- Test d’authentification

**Outils :**
- Navigateur web
- DevTools
- Outils d’analyse de données (optionnel)

---

## Vulnérabilités

- **Type :** Exposition de données sensibles (Sensitive Data Exposure)
- **CWE :** CWE-522 (Protection insuffisante des identifiants)
- **Composants affectés :** Système d’authentification / stockage des identifiants
- **Sévérité estimée :** Élevée

---

## Risques

Cette vulnérabilité permet à un attaquant d’obtenir des identifiants valides
sans recourir à une attaque par force brute, entraînant :
- Compromission de comptes utilisateurs
- Accès non autorisé à des données personnelles
- Usurpation d’identité
- Perte de confiance des utilisateurs et impact réputationnel

---

## Actions

### Atténuation
- Limiter l’exposition des informations liées aux comptes utilisateurs.
- Surveiller et journaliser les tentatives d’accès anormales.

### Correction
- Protéger toute information sensible contre l’accès non autorisé.

### Bonnes pratiques
- Respecter les recommandations OWASP concernant la gestion des mots de passe.
- Réaliser des audits réguliers sur la protection des données sensibles.
