---
name: psm-hazop-lopa-analysis
description: >
  Conduire des analyses HAZOP assistées IA (noeuds, guide words, déviations, causes,
  conséquences, protections), LOPA semi-quantitatif (IEF, IPL, PFD, TMEF, SIL
  determination), Bow-Tie automatisé. Utiliser ce skill dès que l'utilisateur mentionne
  HAZOP, PHA, LOPA, Bow-Tie, analyse de dangers procédés, déviations, guide words,
  couches de protection, SIL determination, ou toute analyse de risque process safety.
---

# HAZOP / LOPA Analysis — Skill Process Safety

## 1. Quand utiliser ce Skill

- Analyse HAZOP (Hazard and Operability Study) pour tout procédé industriel
- LOPA (Layer of Protection Analysis) pour détermination SIL
- Génération Bow-Tie (menaces → événement → conséquences → barrières)
- Toute évaluation PHA (Process Hazard Analysis) sous OSHA PSM Element #3

## 2. Méthodologie HAZOP

### 2.1 Structure d'un HAZOP

L'étude HAZOP décompose le procédé en **noeuds** (sections avec frontières définies) puis applique systématiquement des **guide words** aux **paramètres process** pour identifier les **déviations** du design intent.

**Noeuds typiques** : lignes de transfert, réacteurs, colonnes, échangeurs, stockage, systèmes de relief.

### 2.2 Guide Words Standards (IEC 61882)

| Guide Word | Signification | Exemples de déviation |
|------------|--------------|----------------------|
| NO / NOT | Négation complète | No Flow, No Reaction |
| MORE | Augmentation quantitative | High Temperature, High Pressure, More Flow |
| LESS | Diminution quantitative | Low Temperature, Low Pressure, Less Flow |
| AS WELL AS | Modification qualitative (ajout) | Contamination, Phase supplémentaire |
| PART OF | Modification qualitative (perte) | Composition incomplète |
| REVERSE | Direction opposée | Reverse Flow, Reverse Reaction |
| OTHER THAN | Substitution complète | Wrong Material, Wrong Sequence |
| EARLY | Occurrence prématurée | Early Reaction, Early Valve Opening |
| LATE | Occurrence retardée | Late Shutdown, Delayed Response |
| BEFORE / AFTER | Séquence erronée | Step Before/After intended |

### 2.3 Paramètres Process

Température, Pression, Débit (Flow), Niveau, Composition, pH, Viscosité, Vitesse de réaction, Phase, Concentration, Temps de séjour, Agitation, Densité.

### 2.4 Format de Sortie HAZOP

Pour chaque déviation identifiée, documenter :

1. **Noeud** : identifiant et description
2. **Paramètre** : variable process concernée
3. **Guide Word** : mot-clé appliqué
4. **Déviation** : description de l'écart (ex: "High Pressure")
5. **Causes** : toutes causes crédibles (défaillance équipement, erreur humaine, externe)
6. **Conséquences** : impact sans protections (worst case)
7. **Protections existantes** : alarmes, interlocks, PSV, SIF, procédures
8. **RPL** (Risk Priority Level) : H/M/L basé sur matrice conséquence × probabilité
9. **Recommandations** : actions requises si protections insuffisantes
10. **Responsable** et échéance

### 2.5 Règles HAZOP

- Ne PAS considérer la défaillance simultanée de 2+ événements indépendants (probabilité trop faible)
- Considérer que TOUTES les protections ont échoué pour évaluer la conséquence worst case
- Chaque recommandation doit être assignée, datée et suivie
- L'équipe HAZOP doit être multidisciplinaire : facilitateur, scribe, ingénieur procédé, opérateur, maintenance, sécurité
- Revalider HAZOP à chaque MOC significatif ou minimum tous les 5 ans

## 3. Méthodologie LOPA

### 3.1 Principes LOPA

LOPA (Layer of Protection Analysis) est une méthode semi-quantitative développée par CCPS (AIChE) pour :
- Évaluer l'adéquation des IPL (Independent Protection Layers) existantes
- Déterminer le SIL requis pour les SIF (Safety Instrumented Functions)
- Calculer la fréquence mitigée d'un scénario dangereux

### 3.2 Formule fondamentale

```
TMEF = Σ [ IEFᵢ × Π PFDᵢⱼ × Π CMₖ ]
```

Où :
- **TMEF** = Total Mitigated Event Frequency (fréquence mitigée)
- **IEF** = Initiating Event Frequency (fréquence de l'événement initiateur)
- **PFD** = Probability of Failure on Demand de chaque IPL
- **CM** = Conditional Modifiers (probabilité d'occupation, probabilité d'ignition, etc.)

### 3.3 Critères IPL (Independent Protection Layer)

Une protection n'est IPL QUE si elle satisfait TOUS ces critères (CCPS) :

1. **Spécificité** : capable de détecter et prévenir/mitiger le scénario spécifique
2. **Indépendance** : non affectée par la défaillance d'une autre IPL ou par l'événement initiateur
3. **Fiabilité** : PFD quantifiable et documentable
4. **Auditabilité** : conçue pour permettre validation/test périodique

### 3.4 PFD Typiques des IPL

| IPL Type | PFD Typique | RRF |
|----------|------------|-----|
| Design process (containment) | 10⁻² | 100 |
| BPCS control loop | 10⁻¹ | 10 |
| Alarme + intervention opérateur | 10⁻¹ | 10 |
| SIF SIL 1 | 10⁻¹ à 10⁻² | 10-100 |
| SIF SIL 2 | 10⁻² à 10⁻³ | 100-1000 |
| SIF SIL 3 | 10⁻³ à 10⁻⁴ | 1000-10000 |
| Relief device (PSV) | 10⁻² | 100 |
| Rupture disk | 10⁻² | 100 |
| Dike / bund wall | 10⁻² | 100 |
| Deluge system | 10⁻² | 100 |

### 3.5 IEF Typiques

| Événement initiateur | Fréquence (par an) |
|---------------------|-------------------|
| Défaillance vanne contrôle | 10⁻¹ |
| Défaillance pompe | 10⁻¹ |
| Erreur humaine (opérateur) | 10⁻¹ à 10⁻² |
| Perte utilités (électricité, air, eau) | 10⁻¹ |
| Défaillance instrument | 10⁻¹ |
| Corrosion/érosion (perte confinement) | 10⁻² |
| Événement externe (impact) | 10⁻² à 10⁻³ |
| Rupture tuyauterie (fatigue) | 10⁻³ à 10⁻⁴ |

### 3.6 Détermination SIL

Si TMEF > Tolerable Risk → gap identifié → SIF requise :

| SIL | PFD Range | RRF Range |
|-----|-----------|-----------|
| SIL 1 | ≥10⁻² à <10⁻¹ | >10 à ≤100 |
| SIL 2 | ≥10⁻³ à <10⁻² | >100 à ≤1000 |
| SIL 3 | ≥10⁻⁴ à <10⁻³ | >1000 à ≤10000 |
| SIL 4 | ≥10⁻⁵ à <10⁻⁴ | >10000 à ≤100000 |

Note : SIL 4 est rare en process industries (principalement nucléaire/aérospatial).

### 3.7 Target Mitigated Event Likelihood (TMEL)

Risque tolérable typique : 10⁻⁴ à 10⁻⁵ événements/an pour conséquences fatales.

## 4. Bow-Tie Automatisé

### 4.1 Structure Bow-Tie

```
MENACES → [Barrières Prévention] → ÉVÉNEMENT TOP → [Barrières Mitigation] → CONSÉQUENCES
```

- **Gauche** : Menaces (causes identifiées en HAZOP) avec barrières de prévention
- **Centre** : Événement redouté central (perte de confinement, runaway, etc.)
- **Droite** : Conséquences (explosion, relâchement toxique, incendie) avec barrières de mitigation
- Chaque barrière = IPL avec PFD assigné

### 4.2 Intégration AgenticX5

Dans le contexte PSM-X5 :
- **A3-PHA-Engine** génère les HAZOP et Bow-Tie automatisés
- **A2-PSI-RAG** fournit les P&ID indexés et données PSI
- **SafetyGraph (Neo4j)** corrèle avec 22M+ incidents historiques
- **A8-MechInt** vérifie SIS/SIF/SIL
- **A13-Audit** archive dans pack évidence PROV-O

## 5. Standards de référence

- **IEC 61882** : HAZOP methodology standard
- **CCPS LOPA** : Layer of Protection Analysis guidelines (2001, 2015)
- **IEC 61511 / ISA-84** : SIS lifecycle, SIL determination
- **OSHA 29 CFR 1910.119(e)** : Process Hazard Analysis requirement
- **API RP 754** : Process Safety Performance Indicators
