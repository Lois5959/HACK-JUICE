# Challenge : Bjoern's Favorite Pet
Catégorie : Broken Authentication  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Réinitialiser le mot de passe du compte OWASP de Bjoern via le mécanisme
« Mot de passe oublié » en utilisant la réponse originale à sa question de sécurité.

Ce challenge illustre les faiblesses des mécanismes de récupération de mot de passe
reposant sur des questions de sécurité prévisibles ou mal protégées.

---

## Méthodologie

1. Identifier le compte cible à partir des informations disponibles dans l’application.
2. Rechercher l’adresse e-mail associée à Bjoern en analysant les avis publiés sur les produits, notamment la page du produit *OWASP Snakes and Ladders – Web Applications*.
3. Accéder à la page de connexion et utiliser la fonctionnalité « Mot de passe oublié ».
4. Observer que le mécanisme de récupération repose sur une question de sécurité.
5. Effectuer une recherche OSINT afin d’identifier la réponse originale à la question de sécurité de Bjoern.
6. Fournir la réponse correcte à la question de sécurité.
7. Définir un nouveau mot de passe pour le compte.
8. Valider l’exploitation en se connectant avec le compte de Bjoern.

**Techniques utilisées :**
- Analyse de mécanisme d’authentification
- Test de récupération de compte

**Outils :**
- Navigateur web
- Youtube

---

## Vulnérabilités

- **Type :** Authentification défaillante (Broken Authentication)
- **CWE :** CWE-287 (Authentification incorrecte) 
- **Composants affectés :** Mécanisme de récupération de mot de passe
- **Sévérité estimée :** Élevée

---

## Risques
- Réinitialisation de comptes sans autorisation
- Usurpation d’identité

---

## Actions

### Atténuation
- Limiter les tentatives de récupération de mot de passe.
- Surveiller les abus sur les mécanismes de reset.

### Correction
- Supprimer l’usage des questions de sécurité.
- Associer la récupération de compte à un canal sécurisé (email vérifié).

### Bonnes pratiques
- Appliquer les recommandations OWASP sur l’authentification.
- Utiliser l’authentification multi-facteurs.
- Sensibiliser les utilisateurs aux bonnes pratiques de sécurité.
