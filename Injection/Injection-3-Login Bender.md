# Challenge : Login Bender
Catégorie : Injection  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Se connecter au compte utilisateur de Bender.

Ce challenge met en évidence une vulnérabilité d’injection permettant de
contourner le mécanisme d’authentification de l’application.

---

## Méthodologie

1. Aller sur la page login 
2. Mettre l’adresse mail de bender trouvé dans la review d’un produit 
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

- **Type :** Injection 
- **CWE :** CWE-89 (Injection SQL)
- **Composants affectés :** Système d’authentification
- **Sévérité estimée :** Élevée

---

## Risques
- Contournement de l’authentification
- Accès non autorisé aux comptes
- Compromission des données utilisateurs

---

## Actions

### Atténuation
- Surveiller et limiter les tentatives de connexion anormales.
- Mettre en place des mécanismes de détection d’injections.

### Correction
- Valider et échapper strictement toutes les entrées utilisateur.
- Ne jamais concaténer directement des données utilisateur dans des requêtes.

### Bonnes pratiques
- Appliquer les recommandations OWASP contre les injections.
- Effectuer des revues de code régulières.
- Mettre en place des tests de sécurité automatisés sur l’authentification.
