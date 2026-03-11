---
name: psm-mechanical-integrity-ragagep
description: >
  Intégrité mécanique des équipements critiques PSM et RAGAGEP (Recognized and Generally
  Accepted Good Engineering Practices). Pressure vessels (API 510), piping (API 570),
  storage tanks (API 653), relief devices (API 520/521), rotating equipment. Utiliser dès
  que l'utilisateur mentionne intégrité mécanique, RAGAGEP, inspection équipement, API 510,
  API 570, API 653, ASME, relief valve, pressure vessel, ou maintenance prédictive process safety.
---

# Mechanical Integrity & RAGAGEP — Skill Process Safety

## 1. Cadre OSHA PSM Element #8

29 CFR 1910.119(j) couvre l'intégrité mécanique de :
1. Pressure vessels et storage tanks
2. Piping systems (incluant composants : vannes, brides, joints)
3. Relief and vent systems and devices
4. Emergency shutdown systems
5. Controls (monitoring, alarmes, interlocks)
6. Pumps (ajouté par interprétation OSHA)

## 2. RAGAGEP — Standards de Référence

### 2.1 Définition OSHA
RAGAGEP = base pour ingénierie, opération ou maintenance, dérivée de codes, standards, rapports techniques ou pratiques recommandées publiés.

### 2.2 Hiérarchie RAGAGEP (non-officielle)

| Catégorie | Exemples | Acceptation OSHA |
|-----------|----------|-----------------|
| Codes largement adoptés | NFPA 70, NFPA 101 | Acceptés directement |
| Documents consensus ANSI | ASME B31.3, ASME BPVC | Largement acceptés |
| Documents non-consensus industrie | API, Chlorine Institute | Acceptés si applicables |
| Standards internes entreprise | Procédures corporate MI | Acceptés si démontrent bonnes pratiques |

### 2.3 Standards clés par type d'équipement

**Pressure Vessels** :
- ASME BPVC (Boiler and Pressure Vessel Code) — conception
- API 510 — inspection en service (min 10 ans externe, 5 ans interne)
- API 579-1/ASME FFS-1 — fitness-for-service

**Piping** :
- ASME B31.3 — process piping design
- API 570 — inspection piping en service
- API 574 — inspection pratiques piping

**Storage Tanks** :
- API 650 — conception tanks atmosphériques
- API 653 — inspection tanks en service (5 ans externe)
- API 620 — tanks basse pression

**Relief Devices** :
- API 520 Part I & II — sizing et installation PSV
- API 521 — pressure-relieving and depressuring systems
- ASME BPVC Section VIII — accumulation maxima
- API 576 — inspection relief devices

**Rotating Equipment** :
- API 610 — pompes centrifuges
- API 617 — compresseurs axiaux/centrifuges
- API 612 — turbines à vapeur

## 3. Programme d'intégrité mécanique

### 3.1 Éléments requis

1. **Inventaire équipement** : liste complète avec P&ID reference, RAGAGEP applicable
2. **Procédures écrites** : par catégorie d'équipement, référençant les standards applicables
3. **Formation personnel** : maintenance et inspection formés sur process + dangers
4. **Inspections et tests** : selon RAGAGEP et recommandations fabricant
5. **Documentation** : date, inspecteur, identifiant, description, résultats
6. **Correction déficiences** : avant remise en service ou mesures intérimaires
7. **Assurance qualité** : équipements neufs convenables pour l'application process

### 3.2 Approche Risk-Based Inspection (RBI)

API 580/581 permet d'ajuster les fréquences d'inspection basées sur :
- Taux de corrosion et mécanismes de dégradation
- Conditions opératoires (T, P, milieu)
- Conséquence de défaillance (sécurité, environnement, économique)
- Historique d'inspection

### 3.3 Relief Device Management

Documentation requise pour chaque PSV :
- Identification et set pressure
- Date de test, résultats (pression d'ouverture réelle, reseat)
- Pass/Fail et action corrective si fail
- Évaluation rétrospective si PSV était hors tolérance

## 4. Intégration PSM-X5

- **A8-MechInt** : monitoring IoT prédictif, compliance RAGAGEP auto, inspection CV assistée
- **SafetyGraph** : corrélation défaillances équipement cross-sites
- **SENTINEL·X5** : alarm management ISA-18.2 sur alarmes intégrité
- **A13-Audit** : documentation MI pour pack évidence audit
