# TP – Audit de sécurité d’un serveur VPN avec l'outil dependency-check d'OWASP
BTS SIO – Option SISR – Bloc 3 Cybersécurité

## Contexte professionnel

Vous êtes administrateur réseau dans une entreprise.  
Un serveur VPN est utilisé pour permettre l’accès distant au réseau interne.

Avant toute mise en production (ou dans le cadre d’un audit de sécurité), vous devez évaluer les risques liés aux composants logiciels utilisés par ce serveur.

L’audit a été réalisé automatiquement à l’aide de OWASP Dependency-Check via une plateforme d’intégration continue (CI).

---

## Travail à réaliser

1. Lancer le workflow « Audit VPN (Dependency-Check) » dans l’onglet *Actions* du dépôt GitHub.
2. Télécharger l’artifact contenant le rapport HTML.
3. Ouvrir le fichier `dependency-check-report.html`.
4. Répondre de façon argumentée aux questions ci-dessous à partir du rapport.

---

## Analyse du rapport de vulnérabilités

### Partie 1 – Compréhension globale du scan

**Question 1**  
Quel est le nom du projet audité tel qu’indiqué dans le rapport ?  
Expliquez ce que représente ce projet dans un contexte réseau.

**Question 2**  
Quel type de système a été analysé ?
- application web
- poste client
- équipement ou service réseau
- autre (à préciser)

Justifiez votre réponse.

**Question 3**  
Quelles catégories de composants sont principalement concernées par le scan ?
- bibliothèques cryptographiques
- bibliothèques système
- composants réseau
- autres

---

### Partie 2 – Analyse des vulnérabilités (CVE)

**Question 4**  
Combien de vulnérabilités sont listées au total dans le rapport ?

**Question 5**  
Quelle est la vulnérabilité ayant le score CVSS le plus élevé ?
- Identifiant CVE  
- Score CVSS  
- Niveau de gravité (faible, moyen, élevé, critique)

**Question 6**  
Cette vulnérabilité concerne-t-elle :
- une bibliothèque cryptographique
- une bibliothèque réseau
- un composant système
- autre (à préciser)

Expliquez pourquoi ce type de composant est critique pour un serveur VPN.

---

### Partie 3 – Exposition réseau et impact sur le système d’information

**Question 7**  
Le serveur VPN est-il exposé directement à Internet ou uniquement accessible depuis le réseau interne ?  
Justifiez votre réponse en vous appuyant sur le rôle d’un VPN.

**Question 8**  
Parmi les vulnérabilités détectées, lesquelles pourraient être exploitables à distance ?  
Expliquez votre raisonnement.

**Question 9**  
Quels impacts ces vulnérabilités pourraient-elles avoir sur le système d’information ?
- accès non autorisé au réseau interne
- interception des communications
- déni de service
- autre (à préciser)

---

### Partie 4 – Décision en tant qu’administrateur SISR

**Question 10**  
En tant qu’administrateur réseau, quelles mesures recommanderiez-vous ?
- mise à jour du système ou des bibliothèques
- redémarrage du service VPN
- surveillance renforcée
- isolement temporaire du service
- refus de mise en production

Justifiez votre choix.

**Question 11**  
Est-il possible de corriger ces vulnérabilités sans modifier de code applicatif ?  
Expliquez pourquoi.

**Question 12**  
Évaluez le niveau de risque global du serveur VPN :
- faible
- modéré
- élevé
- critique

Argumentez votre réponse à partir du rapport.

---

### Partie 5 – Synthèse professionnelle

**Question 13**  
En cinq à dix lignes maximum, rédigez une conclusion destinée à un responsable de la sécurité des systèmes d’information (RSSI), présentant :
- l’état de sécurité du serveur VPN,
- les principaux risques identifiés,
- la décision recommandée.

---

## Rendu attendu

- Un document PDF contenant les réponses aux questions .
- Le rapport `dependency-check-report.html` ou le dossier `reports` zippé .

---

## Rappel

Vous n’êtes pas développeur.  
Vous auditez un service réseau et prenez une décision de sécurité .

---

## Compétences évaluées

- Identifier des vulnérabilités logicielles.
- Analyser l’exposition d’un service réseau.
- Exploiter un rapport de sécurité.
- Prendre une décision en administration système et réseau.
