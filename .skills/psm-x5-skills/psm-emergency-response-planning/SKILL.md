---
name: psm-emergency-response-planning
description: >
  Plans d'urgence process safety pour relâchements HHC (toxique, inflammable, explosif).
  Modélisation dispersion, coordination PMU/autorités, HAZWOPER compliance, drills et
  exercices. Couvre OSHA PSM Element #12. Utiliser dès que l'utilisateur mentionne plan
  d'urgence, emergency response, EAP, relâchement chimique, dispersion modeling, HAZWOPER,
  évacuation, ou coordination urgence process safety.
---

# Emergency Response Planning — Skill Process Safety

## 1. Cadre réglementaire

### OSHA PSM 29 CFR 1910.119(n) — Emergency Planning and Response
- EAP (Emergency Action Plan) requis pour le site entier conforme 1910.38
- Procédures détaillées pour gérer relâchements mineurs HHC
- Si site couvert HAZWOPER (1910.120), EAP doit satisfaire exigences HAZWOPER additionnelles
- Coordination avec autorités d'urgence locales

### EPA RMP — Emergency Response Program
- Programme de réponse d'urgence coordonné avec community emergency planning
- Exercices et drills périodiques

## 2. Composantes du plan d'urgence PSM

### 2.1 Éléments EAP essentiels
1. Procédures d'évacuation et routes d'urgence
2. Procédures pour opérateurs restant pour shutdown critique
3. Système de comptage/accounting du personnel après évacuation
4. Procédures de sauvetage et premiers soins
5. Moyens d'alerte (sirènes, PA, radio)
6. Contacts d'urgence (interne + externe)
7. Coordination avec services d'urgence externes

### 2.2 Scénarios de relâchement HHC
Pour chaque HHC sur site, documenter :
- Propriétés dangereuses (toxicité, inflammabilité, réactivité)
- Scénarios crédibles de relâchement (worst-case et alternative)
- Zones d'impact modélisées (toxic endpoint, LEL, thermal radiation)
- Actions de réponse spécifiques par scénario

### 2.3 Modélisation dispersion
Outils de modélisation pour estimer zones d'impact :
- ALOHA (Areal Locations of Hazardous Atmospheres) — EPA/NOAA
- PHAST (Process Hazard Analysis Software Tool) — DNV
- CANARY — Quest Consultants
- Paramètres clés : débit relâchement, conditions météo, topographie, durée

## 3. Niveaux de réponse

| Niveau | Description | Actions |
|--------|------------|---------|
| 1 - Alerte | Relâchement mineur, confiné à zone | Réponse locale, monitoring, notification |
| 2 - Urgence site | Relâchement significatif, impact multi-zones | Évacuation partielle, ERT activé, autorités notifiées |
| 3 - Urgence majeure | Relâchement catastrophique, impact off-site | Évacuation complète, PMU activé, coordination municipale |

## 4. Exercices et drills

- **Tabletop** : simulation théorique avec décideurs (trimestriel)
- **Drill fonctionnel** : test d'un composant spécifique (alarmes, ERT, évacuation)
- **Exercice pleine échelle** : simulation réaliste avec tous acteurs (annuel minimum)
- Documentation de chaque exercice avec lessons learned et actions correctives

## 5. Intégration PSM-X5

- **A12-Emergency** : plans dynamiques, simulation what-if, coordination PMU auto
- **SafeTwinX5** : simulation 3D de dispersion sur jumeau numérique
- **SENTINEL·X5** : détection automatique situation d'urgence via alarmes corrélées
- **SafeScan360** : surveillance vidéo zones critiques en cas d'incident
- **A6-Contractor** : vérification formation urgence sous-traitants sur site
