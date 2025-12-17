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

1. Accéder à la page « Customer Feedback » de l’application.
2. Lancer l’outil Burp Suite.
3. Configurer le navigateur pour intercepter le trafic via le proxy Burp.
4. Activer l’interception des requêtes HTTP.
5. Retourner sur la page « Customer Feedback ».
6. Soumettre un nouveau feedback en renseignant un commentaire et une note.
7. Compléter le CAPTCHA requis par l’application.
8. Intercepter la requête HTTP envoyée lors de la soumission du feedback.
9. Analyser les paramètres transmis dans la requête.
10. Modifier la valeur du paramètre identifiant l’utilisateur (UserId).
11. Transmettre la requête modifiée au serveur.
12. Valider l’exploitation en constatant que le feedback est publié au nom d’un autre utilisateur.

**Techniques utilisées :**
- Test de contrôle d’accès
- Manipulation de requêtes HTTP

**Outils :**
- Navigateur web
- Burp Suite 

---

## Vulnérabilités

- **Type :** Contrôle d’accès défaillant (Broken Access Control)
- **CWE :** CWE-284 (Contrôle d’accès incorrect)
- **Composants affectés :** Système de gestion des feedbacks
- **Sévérité estimée :** Moyenne

---

## Risques
- Usurpation d’identité
- Altération du contenu utilisateur
- Perte de confiance dans la plateforme

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
