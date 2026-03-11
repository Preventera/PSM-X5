---
name: psm-moc-pssr-workflow
description: >
  Management of Change (MOC) end-to-end et Pre-Startup Safety Review (PSSR) conformes
  OSHA PSM 29 CFR 1910.119(l)(i). Workflow complet : soumission, screening, évaluation impact,
  approbation, exécution, PSSR, clôture. Utiliser dès que l'utilisateur mentionne MOC, Management
  of Change, PSSR, Pre-Startup Safety Review, changement procédé, modification équipement, ou
  gestion des changements process safety.
---

# MOC & PSSR Workflow — Skill Process Safety

## 1. Cadre réglementaire

### OSHA PSM 29 CFR 1910.119(l) — Management of Change
Procédures écrites requises pour gérer les changements (sauf replacement-in-kind) affectant :
- Chimie du procédé, Technologie, Équipement, Procédures, Installations

Chaque changement doit évaluer AVANT implémentation :
1. **Base technique** du changement proposé
2. **Impact sur sécurité et santé** des travailleurs
3. **Modifications** aux procédures opérationnelles
4. **Période** nécessaire pour le changement
5. **Autorisations** requises

### OSHA PSM 29 CFR 1910.119(i) — Pre-Startup Safety Review
PSSR requise pour tout nouvel équipement, équipement modifié, ou installation modifiée.

## 2. Workflow MOC 8 étapes

### Étape 1 : Initiation & Classification
- Capturer qui/quoi/où/pourquoi et date go-live visée
- Classifier : process, équipement, procédural, organisationnel
- Screening : est-ce un replacement-in-kind (RIK) ? Si oui → pas de MOC complet
- Assigner catégorie risque préliminaire → profondeur de revue

### Étape 2 : Définition scope & frontières
- Documenter l'enveloppe complète : équipements, documents, procédures, rôles affectés
- Identifier impacts upstream/downstream
- Verrouiller le scope (scope creep = failure mode classique MOC)

### Étape 3 : Évaluation impact (multidisciplinaire)
Convoquer : opérations, ingénierie, maintenance, HSE, qualité, sous-traitants si applicable.
Évaluer impacts sur : sécurité, opérabilité, fiabilité, qualité produit, environnement, ergonomie.

### Étape 4 : Analyse de risque (HIRA)
Méthode adaptée au niveau de risque :
- Faible : matrice de risque, JSA
- Moyen : What-If / HAZID
- Élevé : HAZOP delta (partiel sur zone changée)
Identifier nouveaux dangers et définir protections supplémentaires.

### Étape 5 : Approbation
Routage multi-approbateurs basé sur catégorie risque :
- Routine : superviseur process + HSE
- Significatif : + engineering manager + operations manager
- Critique : + plant manager + corporate safety

### Étape 6 : Mise à jour documentation
AVANT le changement, mettre à jour :
- Process Safety Information (PSI) : P&ID, specs équipement, limites opératoires
- Procédures opérationnelles (SOPs)
- Programme d'intégrité mécanique
- PHA/HAZOP (si applicable)

### Étape 7 : Formation
Tous les employés/sous-traitants affectés doivent être formés sur :
- Nouvelles procédures AVANT startup
- Nouveaux dangers identifiés
- Changements aux limites opératoires
Documentation de formation requise.

### Étape 8 : PSSR & Clôture
- Conduire PSSR (voir section 3)
- Vérifier que TOUTES les actions pré-startup sont complétées
- Go/No-Go decision
- Archiver pack MOC complet avec traçabilité PROV-O

## 3. Pre-Startup Safety Review (PSSR)

### 3.1 Checklist PSSR dynamique

La PSSR vérifie que :
- [ ] Construction/modification conforme aux spécifications de conception
- [ ] Procédures opérationnelles en place, révisées et accessibles
- [ ] PHA complétée, recommandations résolues ou implémentées
- [ ] PSI mise à jour (P&ID, specs, limites)
- [ ] Formation de TOUS les opérateurs concernés complétée
- [ ] Équipements critiques inspectés (intégrité mécanique)
- [ ] Systèmes de sécurité testés et opérationnels (SIF, PSV, détecteurs)
- [ ] Plan d'urgence mis à jour si applicable
- [ ] MOC documenté et approuvé
- [ ] Autorisation de startup signée par tous les approbateurs requis

### 3.2 PSSR spécialisées par type de changement

- **Changement chimique** : MSDS vérifiée, compatibilité matériaux, HAZOP delta
- **Changement équipement** : RAGAGEP conforme, inspection, test hydrostatique si applicable
- **Changement procédural** : SOPs révisées, formation validée
- **Changement organisationnel** : staffing adéquat, compétences vérifiées

## 4. MOC temporaire vs permanent

- **Temporaire** : date d'expiration obligatoire, suivi automatique, workflow de reversion ou conversion
- **Permanent** : mise à jour permanente de toute documentation affected
- MOC temporaire non clôturé à expiration = non-conformité critique

## 5. Intégration PSM-X5

- **A10-MOC** : workflow complet, évaluation impact auto, notifications cascade
- **A7-PSSR** : checklists dynamiques, validation multi-signateurs
- **A2-PSI-RAG** : mise à jour PSI automatique en cascade
- **A3-PHA-Engine** : HAZOP delta automatique si changement le requiert
- **A5-Training** : module formation auto-généré via LiteraCIA
- **A13-Audit** : archivage pack évidence PROV-O complet

## 6. Causes d'échec MOC communes

- Changements "cachés" : petites modifications setpoints/alarmes sans MOC
- Scope creep non maîtrisé
- PSSR superficielle (checkbox mentality)
- Formation retardée après startup
- MOC temporaires expirés non clôturés
- Changements organisationnels (réduction effectifs) non couverts par MOC
