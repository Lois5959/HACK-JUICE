# Challenge : Forged Review
Catégorie : Broken Access Control  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Publier un avis produit au nom d’un autre utilisateur ou modifier l’avis existant d’un autre utilisateur.

Ce challenge met en évidence une mauvaise gestion des contrôles d’accès
lors de la création ou de la modification des avis produits.

---

## Méthodologie

1. Lancer l’outil Burp Suite.
2. Configurer le navigateur pour faire transiter le trafic HTTP via le proxy Burp.
3. Activer l’interception des requêtes dans l’onglet « Proxy ».
4. Accéder à l’application OWASP Juice Shop.
5. Sélectionner un produit et rédiger un avis.
6. Soumettre l’avis via le bouton de validation.
7. Intercepter la requête HTTP envoyée lors de la soumission de l’avis.
8. Analyser les paramètres transmis par le client dans la requête.
9. Identifier les champs liés à l’utilisateur ou à l’avis existant.
10. Modifier les paramètres permettant d’usurper ou de cibler un autre utilisateur.
11. Transmettre la requête modifiée au serveur.
12. Valider l’exploitation en constatant que l’avis est publié ou modifié au nom d’un autre utilisateur.

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
- **Composants affectés :** Système de gestion des avis produits
- **Sévérité estimée :** Moyenne

---

## Risques
- Manipulation des avis
- Impact sur la crédibilité des produits
- Désinformation des utilisateurs

---

## Actions

### Atténuation
- Vérifier que seul l’auteur peut créer ou modifier un avis
- Restreindre les actions de modification aux seuls auteurs légitimes.

### Correction
- Empêcher toute modification d’un avis par un utilisateur non propriétaire.

### Bonnes pratiques
- Validation stricte côté serveur pour toutes les actions sensibles
