# Challenge : Payback Time
Catégorie : Improper Input Validation  
Difficulté : 3  

---

## Description

**Énoncé du challenge :**  
Passer une commande permettant de gagner de l’argent.

Ce challenge met en évidence une validation insuffisante des entrées utilisateur,
permettant de manipuler des valeurs numériques sensibles lors du processus de commande.

---

## Méthodologie

1. Ajouter un article au panier.
2. Accéder à la page Panier.
3. Lancer Burp Suite.
4. Activer l’interception dans l’onglet Proxy.
5. Revenir sur Juice Shop et cliquer sur le bouton + pour augmenter la quantité.
6. Intercepter la requête HTTP dans Burp.
7. Transmettre la requête une première fois.
8. Modifier la valeur de la quantité avec une valeur négative (ex : -100).
9. Transmettre la requête modifiée.
10. Désactiver l’interception.
11. Revenir sur Juice Shop et finaliser le paiement.

**Techniques utilisées :**
- Interception de requêtes HTTP
- Manipulation de paramètres
- Exploitation de validation insuffisante

**Outils :**
- Navigateur web
- Burp Suite 

---

## Vulnérabilités

- **Type :** Validation incorrecte des entrées (Improper Input Validation)
- **CWE :** CWE-20 (Validation incorrecte des entrées)
- **Composants affectés :** Gestion du panier / calcul du prix
- **Sévérité estimée :** Élevée

---

## Risques
- La manipulation des montants de commande
- Des pertes financières
- Une altération de l’intégrité des transactions

---

## Actions

### Atténuation
- Surveiller les valeurs anormales envoyées par le client.
- Mettre en place des contrôles de cohérence côté serveur.

### Correction
- Valider strictement les entrées numériques (quantités ≥ 0).
- Refuser toute valeur négative ou incohérente.

### Bonnes pratiques
- Appliquer une validation forte des entrées utilisateur.
- Tester les cas limites (valeurs négatives, extrêmes).
