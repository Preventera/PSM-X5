# CLAUDE.md — PSM-X5 Process Safety Management

> Mémoire de projet structurée pour Claude Code et Claude.ai
> Dernière mise à jour : 11 Mars 2026 — v1.0
> Déployé et opérationnel sur GitHub + Netlify

## Identité du Projet

**PSM-X5** (Process Safety Management X5) est la 26e plateforme de l'écosystème AgenticX5. Elle automatise la gestion de la sécurité des procédés industriels via 14 agents IA couvrant les 14 éléments du standard OSHA PSM (29 CFR 1910.119). Plateforme agnostique — applicable mines, pétrochimie, raffinage, énergie, manufacturing, agroalimentaire, traitement des eaux, transport.

**Organisation** : Preventera Inc. / AgenticX5
**Repo GitHub** : https://github.com/Preventera/PSM-X5
**Production** : Netlify (auto-deploy depuis GitHub)
**Contact** : team@agenticx5.com | genaisafety.online
**VP AI / CTO** : Mario Deshaies
**Local** : C:\Users\Mario\Documents\2025\Projets de développement Agentique\psm-x5

## Qu'est-ce que le PSM ?

Le Process Safety Management est un cadre réglementaire OSHA (1992) créé après Bhopal (1984) pour prévenir les relâchements catastrophiques de substances hautement dangereuses (HHC) — explosions, incendies, nuages toxiques. Il s'applique aux 137 substances listées + tout liquide/gaz inflammable ≥ 10,000 lbs. Standard "performance-based" à 14 éléments interconnectés protégeant contre les événements catastrophiques à basse fréquence / haute conséquence. PSM-X5 transforme ces 14 éléments d'obligations papier réactives en un système agentique proactif et prédictif.

## Architecture — Contrainte Fondamentale

**SINGLE-FILE HTML.** Le Hub PSM-X5 vit dans `index.html` (~77 KB). Pas de build step, pas de bundler, pas de framework. HTML5 + CSS3 + JavaScript ES6+ inline. Déploiement Netlify CDN statique.

### Pourquoi single-file :
- Portabilité totale (email, USB, offline)
- Zéro dépendance serveur
- Demo instantanée (ouvrir dans un navigateur)
- Déploiement Netlify en 15 secondes via git push

### Librairies externes (CDN uniquement) :
- Chart.js v4.4.1 — Charts (radar 14 éléments, line SIL trends)
- Google Fonts — Outfit + JetBrains Mono

## Structure des Fichiers Déployés

```
PSM-X5/                                        # Repo Preventera/PSM-X5
├── index.html                                  # 77KB — Dashboard 5D + Claude API
├── CLAUDE.md                                   # Ce fichier
├── docs/
│   └── PSM-X5_Descriptif_Projet_v1.docx        # 26KB — Descriptif Word
└── .skills/psm-x5-skills/                      # 10 skills PSM
    ├── psm-hazop-lopa-analysis/SKILL.md         # 7.5KB
    ├── psm-sis-sif-sil-verification/SKILL.md    # 5.2KB
    ├── psm-moc-pssr-workflow/SKILL.md            # 5.4KB
    ├── psm-mechanical-integrity-ragagep/SKILL.md # 4.1KB
    ├── psm-incident-investigation-rca/SKILL.md   # 3.8KB
    ├── psm-emergency-response-planning/SKILL.md  # 3.4KB
    ├── psm-process-safety-information/SKILL.md   # 2.7KB
    ├── psm-osha-29cfr1910119-compliance/SKILL.md # 3.3KB
    ├── psm-epa-rmp-seveso-comah/SKILL.md         # 3.3KB
    └── psm-atex-hazardous-areas/SKILL.md         # 4.1KB
```

## Structure des 5 Dimensions (index.html)

```
Hub Landing ─── 14 cartes PSM elements, stats KPI animés
│
├── D1 — HAZOP/PHA Engine (cyan #06b6d4)
│   ├── 3 noeuds HAZOP interactifs (Réacteur, Colonne, Stockage HHC)
│   ├── Table déviations (guide words, causes, conséquences, RPL)
│   ├── Bow-Tie SVG (menaces → barrières → conséquences)
│   └── ★ HAZOP IA assisté (Claude API — A3-PHA-Engine)
│
├── D2 — MOC & PSSR (amber #f59e0b)
│   ├── Simulation MOC live 8 étapes (play button)
│   ├── Pipeline agents animé (A10→A2→A3→A4→A5→A8→A7→A13)
│   └── Checklist PSSR dynamique (synchro simulation)
│
├── D3 — SIS/SIL Monitoring (purple #a855f7)
│   ├── 6 SIF cards gauges PFD (ok/warn/alert)
│   └── Chart tendance 90 jours IEC 61511
│
├── D4 — Audit 14 Éléments (emerald #10b981)
│   ├── Radar Chart.js 14 axes + grille scoring
│   ├── Bouton "Simuler audit"
│   └── ★ Pack Évidence IA (Claude API — A13-Audit)
│
└── D5 — Agents & Écosystème (accent #e94560)
    ├── Pipeline 14 agents + 14 cartes détail
    ├── 12 interconnexions AgenticX5
    └── ★ Investigation Incident IA (Claude API — A11-RCA)
```

## Design System

```css
--bg: #050608    --accent: #e94560 (rouge PSM)    --cyan: #06b6d4 (D1)
--amber: #f59e0b (D2)    --purple: #a855f7 (D3)    --emerald: #10b981 (D4)
--rose: #f43f5e    --orange: #f97316    --blue: #3b82f6
--font: 'Outfit'    --mono: 'JetBrains Mono'
```

Thème DARK uniquement. Bilingue FR/EN via `data-fr`/`data-en` + variable `LN`.

## Les 14 Agents PSM-X5

| # | Agent | Élément OSHA PSM | Fonction |
|---|-------|-----------------|----------|
| 1 | A1-Participation | Employee Participation | NLP sondages, feedback, gamification |
| 2 | A2-PSI-RAG | Process Safety Information | RAG 1536 dims, P&ID, MSDS, recherche sémantique |
| 3 | A3-PHA-Engine | Process Hazard Analysis | HAZOP/LOPA IA, Bow-Tie auto <5min |
| 4 | A4-OpsProc | Operating Procedures | Génération/MAJ SOPs IA, obsolescence |
| 5 | A5-Training | Training | Parcours LiteraCIA, VR, certification, refresher 3 ans |
| 6 | A6-Contractor | Contractors | Onboarding digital, qualifications HHC |
| 7 | A7-PSSR | Pre-Startup Safety Review | Checklists dynamiques, multi-approbateurs |
| 8 | A8-MechInt | Mechanical Integrity | IoT prédictif, SIS/SIF/SIL, RAGAGEP |
| 9 | A9-HotWork | Hot Work Permits | Permis géolocalisés, détection ATEX |
| 10 | A10-MOC | Management of Change | Workflow complet, impact auto, cascade PSI |
| 11 | A11-RCA | Incident Investigation | RCA IA, 5-Why, Bow-Tie post-incident |
| 12 | A12-Emergency | Emergency Planning | Plans dynamiques, simulation relâchement |
| 13 | A13-Audit | Compliance Audits | Pack évidence <2h, scoring continu PROV-O |
| 14 | A14-InfoSec | Trade Secrets | Classification, RBAC, traçabilité PSI |

## 10 Skills — Base de Connaissances Métier (979 lignes, 42.7KB)

| Skill | Contenu clé |
|-------|-------------|
| `psm-hazop-lopa-analysis` | Guide words IEC 61882, formule TMEF, PFD/IEF typiques, critères IPL CCPS, tables SIL |
| `psm-sis-sif-sil-verification` | Lifecycle IEC 61511, 3 critères SIL, calcul PFDavg, proof testing, FSA 5 stages |
| `psm-moc-pssr-workflow` | Workflow 8 étapes MOC, PSSR checklist, MOC temporaire/permanent, causes échec |
| `psm-mechanical-integrity-ragagep` | API 510/570/653, ASME BPVC/B31.3, RBI 580/581, relief device management |
| `psm-incident-investigation-rca` | 5-Why, Bow-Tie post-incident, API 754 Tier 1-4, actions SMART |
| `psm-emergency-response-planning` | EAP, dispersion ALOHA/PHAST, 3 niveaux réponse, HAZWOPER |
| `psm-process-safety-information` | PSI chimie/techno/équipement, RAG indexation, cascade MOC |
| `psm-osha-29cfr1910119-compliance` | 14 éléments CFR, pénalités 2025, PSM-NEP, replacement-in-kind |
| `psm-epa-rmp-seveso-comah` | EPA RMP 2024, Seveso III, COMAH UK, 8 juridictions |
| `psm-atex-hazardous-areas` | Zone 0/1/2, NEC Class/Division, groupes gaz, 8 types protection Ex |

## Claude API — 3 Fonctions IA

Modèle : `claude-sonnet-4-20250514` | Max tokens : 2000

| Fonction | Dimension | Agent | System prompt | Input |
|----------|-----------|-------|---------------|-------|
| `generateAIHazop()` | D1 | A3-PHA-Engine | `PSM_SYSTEM_HAZOP` | Description procédé |
| `generateAIAudit()` | D4 | A13-Audit | `PSM_SYSTEM_AUDIT` | Description installation |
| `generateAIRCA()` | D5 | A11-RCA | `PSM_SYSTEM_RCA` | Description incident |

Toutes passent par `callClaudeAPI()` → POST api.anthropic.com → `formatAIResponse()` (MD→HTML).

## JavaScript — Fonctions Clés

```javascript
go(dim)              // Navigation hub/d1-d5
setLang(l)           // Toggle FR/EN
renderHub()          // 14 cartes + count-up
renderHAZOP()        // Table déviations par noeud
renderBowTie()       // SVG Bow-Tie automatisé
startMOC()           // Simulation live 8 étapes
renderPSSR()         // Checklist synchro MOC
renderSIS()          // 6 SIF cards + gauges
renderSILChart()     // Chart.js tendance PFD
renderAudit()        // Grille + radar 14 axes
randomizeAudit()     // Démo re-randomize
renderAgents()       // Pipeline + cartes + écosystème
callClaudeAPI()      // Appel API générique
formatAIResponse()   // MD → HTML
```

## Standards Couverts (40+)

OSHA PSM 29 CFR 1910.119 · EPA RMP 40 CFR 68 · IEC 61511/ISA-84 (SIS) · IEC 61882 (HAZOP) · API 754 (KPIs) · API 510/570/653 (inspection) · API 520/521 (relief) · API 579-1 (FFS) · API 580/581 (RBI) · ASME BPVC · ASME B31.3 · NFPA 30/70E/652 · IEC 60079 (ATEX) · EU 2014/34/EU · Seveso III · COMAH UK · CCPS/AIChE · ISO 45001/31000 · RGPD/Loi 25 · EU AI Act · NIST AI RMF

## Interconnexions Écosystème AgenticX5

EDGY-AgenticX5 (orchestrateur) · SafetyGraph (Neo4j 22M+) · SENTINEL·X5 (alarm intelligence) · SafeScan360 (computer vision) · SafeTwinX5 (digital twins) · DensityGuard (mining process) · BehaviorX (comportemental 7D) · HolisticErgo (ergonomie) · LiteraCIA (formation) · SafeVision SST (vidéos IA) · Hovermap Safety (LiDAR drones) · Standards-Gouvernance (règles)

## Règles Non Négociables

1. **Primauté de la vie** — aucun compromis sécurité. En cas de doute → scénario conservateur
2. **Human-in-the-Loop** — HAZOP, LOPA, MOC critiques, PSSR : validation humaine obligatoire
3. **Honnêteté des claims** — métriques = *projections modélisées*, PAS faits documentés
4. **Single-file** — ne JAMAIS séparer index.html sans accord explicite
5. **Bilingue** — tout contenu DOIT avoir `data-fr` et `data-en`
6. **Agnostique** — AUCUNE référence client spécifique dans le code
7. **RAGAGEP documenté** — toujours citer le standard de référence
8. **UTF-8 sans BOM** — `[System.IO.File]::WriteAllText()` pour tous fichiers PowerShell

## Roadmap

| Version | Statut | Feature |
|---------|--------|---------|
| v1.0 | ✅ Déployé | Dashboard 5D, 14 agents, 3 Claude API, 10 skills, GitHub+Netlify |
| v2.0 | ⏳ | Skills injectées comme context Claude API, LOPA calculator, export PDF |
| v3.0 | ⏳ | Neo4j Aura live (SafetyGraph 22M+) |
| v4.0 | ⏳ | IoT SCADA real-time (MQTT/OPC-UA) |
| v5.0 | ⏳ | Orchestration LangGraph 14 agents production |

## Commandes

```bash
# Git push → Netlify auto-deploy ~15s
git add . && git commit -m "description" && git push

# Dev local
npx serve . -p 3000

# Encoding BOM-safe (PowerShell)
[System.IO.File]::WriteAllText("$PWD\file", $content, [System.Text.UTF8Encoding]::new($false))
```

---
*PSM-X5 — Plateforme #26 AgenticX5 — genaisafety.online — team@agenticx5.com*
