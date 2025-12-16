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

1. Lancer Burp 
2. Aller dans Proxy et activer Intercept 
3. Retourner sur le site Juice Shop 
4. Cliquer sur un produit et écrire une review 
5. Cliquer sur Submit 
6. Retourner sur Burp  
7. Appuyer sur Foward 

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
- **Sévérité estimée :** Élevée

---

## Risques

Cette vulnérabilité permet à un attaquant de se faire passer pour un autre utilisateur
ou de modifier ses contenus, entraînant :
- Perte d’intégrité des données
- Manipulation de l’opinion des utilisateurs
- Atteinte à la crédibilité de la plateforme
- Risques juridiques et réputationnels

---

## Actions

### Atténuation
- Vérifier les autorisations côté serveur pour toute création ou modification d’avis.
- Restreindre les actions de modification aux seuls auteurs légitimes.

### Correction
- Déterminer l’auteur d’un avis uniquement à partir du contexte de session côté serveur.
- Empêcher toute modification d’un avis par un utilisateur non propriétaire.
- Supprimer toute dépendance aux identifiants envoyés par le client.

### Bonnes pratiques
- Principe du moindre privilège
- Contrôles d’accès centralisés et systématiques
- Validation stricte côté serveur pour toutes les actions sensibles
