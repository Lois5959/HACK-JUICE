# Challenge : Login Jim
Catégorie : Injection  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Se connecter au compte utilisateur de Jim.

Ce challenge met en évidence une vulnérabilité d’injection permettant de
contourner le mécanisme d’authentification de l’application.

---

## Méthodologie

1. Aller sur la page login 
2. Saisir l’adresse e-mail de Jim (visible dans l’avis d’un produit).
3. Saisir n’importe quel mot de passe (ex : `abcd`).
4. Dans Burp Suite, activer l’interception (Proxy > Intercept is on).
5. Cliquer sur « Log in ».
6. Dans la requête interceptée, ajouter `'--` juste après l’adresse e-mail : la suite de la requête SQL (le test du mot de passe) est alors mise en commentaire.
7. Cliquer sur « Forward » : la connexion réussit sans connaître le mot de passe.

**Techniques utilisées :**
- Test d’injection
- Analyse des entrées utilisateur
- Contournement de l’authentification

**Outils :**
- Navigateur web
- Burp Suite 

---

## Vulnérabilités

- **Type :** Injection (ex. injection SQL)
- **CWE :** CWE-89 (Injection SQL)
- **Composants affectés :** Système d’authentification
- **Sévérité estimée :** Élevée

---

## Risques
- Accès non autorisé aux comptes utilisateurs
- Exploitation généralisée de la faille

---

## Actions

### Atténuation
- Limiter les tentatives de connexion et détecter les comportements anormaux.
- Journaliser et surveiller les erreurs d’authentification.

### Correction
- Mettre en place une séparation claire entre données et logique de requête.

### Bonnes pratiques
- Suivre les recommandations OWASP contre les injections.
- Réaliser des tests de sécurité réguliers.
