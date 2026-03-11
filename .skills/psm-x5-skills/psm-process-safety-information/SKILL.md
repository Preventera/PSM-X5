---
name: psm-process-safety-information
description: >
  Gestion Process Safety Information (PSI) : documentation chimie process, technologie,
  équipements (P&ID, MSDS/SDS, specs, limites opératoires). Indexation RAG, mise à jour
  cascade MOC. Couvre OSHA PSM Element #2. Utiliser dès que l'utilisateur mentionne PSI,
  Process Safety Information, P&ID, MSDS, SDS, limites opératoires, specs équipement,
  documentation process safety, ou information sécurité procédés.
---

# Process Safety Information — Skill Process Safety

## 1. Cadre OSHA PSM Element #2

29 CFR 1910.119(d) — Compilation de la PSI AVANT la PHA :

### 1.1 Information sur les HHC
- Toxicité, limites d'exposition permises
- Données physiques/chimiques (point flash, LEL/UEL, pression vapeur)
- Données réactivité et stabilité thermique
- Effets corrosifs/nécroses
- Risques associés au mélange avec autres produits

### 1.2 Information sur la technologie du procédé
- Diagrammes de flux (Block Flow, PFD)
- Chimie du procédé (réactions, stœchiométrie)
- Inventaire maximum prévu de HHC
- Limites opératoires sûres (T, P, débit, niveau, composition)
- Conséquences des déviations au-delà des limites

### 1.3 Information sur les équipements
- Matériaux de construction
- P&ID (Piping and Instrumentation Diagrams)
- Classification électrique (NEC/ATEX zones)
- Design codes et standards utilisés (RAGAGEP)
- Systèmes de relief (design basis, sizing)
- Systèmes de ventilation
- Bilan de sécurité (si équipement existant avant PSM)

## 2. Gestion PSI dans PSM-X5

### 2.1 Agent A2-PSI-RAG
- Indexation RAG de toute la documentation PSI (embeddings 1536 dims Pinecone)
- Recherche sémantique langage naturel sur P&ID, MSDS, specs
- Extraction automatique de données depuis documents techniques
- Alertes sur documents obsolètes ou incohérents

### 2.2 Mise à jour cascade via MOC
Chaque MOC déclenche automatiquement la vérification et mise à jour :
1. P&ID affectés → marqués pour révision
2. Limites opératoires → vérifiées contre nouvelles conditions
3. MSDS/SDS → vérifiées si nouveau produit chimique
4. Specs équipement → mises à jour si modification
5. PHA/HAZOP → delta analysis si changement significatif

### 2.3 Version control
- Chaque document PSI est versionné avec historique complet
- Lien bidirectionnel MOC ↔ document PSI modifié
- Traçabilité PROV-O de chaque modification

## 3. Accessibilité PSI

OSHA exige que la PSI soit accessible à TOUS les employés impliqués dans le procédé, incluant sous-traitants. Pas de restriction trade secrets pour les informations nécessaires à la sécurité.
