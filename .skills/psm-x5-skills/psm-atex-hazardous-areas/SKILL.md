---
name: psm-atex-hazardous-areas
description: >
  Classification zones ATEX/IECEx (Zone 0/1/2, Zone 20/21/22), NEC Class/Division,
  sélection équipements Ex (Ex d, Ex e, Ex i, Ex p), hot work permits zones classées,
  détection gaz, IEC 60079 series. Utiliser dès que l'utilisateur mentionne ATEX, zones
  explosives, IECEx, Zone 0/1/2, NEC Division, Ex equipment, explosive atmospheres,
  classification zones dangereuses, ou hot work zone classée.
---

# ATEX & Hazardous Areas — Skill Process Safety

## 1. Systèmes de classification

### 1.1 Système Zone (IEC/ATEX/IECEx) — International
**Gaz/Vapeurs** :
- **Zone 0** : atmosphère explosive présente continuellement ou longues périodes (>1000h/an)
- **Zone 1** : atmosphère explosive probable en opération normale (10-1000h/an)
- **Zone 2** : atmosphère explosive improbable en normal, brève si elle survient (<10h/an)

**Poussières combustibles** :
- **Zone 20** : nuage explosif continu (intérieur silos, collecteurs)
- **Zone 21** : nuage explosif probable en normal (stations ensachage, filtres)
- **Zone 22** : nuage explosif improbable en normal (emballage, entrepôts)

### 1.2 Système Class/Division (NEC — Amérique du Nord)
- **Class I** : gaz/vapeurs inflammables
  - Division 1 ≈ Zone 0 + Zone 1
  - Division 2 ≈ Zone 2
- **Class II** : poussières combustibles
  - Division 1 ≈ Zone 20 + Zone 21
  - Division 2 ≈ Zone 22
- **Class III** : fibres/résidus volatils

### 1.3 Groupes de gaz
| Groupe IEC | Gaz représentatifs | NEC Group |
|-----------|-------------------|-----------|
| IIA | Propane, méthane, acétone | D |
| IIB | Éthylène, éthanol, H₂S | C |
| IIC | Hydrogène, acétylène | B (+ A pour acétylène) |

## 2. Standards clés

| Standard | Portée |
|----------|--------|
| ATEX 2014/34/EU | Directive équipements zones explosives (EU) |
| ATEX 1999/92/EC | Directive protection travailleurs (EU) |
| IEC 60079-10-1 | Classification zones gaz |
| IEC 60079-10-2 | Classification zones poussières |
| IEC 60079-0 | Exigences générales Ex equipment |
| IEC 60079-1 (Ex d) | Enveloppes antidéflagrantes |
| IEC 60079-7 (Ex e) | Sécurité augmentée |
| IEC 60079-11 (Ex i) | Sécurité intrinsèque |
| IEC 60079-2 (Ex p) | Surpression interne |
| NEC Article 500-506 | Hazardous locations (USA) |
| CSA C22.1 Section 18 | Canadian Electrical Code zones |

## 3. Protection types equipment

| Type | Code | Principe | Zone applicable |
|------|------|----------|----------------|
| Antidéflagrant | Ex d | Contenir explosion, refroidir flamme | Zone 1, 2 |
| Sécurité augmentée | Ex e | Prévenir arcs/étincelles/surfaces chaudes | Zone 1, 2 |
| Sécurité intrinsèque | Ex i (ia/ib/ic) | Limiter énergie électrique | Zone 0 (ia), 1 (ib), 2 (ic) |
| Surpression | Ex p | Maintenir gaz inerte dans enclosure | Zone 1, 2 |
| Encapsulage | Ex m | Noyer composants dans résine | Zone 1, 2 |
| Remplissage sable | Ex q | Noyer dans quartz | Zone 1, 2 |
| Non-sparking | Ex nA | Pas d'arcs en normal | Zone 2 seulement |
| Dust-tight | Ex t | Enveloppe étanche poussières | Zone 21, 22 |

## 4. Hot Work en zones classées

### 4.1 Agent A9-HotWork de PSM-X5
- Permis digitaux géolocalisés avec mapping zones ATEX
- Vérification automatique : zone classée → protocole renforcé obligatoire
- Monitoring atmosphère en continu (LEL, O₂) pendant travaux
- Expiration automatique du permis
- Fire watch post-travaux documenté

### 4.2 Protocole zones classées
1. Confirmation zone dégazée et testée (<10% LEL)
2. Monitoring continu O₂ et LEL pendant travaux
3. Équipements de soudage conformes (mise à terre, extincteur)
4. Fire watch pendant + 30-60 min après travaux
5. Autorisation spécifique du responsable zone

## 5. Intégration PSM-X5
- **A9-HotWork** : permis digitaux, détection ATEX auto
- **SafeScan360** : surveillance vidéo zones classées
- **Hovermap Safety** : inspection LiDAR zones ATEX confinées
- **SENTINEL·X5** : monitoring multi-capteurs gaz en continu
- **DensityGuard** : atmosphères toxiques mines (O₂, H₂S, CO, CH₄)
