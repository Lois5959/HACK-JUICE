# Challenge : CAPTCHA Bypass
Catégorie : Broken Anti Automation  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Soumettre 10 feedbacks ou plus en moins de 20 secondes.

Ce challenge met en évidence une protection anti-automatisation inefficace,
permettant de soumettre plusieurs requêtes identiques sans contrôle réel

---

## Méthodologie

1. Accéder à la page Customer Feedback.
2. Remplir le formulaire de feedback.
3. Lancer Burp Suite.
4. Activer l’interception dans l’onglet Proxy.
5. Cliquer sur Submit pour envoyer le feedback.
6. Intercepter la requête HTTP dans Burp.
7. Envoyer la requête interceptée dans Repeater.
8. Cliquer plusieurs fois sur Send afin de soumettre le feedback à répétition.

**Techniques utilisées :**
- Interception de requêtes HTTP
- Rejeu de requêtes (Replay Attack)

**Outils :**
- Navigateur web
- Burp Suite 

---

## Vulnérabilités

- **Type :** Broken Anti Automation
- **CWE :** CWE-307 (Restriction insuffisante des tentatives d’authentification)
- **Composants affectés :** CAPTCHA / limitation des requêtes
- **Sévérité estimée :** Moyenne

---

## Risques
- Le spam massif de feedbacks
- La dégradation de la qualité des données
- Une surcharge du système
- Une mauvaise expérience utilisateur

---

## Actions

### Atténuation
- Limiter le nombre de requêtes par utilisateur ou par IP.
- Surveiller les comportements anormaux.

### Correction
- Implémenter un CAPTCHA vérifié côté serveur.
- Empêcher la réutilisation d’une même requête.

### Bonnes pratiques
- Combiner CAPTCHA et rate limiting.
- Tester régulièrement les mécanismes anti-automatisation.
