# TP – Audit de sécurité d’un composant logiciel fournisseur  
BTS SIO – Option SISR – Bloc 3 : Cybersécurité des services informatiques

---

## Contexte professionnel

Vous êtes **administrateur systèmes et réseaux** dans une organisation.  
Un fournisseur vous livre une **appliance réseau** (pare-feu, VPN, proxy, etc.) intégrant une **console d’administration logicielle**.

Avant toute mise en production sur le système d’information, il est nécessaire de réaliser un **audit de sécurité des composants logiciels fournis**, afin d’identifier d’éventuelles vulnérabilités connues dans les bibliothèques utilisées par cette appliance.

L’audit est automatisé via une chaîne d’intégration continue (CI) utilisant **GitHub Actions** et l’outil **OWASP Dependency-Check**.

---

## Qu’est-ce qu’une appliance réseau ?

Une **appliance réseau** est un **équipement matériel ou virtuel prêt à l’emploi**, dédié à une **fonction réseau ou de sécurité précise**, livré par un constructeur et **administré comme un tout** (matériel + système + logiciel).

L’administrateur ne développe pas le code de l’appliance :  
il **configure**, **met à jour**, **sécurise** et **intègre** l’équipement dans le système d’information.

### Exemples courants d’appliances réseau

- **Pare-feu / UTM** : :contentReference[oaicite:0]{index=0}, :contentReference[oaicite:1]{index=1}  
- **VPN** : :contentReference[oaicite:2]{index=2}  
- **Proxy / filtrage web** : :contentReference[oaicite:3]{index=3}  
- **IDS / IPS** : :contentReference[oaicite:4]{index=4}  

### Formes de déploiement possibles

Ces solutions existent souvent :
- en **boîtier physique**,
- en **machine virtuelle**,
- en **conteneur**.

---

## Objectifs du TP

- Identifier des vulnérabilités connues (CVE) dans un composant logiciel fourni par un tiers.
- Comprendre les impacts de ces vulnérabilités sur un **service réseau potentiellement exposé**.
- Adopter une posture d’**administrateur SISR** : analyse de risque et décision de mise en production ou de blocage.

---

## Travail à réaliser

1. Ouvrir le dépôt GitHub fourni via GitHub Classroom.
2. Aller dans l’onglet **Actions**.
3. Lancer manuellement le workflow **Audit – Dependency-Check**.
4. Attendre la fin de l’exécution du workflow.
5. Télécharger l’artifact contenant le rapport d’audit.
6. Ouvrir le fichier `dependency-check-report.html`.
7. Répondre aux questions ci-dessous en vous appuyant sur le rapport.

---

## Analyse du rapport de vulnérabilités

### Partie 1 – Compréhension du périmètre audité

**Question 1**  
Quel est le nom du projet audité tel qu’indiqué dans le rapport ?  
Expliquez ce que représente ce projet dans le cadre d’une appliance réseau fournie par un constructeur.

**Question 2**  
Quel est le type de composant analysé ?
- composant applicatif d’administration,
- bibliothèque logicielle,
- service système,
- autre (à préciser).

Justifiez votre réponse.

**Question 3**  
Quelles technologies ou écosystèmes logiciels sont utilisés par ce composant ?  
Citez les indices présents dans le rapport.

---

### Partie 2 – Analyse des vulnérabilités (CVE)

**Question 4**  
Combien de dépendances ont été analysées (*Dependencies Scanned*) ?  
Combien de dépendances vulnérables ont été identifiées ?

**Question 5**  
Quelle est la vulnérabilité la plus critique détectée ?
- identifiant CVE,
- score CVSS,
- niveau de gravité.

**Question 6**  
Quel type de composant est concerné par cette vulnérabilité (journalisation, réseau, parsing, etc.) ?  
Expliquez pourquoi ce type de composant est critique dans une appliance réseau.

---

### Partie 3 – Impact sur le système d’information

**Question 7**  
La console d’administration est-elle susceptible d’être exposée :
- à Internet,
- au réseau interne,
- uniquement à des administrateurs ?

Expliquez les risques associés à cette exposition.

**Question 8**  
Quels impacts ces vulnérabilités pourraient-elles avoir sur le système d’information ?
- accès non autorisé,
- compromission du réseau,
- élévation de privilèges,
- déni de service,
- fuite d’informations.

**Question 9**  
Pourquoi une vulnérabilité logicielle dans un composant fournisseur engage-t-elle la responsabilité de l’administrateur SISR, même sans modification du code source ?

---

### Partie 4 – Décision en tant qu’administrateur SISR

**Question 10**  
Quelle décision recommandez-vous ?
- mise en production,
- mise en production conditionnelle,
- refus de mise en production,
- demande de correctif au fournisseur.

Argumentez votre réponse.

**Question 11**  
Quelles actions pouvez-vous mener sans modifier le code source ?
- mise à jour de l’appliance,
- restriction des accès,
- filtrage réseau,
- supervision renforcée,
- durcissement de configuration.

**Question 12**  
Quels contrôles supplémentaires recommanderiez-vous avant validation finale ?
- audit de configuration,
- tests d’intrusion,
- supervision et journalisation,
- revue de conformité sécurité.

---

### Partie 5 – Synthèse professionnelle

**Question 13**  
En 5 à 10 lignes maximum, rédigez une synthèse destinée à un RSSI ou à un responsable informatique :
- état de sécurité du composant audité,
- niveau de risque pour le système d’information,
- décision recommandée et justification.

---

## Rendu attendu

- Un fichier `SYNTHESE.md` (ou PDF) contenant les réponses argumentées.
- Le rapport `dependency-check-report.html` en annexe si demandé.

---

## Rappel important

Vous êtes dans une posture **SISR** :  
vous n’êtes pas développeur du composant, mais **responsable de son intégration sécurisée** dans le système d’information.

---

## Compétences évaluées (SISR)

- Exploiter un rapport d’audit de sécurité.
- Analyser l’exposition et les impacts sur une infrastructure réseau.
- Prendre une décision argumentée de mise en production.
- Mettre en œuvre une démarche de gestion des risques cyber.
