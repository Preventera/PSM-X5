---
name: psm-sis-sif-sil-verification
description: >
  Vérification SIL selon IEC 61511/ISA-84, lifecycle SIS complet (analyse→réalisation→opération),
  monitoring PFD temps réel, proof testing, Safety Requirements Specification (SRS), architectural
  constraints. Utiliser dès que l'utilisateur mentionne SIS, SIF, SIL, IEC 61511, ISA-84, PFD,
  PFH, proof test interval, functional safety, safety instrumented system, ou intégrité des systèmes
  de sécurité instrumentés.
---

# SIS / SIF / SIL Verification — Skill Process Safety

## 1. Fondamentaux

### 1.1 Définitions clés

- **SIS** (Safety Instrumented System) : système combinant capteurs + solveur logique + éléments finaux, conçu pour amener le procédé à un état sûr
- **SIF** (Safety Instrumented Function) : fonction de sécurité spécifique implémentée par le SIS, protégeant contre un scénario dangereux identifié
- **SIL** (Safety Integrity Level) : niveau discret (1-4) spécifiant l'intégrité de sécurité requise pour la SIF. SIL 4 = plus haute intégrité, SIL 1 = plus basse

### 1.2 Standards applicables

| Standard | Portée |
|----------|--------|
| IEC 61508 | Standard parent générique (functional safety E/E/PE) |
| IEC 61511 / ANSI/ISA-84 | Application SIS secteur process (raffinage, chimie, pharma, mines) |
| IEC 61513 | Nucléaire |
| IEC 62061 | Machines/manufacturing |

OSHA reconnaît IEC 61511/ISA-84 comme RAGAGEP (lettre OSHA mars 2000 à ISA).

## 2. Safety Lifecycle IEC 61511

### 2.1 Trois phases principales

**Phase 1 — Analyse** :
- Hazard & Risk Assessment (HAZOP, LOPA)
- Allocation des fonctions de sécurité au SIS
- Détermination du SIL cible par SIF
- Rédaction Safety Requirements Specification (SRS)

**Phase 2 — Réalisation** :
- Conception SIS (hardware + software)
- Vérification SIL : PFDavg ≤ target + architectural constraints
- Installation, commissioning, validation

**Phase 3 — Opération** :
- Proof testing périodique (test complet de la boucle SIF)
- Maintenance, documentation demands/failures
- Monitoring PFD réel vs calculé
- MOC strict pour toute modification SIF
- Functional Safety Assessment (FSA) aux 5 stages clés

### 2.2 Safety Requirements Specification (SRS)

Le SRS est le livrable le plus critique — pont entre analyse et conception :

1. Description fonctionnelle de chaque SIF (action requise, conditions de déclenchement)
2. Target SIL et PFDavg maximum
3. Temps de réponse requis (process safety time)
4. Conditions environnementales et opérationnelles
5. Diagnostics et tolérance aux pannes
6. Exigences de proof testing
7. Actions sur détection de faute

## 3. Vérification SIL

### 3.1 Trois critères à satisfaire simultanément

Pour chaque SIF, les 3 critères suivants DOIVENT être satisfaits :

1. **PFDavg** : la probabilité de défaillance dangereuse à la demande (low demand) doit être dans la plage du SIL cible
2. **Architectural constraints** : redondance minimale (HFT = Hardware Fault Tolerance)
3. **Systematic capability** : chaque composant doit avoir la systematic capability ≥ SIL cible

### 3.2 Tables SIL (Low Demand Mode)

| SIL | PFDavg | RRF | Availability |
|-----|--------|-----|-------------|
| 1 | [10⁻¹, 10⁻²) | 10-100 | 90-99% |
| 2 | [10⁻², 10⁻³) | 100-1000 | 99-99.9% |
| 3 | [10⁻³, 10⁻⁴) | 1000-10000 | 99.9-99.99% |
| 4 | [10⁻⁴, 10⁻⁵) | 10000-100000 | 99.99-99.999% |

### 3.3 Calcul PFDavg simplifié (1oo1, low demand)

```
PFDavg ≈ λDU × TI / 2
```

Où : λDU = taux de défaillance dangereuse non détectée, TI = proof test interval

Pour architectures votées (1oo2, 2oo3) : formules combinatoires avec β-factor (common cause).

### 3.4 Proof Test Interval

L'intervalle de test est CRITIQUE pour maintenir le SIL :
- Augmenter TI → augmente PFDavg → peut dégrader sous le SIL cible
- Diminuer TI → réduit PFDavg mais augmente coûts opérationnels
- Proof test doit couvrir la boucle COMPLÈTE (capteur → logique → élément final)
- Proof test coverage < 100% → partial stroke testing, diagnostic coverage

## 4. Monitoring PSM-X5

### 4.1 Agent A8-MechInt

L'agent A8-MechInt de PSM-X5 assure :
- Surveillance continue des taux de défaillance réels vs calculés
- Alertes prédictives quand PFD trending vers la limite du SIL cible
- Vérification automatique que proof tests sont à jour
- Documentation automatique pour audit IEC 61511 compliance
- Intégration SENTINEL·X5 pour corrélation alarmes SIS

### 4.2 KPIs SIS

- PFDavg réelle vs target par SIF
- % SIF proof-testées à temps
- Nombre de demands réelles sur SIS
- Nombre de spurious trips (faux déclenchements)
- Dangerous detected/undetected failure ratio
- Proof test overdue count

## 5. Functional Safety Assessment (FSA)

5 stages obligatoires selon IEC 61511 :
- **Stage 1** : Après H&RA + SRS
- **Stage 2** : Après conception SIS
- **Stage 3** : Après commissioning/validation (AVANT que le danger soit présent)
- **Stage 4** : Après expérience opération/maintenance
- **Stage 5** : Après toute modification

Chaque FSA requiert un assesseur indépendant compétent.
