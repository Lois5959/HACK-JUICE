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

1. Lancer l’outil Burp Suite.
2. Configurer le navigateur afin que le trafic HTTP transite par le proxy Burp.
3. Activer l’interception des requêtes dans l’onglet « Proxy ».
4. Accéder à l’application OWASP Juice Shop.
5. Ajouter un produit au panier depuis l’interface utilisateur.
6. Intercepter la requête HTTP générée lors de l’ajout du produit au panier.
7. Envoyer la requête interceptée vers l’outil Repeater de Burp Suite.
8. Analyser les paramètres transmis par le client, notamment l’identifiant du panier (BasketId).
9. Modifier la valeur du paramètre BasketId afin de cibler le panier d’un autre utilisateur.
10. Rejouer la requête modifiée depuis le Repeater.
11. Valider l’exploitation en constatant qu’un produit est ajouté au panier d’un autre utilisateur.

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
- Modification frauduleuse de commandes
- Impact financier
- Atteinte à l’intégrité des données

---

## Actions

### Atténuation
- Vérifier côté serveur que l’utilisateur est bien propriétaire du panier avant toute modification.
- Restreindre l’accès aux actions de modification du panier aux seuls propriétaires légitimes.

### Correction
- Associer le panier exclusivement au compte utilisateur authentifié côté serveur.
- Empêcher toute modification d’un panier par un utilisateur non autorisé.

### Bonnes pratiques
- Validation stricte côté serveur pour toutes les actions sensibles
