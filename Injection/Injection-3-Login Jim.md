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
2. Mettre l’adresse mail de jim trouvé dans la review d’un produit 
3. Mettre abcd en mot de passe 
4. Aller sur burp activer intecept  
5. Cliquer sur login 
6. Mettre ‘-- à coter de l’adresse mail dans burp 
7. Appuyer sur forward  

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

Cette vulnérabilité permet à un attaquant de :
- Accéder à des comptes utilisateurs sans autorisation
- Consulter ou modifier des données personnelles
- Exploiter le système pour des attaques plus avancées
- Nuire à la réputation et à la confiance envers l’application

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
