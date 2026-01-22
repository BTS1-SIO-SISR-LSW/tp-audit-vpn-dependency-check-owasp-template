# TP – Audit de sécurité d’un composant logiciel fournisseur  
BTS SIO – Option SISR – Bloc 3 Cybersécurité

## Contexte professionnel

Vous êtes **administrateur systèmes et réseaux** dans une entreprise.  
Un fournisseur vous livre une **appliance réseau** (pare-feu, VPN, proxy, etc.) accompagnée d’une **console d’administration logicielle**.

Avant la mise en production de cet équipement sur le système d’information, vous devez réaliser un **audit de sécurité des composants logiciels fournis**, afin d’identifier d’éventuelles vulnérabilités connues dans les bibliothèques utilisées.

L’audit est réalisé automatiquement via une chaîne d’intégration continue (**:contentReference[oaicite:0]{index=0}**) et l’outil **:contentReference[oaicite:1]{index=1}**.

---

## Objectifs du TP

- Identifier des vulnérabilités connues (CVE) dans un composant logiciel fourni par un tiers.
- Comprendre les impacts de ces vulnérabilités sur un **service réseau exposé**.
- Adopter une posture d’**administrateur SISR** : analyse de risque, décision de mise en production ou de blocage.

---

## Travail à réaliser

1. Lancer le workflow **Audit – Dependency-Check** dans l’onglet *Actions* du dépôt GitHub.
2. Attendre la fin de l’exécution du workflow.
3. Télécharger l’artifact contenant le rapport d’audit.
4. Ouvrir le fichier `dependency-check-report.html`.
5. Répondre aux questions ci-dessous à partir du rapport.

---

## Analyse du rapport de vulnérabilités

### Partie 1 – Compréhension du périmètre audité

**Question 1**  
Quel est le nom du projet audité tel qu’indiqué dans le rapport ?  
Expliquez ce que représente ce projet dans le cadre d’un équipement réseau fourni par un constructeur.

**Question 2**  
Quel est le type de composant analysé ?
- composant applicatif d’administration
- bibliothèque logicielle
- service système
- autre (à préciser)

Justifiez votre réponse.

**Question 3**  
Quelles technologies ou écosystèmes logiciels sont utilisés par ce composant (ex. Java, bibliothèques tierces, etc.) ?  
Citez les indices présents dans le rapport.

---

### Partie 2 – Analyse des vulnérabilités (CVE)

**Question 4**  
Combien de dépendances ont été analysées (champ *Dependencies Scanned*) ?  
Combien de dépendances vulnérables ont été identifiées ?

**Question 5**  
Quelle est la vulnérabilité la plus critique détectée ?
- Identifiant CVE  
- Score CVSS  
- Niveau de gravité (faible, moyen, élevé, critique)

**Question 6**  
Cette vulnérabilité concerne-t-elle :
- une bibliothèque de journalisation
- une bibliothèque réseau
- un composant de parsing ou de sérialisation
- un autre type de composant

Expliquez pourquoi ce type de composant est critique dans une appliance réseau.

---

### Partie 3 – Impact sur le système d’information

**Question 7**  
La console d’administration est-elle susceptible d’être :
- exposée à Internet
- accessible depuis le réseau interne
- accessible uniquement par des administrateurs

Expliquez les risques associés à cette exposition.

**Question 8**  
Quels impacts ces vulnérabilités pourraient-elles avoir sur le système d’information ?
- accès non autorisé à l’équipement
- compromission du réseau interne
- élévation de privilèges
- déni de service
- fuite d’informations sensibles

Justifiez votre réponse.

**Question 9**  
Pourquoi une vulnérabilité logicielle dans un composant fournisseur est-elle critique même si l’administrateur n’a pas écrit le code ?

---

### Partie 4 – Décision en tant qu’administrateur SISR

**Question 10**  
En tant qu’administrateur systèmes et réseaux, quelle décision recommandez-vous ?
- mise en production immédiate
- mise en production conditionnelle (après correctif)
- refus de mise en production
- demande de correctif au fournisseur

Argumentez votre choix.

**Question 11**  
Quelles actions pouvez-vous mener sans modifier le code source ?
- mise à jour de la version du composant
- configuration restrictive
- filtrage réseau / pare-feu
- limitation d’accès à la console
- surveillance renforcée

**Question 12**  
Quels contrôles supplémentaires recommanderiez-vous avant validation finale ?
- tests d’intrusion
- audit de configuration
- journalisation et supervision
- revue de conformité sécurité

---

### Partie 5 – Synthèse professionnelle

**Question 13**  
En 5 à 10 lignes maximum, rédigez une synthèse destinée à un RSSI ou à un responsable informatique :
- état de sécurité du composant audité
- niveau de risque pour le système d’information
- décision recommandée et justification

---

## Rendu attendu

- Un fichier `SYNTHESE.md` (ou un document PDF) contenant les réponses argumentées.
- Le rapport `dependency-check-report.html` en annexe si demandé.

---

## Rappel important

Vous êtes dans une posture **SISR** :  
vous n’êtes pas développeur du composant, mais **responsable de son intégration sécurisée** dans le système d’information.

---

## Compétences évaluées (SISR)

- Identifier des vulnérabilités logicielles dans un contexte d’infrastructure.
- Analyser l’exposition et les impacts sur un service réseau.
- Exploiter un rapport d’audit de sécurité.
- Prendre une décision de mise en production ou de blocage.
- S’inscrire dans une démarche de gestion des risques cyber.
