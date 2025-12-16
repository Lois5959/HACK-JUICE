# Challenge : Forged Feedback
Catégorie : Broken Access Control  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Publier un feedback au nom d’un autre utilisateur.

Ce challenge met en évidence une mauvaise gestion des contrôles d’accès
lors de la soumission de feedback dans l’application.

---

## Méthodologie

1. Aller sur la page Customer Feedback 
2. Lancer Burp 
3. Aller sur Proxy 
4. Activer Intercept 
5. Retourner sur la page Customer Feedback 
6. Mettre un commentaire 
7. Mettre des étoiles et répondre au CAPTCHA 
8. Retourner sur Burp 
9. Changer la valeur du “UserId” 

**Techniques utilisées :**
- Test de contrôle d’accès
- Manipulation de requêtes HTTP
- Enumération

**Outils :**
- Navigateur web
- Burp Suite 

---

## Vulnérabilités

- **Type :** Contrôle d’accès défaillant (Broken Access Control)
- **CWE :** CWE-284 (Contrôle d’accès incorrect)
- **Composants affectés :** Système de gestion des feedbacks
- **Sévérité estimée :** Élevée

---

## Risques

Cette vulnérabilité permet à un attaquant de se faire passer pour un autre utilisateur
et de soumettre des feedbacks à sa place, entraînant :
- Perte d’intégrité des données
- Atteinte à la fiabilité des avis
- Perte de confiance des utilisateurs
- Risques réputationnels pour la plateforme

---

## Actions

### Atténuation
- Vérifier systématiquement les droits de l’utilisateur côté serveur avant l’enregistrement d’un feedback.
- Restreindre les actions sensibles aux seuls utilisateurs légitimes.

### Correction
- Empêcher toute soumission ou modification d’un feedback par un utilisateur non autorisé.
- Supprimer toute dépendance aux données d’identité envoyées par le client.

### Bonnes pratiques
- Contrôles d’accès systématiques
- Validation stricte
