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

1. Explorer l’application pour identifier des zones ou fonctionnalités cachées.
2. Mettre ftp dans l’url 
3. Cliquer sur le ficher eastere.gg 
4. Le telercharger en mettant dans l’url %2500.md 

**Techniques utilisées :**
- Exploration manuelle

**Outils :**
- Navigateur web

---

## Vulnérabilités

- **Type :** Contrôle d’accès défaillant / fonctionnalité cachée accessible
- **CWE :** CWE-284 (Contrôle d’accès incorrect)
- **Composants affectés :** Fonctionnalité ou contenu caché
- **Sévérité estimée :** Élevée

---

## Risques

Cette vulnérabilité permet à un utilisateur non autorisé de découvrir ou d’activer des fonctionnalités cachées, entraînant :
- Divulgation d’informations sensibles ou non publiques
- Atteinte à l’intégrité ou au fonctionnement de l’application
- Risques réputationnels si ces contenus sont visibles par le public

---

## Actions

### Atténuation
- Restreindre l’accès aux fonctionnalités cachées aux utilisateurs autorisés uniquement.
- Vérifier côté serveur toutes les actions déclenchées par des contenus non documentés.

### Correction
- S’assurer que l’easter egg ou toute fonctionnalité cachée nécessite l’authentification et les droits appropriés.
- Supprimer tout accès public non autorisé à des fonctionnalités sensibles.

### Bonnes pratiques
- Principes du moindre privilège et de la défense en profondeur
- Contrôles d’accès centralisés
- Tester régulièrement l’application pour détecter des fonctionnalités cachées accessibles
