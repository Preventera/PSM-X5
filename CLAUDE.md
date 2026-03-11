# CLAUDE.md — PSM-X5 Process Safety Management

> Mémoire de projet structurée pour Claude Code et Claude.ai
> Dernière mise à jour : Mars 2026 — v1.0

## Identité du Projet

**PSM-X5** (Process Safety Management X5) est la 26e plateforme de l'écosystème AgenticX5, dédiée à l'automatisation intelligente de la gestion de la sécurité des procédés industriels. 14 agents IA couvrant les 14 éléments OSHA PSM (29 CFR 1910.119).

**Organisation** : Preventera Inc. / AgenticX5
**Repo** : github.com/Preventera/PSM-X5
**Production** : psm-x5.netlify.app
**Contact** : team@agenticx5.com

## Architecture — Contrainte Fondamentale

**SINGLE-FILE HTML.** Le Hub PSM-X5 vit dans `index.html` (~66 KB). Pas de build step, pas de bundler, pas de framework. HTML5 + CSS3 + JavaScript ES6+ inline. Déploiement Netlify CDN statique.

### Pourquoi single-file :
- Portabilité totale (email, USB, offline)
- Zéro dépendance serveur
- Demo instantanée (ouvrir dans un navigateur)
- Déploiement Netlify en 15 secondes

### Librairies externes (CDN uniquement) :
- Chart.js v4.4.1 — Charts (radar 14 éléments, line SIL trends)
- Google Fonts — Outfit + JetBrains Mono

## Structure des 5 Dimensions

```
index.html (PSM-X5.html)
├── Hub Landing (14 cartes PSM elements, agents assignés)
├── D1 — HAZOP/PHA Engine (--d1: #06b6d4 cyan)
│   ├── 3 noeuds HAZOP interactifs (Réacteur, Colonne, Stockage HHC)
│   ├── Table déviations avec guide words et RPL
│   ├── Bow-Tie SVG automatisé (menaces → barrières → conséquences)
│   ├── ★ HAZOP IA assisté (Claude API — prévu v2.0)
│   └── Stats : -60% durée, 95% couverture, <5min Bow-Tie
├── D2 — MOC & PSSR Workflow (--d2: #f59e0b amber)
│   ├── Simulation MOC live 8 étapes (play button animé)
│   ├── Timeline agents A10-MOC → A2-PSI → A3-PHA → A4-OpsProc → A5-Training → A8-MechInt → A7-PSSR → A13-Audit
│   ├── Checklist PSSR dynamique (coches progressives)
│   └── Stats : -80% temps MOC, 100% PSI updated, PROV-O
├── D3 — SIS/SIL Monitoring (--d3: #a855f7 purple)
│   ├── 6 SIF cards avec gauges PFD temps réel
│   ├── Chart tendance PFD 90 jours (SIF-301 alerte, SIF-003 warning)
│   ├── Monitoring IEC 61511 compliance
│   └── Stats : 98.2% SIF conformes, -72% pannes imprévues
├── D4 — Audit 14 Éléments (--d4: #10b981 emerald)
│   ├── Radar Chart.js 14 axes (scoring continu par élément)
│   ├── Grille audit 14 cartes avec barres conformité
│   ├── Bouton "Simuler audit" (randomize scores)
│   ├── ★ Pack évidence IA (Claude API — prévu v2.0)
│   └── Stats : <2h pack évidence, PROV-O traçabilité, -99% temps préparation
└── D5 — Agents & Écosystème (--d5: #e94560 accent)
    ├── Pipeline visuel 14 agents
    ├── Cartes détaillées 14 agents
    ├── 12 interconnexions écosystème AgenticX5
    └── CTA contact
```

## Design System

```css
--bg: #050608        /* fond principal */
--card: rgba(15,17,22,0.85)
--accent: #e94560    /* rouge PSM — danger/process safety */
--cyan: #06b6d4      /* HAZOP/PHA */
--amber: #f59e0b     /* MOC/PSSR */
--purple: #a855f7    /* SIS/SIL */
--emerald: #10b981   /* Audit/Conformité */
--rose: #f43f5e      /* Urgence/Alarmes */
--font: 'Outfit'
--mono: 'JetBrains Mono'
```

Thème DARK uniquement. Bilingue FR/EN via `data-fr` / `data-en` et variable `LN`.

## Les 14 Agents PSM-X5

| Agent | Élément PSM | Fonction | Interconnexions |
|-------|-------------|----------|----------------|
| A1-Participation | #1 Employee Participation | NLP sondages, feedback, gamification | BehaviorX, LiteraCIA |
| A2-PSI-RAG | #2 Process Safety Information | RAG 1536 dims sur P&ID, MSDS, specs | Pinecone, SafetyGraph |
| A3-PHA-Engine | #3 Process Hazard Analysis | HAZOP/LOPA IA, Bow-Tie auto <5min | SafetyGraph (22M+) |
| A4-OpsProc | #4 Operating Procedures | Génération/MAJ SOPs IA, obsolescence | A10-MOC cascade |
| A5-Training | #5 Training | Parcours adaptatifs, VR, certification | LiteraCIA, SafeVision |
| A6-Contractor | #6 Contractors | Onboarding digital, qualifications HHC | A5-Training |
| A7-PSSR | #7 Pre-Startup Safety Review | Checklists dynamiques, multi-approbateurs | A10-MOC |
| A8-MechInt | #8 Mechanical Integrity | IoT prédictif, SIS/SIF/SIL, RAGAGEP | SENTINEL·X5, IEC 61511 |
| A9-HotWork | #9 Hot Work Permits | Permis géolocalisés, détection ATEX | SafeScan360 |
| A10-MOC | #10 Management of Change | Workflow complet, impact auto, cascade PSI | A2, A3, A4, A5, A7, A8 |
| A11-RCA | #11 Incident Investigation | RCA IA, 5-Why, Bow-Tie post-incident | SafetyGraph Neo4j |
| A12-Emergency | #12 Emergency Planning | Plans dynamiques, simulation what-if | SafeTwinX5 |
| A13-Audit | #13 Compliance Audits | Pack évidence 14E <2h, gap analysis | PROV-O, Standards-Gouv. |
| A14-InfoSec | #14 Trade Secrets | Classification docs, RBAC, traçabilité | A2-PSI-RAG |

## Skills Base de Connaissances (10 skills PSM)

```
.skills/
├── psm-hazop-lopa-analysis/SKILL.md        — 7.5KB — Guide words, LOPA, PFD/IEF, Bow-Tie
├── psm-sis-sif-sil-verification/SKILL.md   — 5.2KB — IEC 61511, lifecycle SIS, PFDavg
├── psm-moc-pssr-workflow/SKILL.md          — 5.4KB — Workflow 8 étapes, PSSR checklist
├── psm-mechanical-integrity-ragagep/SKILL.md — 4.1KB — API 510/570/653, ASME, RBI
├── psm-incident-investigation-rca/SKILL.md — 3.8KB — 5-Why, API 754 Tier 1-4
├── psm-emergency-response-planning/SKILL.md — 3.4KB — EAP, dispersion, drills
├── psm-process-safety-information/SKILL.md — 2.7KB — PSI chimie/techno/équipement
├── psm-osha-29cfr1910119-compliance/SKILL.md — 3.3KB — 14 éléments, pénalités, PSM-NEP
├── psm-epa-rmp-seveso-comah/SKILL.md       — 3.3KB — EPA RMP, Seveso III, COMAH
└── psm-atex-hazardous-areas/SKILL.md       — 4.1KB — Zone 0/1/2, NEC, Ex equipment
```

Total : 979 lignes de connaissances métier process safety structurées.

## Standards de Référence

| Standard | Portée | Agent(s) |
|----------|--------|----------|
| OSHA 29 CFR 1910.119 | PSM 14 éléments, USA | Tous |
| EPA 40 CFR Part 68 | Risk Management Program | A12, A13 |
| IEC 61511 / ISA-84 | SIS/SIF/SIL lifecycle | A8-MechInt |
| IEC 61882 | HAZOP methodology | A3-PHA-Engine |
| API 754 | Process Safety KPIs Tier 1-4 | A11-RCA, A13-Audit |
| API 510/570/653 | Inspection pressure vessels/piping/tanks | A8-MechInt |
| API 520/521 | Relief systems sizing/design | A8-MechInt |
| ASME BPVC / B31.3 | Pressure vessel code / process piping | A8-MechInt |
| NFPA 30/70E/652 | Flammables, electrical, combustible dust | A9-HotWork |
| IEC 60079 series | ATEX/IECEx hazardous areas | A9-HotWork |
| EU 2012/18/EU | Seveso III directive | A13-Audit |
| CCPS/AIChE | LOPA guidelines, RBPS | A3-PHA-Engine |
| ISO 45001 | Management SST | Standards-Gouvernance |
| RGPD / Loi 25 QC | Vie privée | A14-InfoSec |
| EU AI Act / NIST AI RMF | Gouvernance IA | Standards-Gouvernance |

## Données Intégrées (hardcodées dans index.html)

| Donnée | Variable | Taille |
|--------|----------|--------|
| 14 Éléments PSM | `PSM_ELEMENTS[]` | 14 objets (nom, agent, desc, icône, couleur) |
| 3 Noeuds HAZOP | `HAZOP_NODES[]` | Réacteur, Colonne, Stockage — déviations détaillées |
| 8 Étapes MOC | `MOC_STEPS[]` | Timeline simulation avec agents et tags |
| 6 SIF | `SIF_DATA[]` | PFD, target SIL, trend, status |
| 14 Scores audit | `auditScores[]` | Scoring conformité par élément |
| 12 Liens écosystème | `ECO_LINKS[]` | Plateformes AgenticX5 interconnectées |

## Claude API — Conventions (prévu v2.0)

Modèle : `claude-sonnet-4-20250514`
Max tokens : 1500
Langue : toujours français dans system prompt

### System prompts (3 contextes prévus) :
1. **HAZOP assisté** : expert process safety, guide words IEC 61882, génération déviations à partir de P&ID
2. **Pack évidence audit** : expert conformité PSM, génération rapport 14 éléments avec scoring et recommandations
3. **Investigation incident** : expert RCA, 5-Why structuré, Bow-Tie post-incident, corrélation causale

## Règles Non Négociables

1. **Primauté de la vie** — aucun compromis sécurité dans les recommandations IA
2. **Human-in-the-Loop** — HAZOP, LOPA, MOC critiques : validation humaine obligatoire
3. **Honnêteté des claims** — les métriques d'impact sont des *projections modélisées*, PAS des faits documentés
4. **Single-file** — ne JAMAIS séparer en fichiers multiples sans accord explicite
5. **Bilingue** — tout nouveau contenu doit avoir `data-fr` et `data-en`
6. **Agnostique** — AUCUNE référence client spécifique (Ma'aden, etc.) dans le code
7. **RAGAGEP documenté** — toujours citer le standard de référence pour chaque recommandation technique

## Roadmap Technique

| Version | Statut | Feature clé |
|---------|--------|-------------|
| v1.0 | ✅ Livré | Dashboard 5D interactif, 14 agents, HAZOP/Bow-Tie/MOC/SIS/Audit |
| v2.0 | ⏳ Planifié | Claude API intégré (HAZOP IA + Pack audit + RCA) |
| v3.0 | ⏳ | Neo4j Aura connecté (SafetyGraph 22M+ incidents) |
| v4.0 | ⏳ | IoT SCADA real-time (MQTT/OPC-UA → SIS monitoring live) |
| v5.0 | ⏳ | Orchestration LangGraph 14 agents production |

## Secteurs Cibles (agnostique)

Mines & Métallurgie · Pétrochimie & Raffinage · Énergie · Manufacturing · Traitement des Eaux · Agroalimentaire · Transport & Logistique · Construction

## Écosystème AgenticX5

PSM-X5 est la plateforme #26, interconnectée avec : EDGY-AgenticX5 (orchestrateur), SafetyGraph (Neo4j 22M+), SENTINEL·X5 (alarm intelligence), SafeScan360 (computer vision), SafeTwinX5 (digital twins), DensityGuard (mining process), BehaviorX (analyse comportementale), HolisticErgo (ergonomie), LiteraCIA (formation), SafeVision SST (vidéos IA), Hovermap Safety (LiDAR drones), Standards-Gouvernance (règles opérationnelles).

## Commandes Git

```bash
# Depuis C:\Users\Mario\Documents\Netifly\PSM-X5\
git add .
git commit -m "description"
git push
# → Netlify auto-deploy en ~15s
```

## MCP Servers Disponibles

- Google Calendar → suivi actions MOC/PSSR
- Gmail → envoi rapports audit IA
- Hugging Face → modèles ML (embeddings PSI)
- Netlify → déploiement automatisé
- Canva → visuels marketing PSM
- Invideo → vidéos formation process safety

---
*Ce fichier est la mémoire structurée du projet. Il doit être mis à jour à chaque changement d'architecture significatif.*
