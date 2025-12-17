# Challenge : Login Amy
Catégorie : Sensitive Data Exposure  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Se connecter avec les identifiants d’origine d’Amy.

Ce challenge démontre qu’une mauvaise protection des informations personnelles
peut permettre de retrouver des identifiants valides sans attaque par force brute.

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

---

## Vulnérabilités

- **Type :** Exposition de données sensibles (Sensitive Data Exposure)
- **CWE :** CWE-522 (Protection insuffisante des identifiants)
- **Composants affectés :** Système d’authentification / stockage des identifiants
- **Sévérité estimée :** Élevée

---

## Risques
- Compromission de comptes
- Usurpation d’identité
- Fuite de données personnelles

---

## Actions

### Atténuation
- Réduire l’exposition d’informations liées aux utilisateurs.
- Surveiller les tentatives de connexion suspectes.

### Correction
- Protéger correctement les identifiants utilisateurs.
- Empêcher toute récupération indirecte d’informations sensibles.

### Bonnes pratiques
- Appliquer les recommandations OWASP sur la gestion des mots de passe.
- Sensibiliser les utilisateurs à l’utilisation de mots de passe robustes.

