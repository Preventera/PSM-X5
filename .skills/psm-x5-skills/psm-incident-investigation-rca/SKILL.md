---
name: psm-incident-investigation-rca
description: >
  Investigation incidents process safety et Root Cause Analysis (RCA). 5-Why, Bow-Tie
  post-incident, TapRooT, arbre des causes, corrélation Knowledge Graph, actions correctives
  SMART. Couvre OSHA PSM Element #11. Utiliser dès que l'utilisateur mentionne investigation
  incident, root cause analysis, RCA, 5-Why, Bow-Tie post-incident, near-miss process safety,
  LOPC investigation, ou analyse causale process.
---

# Incident Investigation & RCA — Skill Process Safety

## 1. Cadre réglementaire

OSHA PSM 29 CFR 1910.119(m) — Incident Investigation :
- Enquête requise pour tout incident résultant ou pouvant résulter en relâchement catastrophique HHC
- Initiée dans les **48 heures** suivant l'incident
- Équipe multidisciplinaire incluant au minimum un expert procédé, un expert investigation
- Rapport documentant : date, description, facteurs causaux, recommandations
- Actions correctives suivies et résolues
- Rapport révisé par personnel affecté
- Rapports conservés minimum **5 ans**

## 2. Méthodologie RCA Process Safety

### 2.1 5-Why Structuré
Poser "Pourquoi?" de manière itérative en suivant les chaînes causales :
- Causes immédiates (techniques)
- Causes sous-jacentes (humaines, procédurales)
- Causes racines (système de management, culture)

### 2.2 Arbre des Causes (Causal Tree)
Structure arborescente : conséquence → événements → causes → racines
Chaque branche représente une chaîne causale indépendante.

### 2.3 Bow-Tie Post-Incident
- Identifier les barrières qui ont ÉCHOUÉ (prévention et mitigation)
- Documenter le mode de défaillance de chaque barrière
- Différencier : barrière absente, barrière dégradée, barrière contournée

### 2.4 Classification API 754
Classifier l'incident en Tier 1, 2, 3, ou 4 :
- **Tier 1** : LOPC avec conséquence majeure (injury DAFW+, fatalité, >$100K dommages, feu/explosion)
- **Tier 2** : LOPC conséquence moindre (recordable injury, >$2500 dommages)
- **Tier 3** : challenge au système de barrières (near-miss, demande sur SIS)
- **Tier 4** : faiblesse composant individuel (leading indicator)

## 3. Facteurs causaux en process safety

### 3.1 Triangle des causes (données CCPS/industrie)
- **Facteurs humains** (~42%) : fatigue, erreur procédurale, prise de risque, charge cognitive
- **Facteurs organisationnels** (~35%) : communication, leadership, culture, maintenance différée
- **Facteurs techniques** (~23%) : défaillance équipement, corrosion, conditions atmosphériques

### 3.2 Causes fréquentes LOPC
- MOC inadéquat ou absent
- Intégrité mécanique déficiente (corrosion, fatigue)
- Erreur opérateur (procédure non suivie)
- SIS/SIF défaillante (PFD dépassée)
- Alarm flood masquant alarme critique
- Maintenance différée / inspection retardée

## 4. Actions correctives

### 4.1 Format SMART
Chaque recommandation doit être :
- **S**pécifique : action précise identifiée
- **M**esurable : critère de complétion défini
- **A**ssignable : responsable nommé
- **R**éaliste : faisable dans le contexte
- **T**emporelle : échéance définie

### 4.2 Hiérarchie des contrôles (process safety)
1. Élimination du danger (design inherently safer)
2. Substitution (matériau moins dangereux)
3. Contrôle engineering (SIS, interlock, confinement)
4. Contrôle administratif (procédure, formation)
5. EPI (dernière ligne)

## 5. Intégration PSM-X5

- **A11-RCA** : Root Cause Analysis IA assisté, 5-Why automatisé, Bow-Tie post-incident
- **SafetyGraph (Neo4j)** : corrélation causale cross-incidents sur 22M+ records
- **A13-Audit** : tracking actions correctives avec escalade automatique
- **BehaviorX** : analyse facteurs humains/comportementaux pré-incident
