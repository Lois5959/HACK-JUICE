# Challenge : Easter Egg
Catégorie : Broken Access Control  
Difficulté : 4  

---

## Description

**Énoncé du challenge :**  
Trouver l’easter egg caché dans l’application.

Ce challenge met en évidence une faille de contrôle d’accès ou une fonctionnalité cachée
qui n’est pas documentée et qui peut être exploitée si elle est accessible à des utilisateurs non autorisés.

---

## Méthodologie

1. Explorer l’application afin de repérer des fonctionnalités ou fichiers non visibles depuis l’interface principale.
2. Modifier manuellement l’URL pour accéder à un répertoire caché.
3. Identifier un fichier lié à l’easter egg.
4. Tester l’accès et le téléchargement de ce fichier. (%2500.md)
5. Valider le challenge en accédant au contenu de l’easter egg.

**Techniques utilisées :**
- Exploration manuelle

**Outils :**
- Navigateur web

---

## Vulnérabilités

- **Type :** Contrôle d’accès défaillant / fonctionnalité cachée accessible
- **CWE :** CWE-284 (Contrôle d’accès incorrect)
- **Composants affectés :** Fonctionnalité ou contenu caché
- **Sévérité estimée :** Faible

---

## Risques
- Accès à des ressources non prévues
- Découverte d’informations internes

---

## Actions

### Atténuation
- Restreindre l’accès aux fonctionnalités cachées aux utilisateurs autorisés uniquement.

### Correction
- S’assurer que l’easter egg ou toute fonctionnalité cachée nécessite l’authentification et les droits appropriés.
- Supprimer tout accès public non autorisé à des fonctionnalités sensibles.

### Bonnes pratiques
- Tester régulièrement l’application pour détecter des fonctionnalités cachées accessibles
