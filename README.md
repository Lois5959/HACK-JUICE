# OWASP Juice Shop — rapports de pentest

![Challenges](https://img.shields.io/badge/challenges-14-orange)
![OWASP Top 10](https://img.shields.io/badge/OWASP-Top_10-000000)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633)

Tests d'intrusion (pentesting) réalisés sur **OWASP Juice Shop**, une application web
volontairement vulnérable, dans le cadre du module **B-SEC-100 – Hack & Juice**
(Bachelor Epitech, Lille).

Chaque challenge résolu fait l'objet d'un rapport : énoncé, étapes pour reproduire la faille,
outils, vulnérabilité (CWE), sévérité, risques et recommandations de correction.

> **Cadre légal.** Toutes les attaques ont été menées sur une instance de Juice Shop, application
> conçue pour cela. Ne testez jamais ces techniques sur un système sans l'autorisation écrite
> de son propriétaire.

---

## Objectifs

- Identifier et exploiter des vulnérabilités de sécurité web
- Résoudre des challenges Juice Shop de difficulté **≥ 3**
- Documenter chaque vulnérabilité pour pouvoir la reproduire et l'expliquer
- Comprendre l'impact métier des failles et proposer des corrections

## Méthodologie

1. Analyse fonctionnelle de l'application et repérage des surfaces d'attaque
2. Exploitation avec un proxy d'interception (**Burp Suite**), le navigateur et ses DevTools
3. Rédaction d'un rapport technique par challenge, sur un modèle commun

---

## Challenges résolus

| Catégorie OWASP | Challenge | Diff. | CWE | Sévérité |
|---|---|:-:|---|---|
| **Injection** | [Login Jim](Injection/Injection-3-Login%20Jim.md) | 3 | CWE-89 | Élevée |
| | [Login Bender](Injection/Injection-3-Login%20Bender.md) | 3 | CWE-89 | Élevée |
| **Broken Access Control** | [Forged Feedback](Broken%20Access%20Control/Broken%20Access%20Control-3-Forged%20Feedback.md) | 3 | CWE-284 | Moyenne |
| | [Forged Review](Broken%20Access%20Control/Broken%20Access%20Control-3-Forged%20Review.md) | 3 | CWE-284 | Moyenne |
| | [Manipulate Basket](Broken%20Access%20Control/Broken%20Access%20Control-3-Manipulate%20Basket.md) | 3 | CWE-284 | Élevée |
| | [Easter Egg](Broken%20Access%20Control/Broken%20Access%20Control-4-Easter%20Egg.md) | 4 | CWE-284 | Faible |
| **Broken Authentication** | [Bjoern's Favorite Pet](Broken%20Authentication/Broken%20Authentication-3-Bjoern's%20Favorite%20Pet.md) | 3 | CWE-287 | Élevée |
| **Broken Anti Automation** | [CAPTCHA Bypass](Broken%20Anti%20Automation/Broken%20Anti%20Automation-3-CAPTCHA%20Bypass.md) | 3 | CWE-307 | Moyenne |
| **Improper Input Validation** | [Payback Time](Improper%20Input%20Validation/Improper%20Input%20Validation-3-Payback%20Time.md) | 3 | CWE-20 | Élevée |
| | [Poison Null Byte](Improper%20Input%20Validation/Improper%20Input%20Validation-4-Poison%20Null%20Byte.md) | 4 | CWE-20 / CWE-158 | Critique |
| **Cryptographic Issues** | [Nested Easter Egg](Cryptographic%20Issues/Cryptographic%20Issues-4-Nested%20Easter%20Egg.md) | 4 | CWE-310 | Moyenne |
| **Sensitive Data Exposure** | [Login Amy](Sensitive%20Data%20Exposure/Sensitive%20Data%20Exposure-3-Login%20Amy.md) | 3 | CWE-522 | Élevée |
| | [Forgotten Developer Backup](Sensitive%20Data%20Exposure/Sensitive%20Data%20Exposure-4-Forgotten%20Developer%20Backup.md) | 4 | CWE-200 | Critique |
| | [Forgotten Sales Backup](Sensitive%20Data%20Exposure/Sensitive%20Data%20Exposure-4-Forgotten%20Sales%20Backup.md) | 4 | CWE-200 | Critique |

Les sévérités sont **estimées** dans le contexte du challenge.

---

## Reproduire les attaques

Lancer sa propre instance de Juice Shop (Docker requis) :

```bash
docker run --rm -p 3000:3000 bkimminich/juice-shop
```

Puis ouvrir http://localhost:3000, configurer le navigateur pour passer par le proxy
de Burp Suite (par défaut `127.0.0.1:8080`) et suivre les étapes de chaque rapport.

## Structure du dépôt

Un dossier par catégorie OWASP, un fichier Markdown par challenge. Le nom du fichier
contient la difficulté (`-3-` ou `-4-`) :

```
.
├── Injection/
├── Broken Access Control/
├── Broken Authentication/
├── Broken Anti Automation/
├── Improper Input Validation/
├── Cryptographic Issues/
├── Sensitive Data Exposure/
└── README.md
```

## Outils

Burp Suite (Proxy, Repeater), navigateur et DevTools, recherche OSINT.
