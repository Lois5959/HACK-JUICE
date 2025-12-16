# Challenge : Manipulate Basket
Catégorie : Broken Access Control  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Ajouter un produit supplémentaire dans le panier d’un autre utilisateur.

Ce challenge met en évidence une mauvaise gestion des contrôles d’accès
lors de la manipulation du panier dans l’application.

---

## Méthodologie

1. Lancer Burp 
2. Aller dans Proxy et activer Intercept 
3. Aller sur Juice Shop  
4. Mettre un article dans le panier 
5. Retourner sur Burp 
6. Envoyer au Repeater 
7. Changer la valeur du “BasketId” 
8. Ajouter un autre “BasketId” 
9. Appuyer sur Send 

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
- **Composants affectés :** Système de panier d’achats
- **Sévérité estimée :** Élevée

---

## Risques

Cette vulnérabilité permet à un attaquant d’ajouter des produits dans le panier d’un autre utilisateur, entraînant :
- Perte d’intégrité des données
- Manipulation des achats d’autrui
- Atteinte à la crédibilité et confiance des utilisateurs
- Risques financiers et réputationnels pour la plateforme

---

## Actions

### Atténuation
- Vérifier côté serveur que l’utilisateur est bien propriétaire du panier avant toute modification.
- Restreindre l’accès aux actions de modification du panier aux seuls propriétaires légitimes.

### Correction
- Associer le panier exclusivement au compte utilisateur authentifié côté serveur.
- Empêcher toute modification d’un panier par un utilisateur non autorisé.
- Supprimer toute dépendance aux identifiants envoyés par le client pour déterminer le propriétaire du panier.

### Bonnes pratiques
- Principe du moindre privilège
- Contrôles d’accès centralisés et systématiques
- Validation stricte côté serveur pour toutes les actions sensibles
