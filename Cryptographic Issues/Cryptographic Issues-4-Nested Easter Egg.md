# Challenge : Nested Easter Egg
Catégorie : Cryptographic Issues  
Difficulté : 4  

---

## Description

**Énoncé du challenge :**  
Appliquer des techniques avancées de cryptanalyse afin de trouver le véritable easter egg.

Ce challenge met en évidence des faiblesses cryptographiques ou une mauvaise utilisation
de mécanismes de chiffrement/encodage pouvant mener à la divulgation d’informations cachées.

---

## Méthodologie

1. Identifier les éléments chiffrés ou encodés liés à l’easter egg.
2. Analyser le format, le type et les caractéristiques des données protégées.
4. Appliquer des techniques de cryptanalyse adaptées au contexte.
5. Vérifier progressivement les résultats intermédiaires.
6. Valider l’exploitation en accédant à l’easter egg final.

**Techniques utilisées :**
- Analyse cryptographique
- Décryptage / décodage
- Recherche de faiblesses algorithmiques

**Outils :**
- Navigateur web
- Outils de décodage/cryptanalyse (en ligne)

---

## Vulnérabilités

- **Type :** Mauvaise implémentation cryptographique
- **CWE :** CWE-310 (Cryptographie insuffisante)
- **Composants affectés :** Mécanisme de protection des données cachées
- **Sévérité estimée :** Moyenne

---

## Risques
- Accès à des informations protégées
- Affaiblissement global de la sécurit

---

## Actions

### Atténuation
- Limiter l’exposition des données sensibles même lorsqu’elles sont chiffrées.
- Ajouter des contrôles d’accès supplémentaires autour des données protégées.

### Correction
- Utiliser des algorithmes cryptographiques robustes et reconnus.
- Implémenter correctement les mécanismes de chiffrement (clés).

### Bonnes pratiques
- Suivre les recommandations OWASP pour la cryptographie.
- Effectuer des audits de sécurité réguliers sur les mécanismes de chiffrement.
