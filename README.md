# SC Shellfish Aquaculture Governance Network

**Kate Chatman** · MPA/EVSS Dual-Degree Thesis  
College of Charleston / SC Sea Grant Consortium · 2026  
Live dashboard: [chatmanka.github.io/sc-shellfish-network](https://chatmanka.github.io/sc-shellfish-network/)

---

## Overview

This repository hosts an interactive social network analysis (SNA) of the governance network surrounding shellfish aquaculture (mariculture) in South Carolina. The analysis is a core component of an MPA/EVSS thesis examining why South Carolina — a state with significant biophysical capacity for shellfish mariculture — has substantially less acreage in active production than its ecological potential supports.

The network maps relationships among 104 actors (regulatory agencies, scientists, industry operators, advocacy organizations, and NGOs) across 275 documented edges (423 directed edges after bidirectional expansion), coded from statutory documents, public records, organizational materials, and interview data collected through January 2026.

---

## Key Findings

**Structural broker:** SC Sea Grant Consortium (SCSGC) holds the highest betweenness centrality (0.367), meaning the science-extension node — not any regulatory agency — is the primary cross-sector bridge in SC shellfish governance.

**Administrative burden:** 117 of 275 raw edges are burden-generating per the Herd & Moynihan (2019) framework. The four-agency permitting stack (SCDNR SMS, SCDES SSS, SCDES BCM, USACE) generates the majority of burden-producing relationships, with out/in degree ratios ranging from 2.5 (SCDNR SMS) to 8.3 (USACE).

**Regulatory fragmentation:** Horizontal regulatory density among agencies is only 0.0946, indicating agencies regulate in largely independent silos rather than in coordination — forcing operators to navigate four uncoordinated institutional channels simultaneously.

**Coalition power asymmetry:** The regulatory-cautious coalition (n=26) holds mean hub score 6× higher than the neutral science-extension cluster, despite similar betweenness. The largest coalition (pro-expansion, n=42) has the lowest structural power.

**Conservation is not the binding constraint:** The conservation coalition's mean betweenness (0.0018) and mean degree (2.2) confirm structural peripheral position, providing convergent evidence — alongside Cribbs et al. (2024) — that the binding constraint on SC shellfish expansion is administrative, not ecological or social.

---

## Network Specifications

| Metric | Value |
|--------|-------|
| Active nodes | 104 |
| Raw edges | 275 |
| Directed edges (bidirectional expanded) | 423 |
| Network density | 0.040 |
| Burden-generating edges | 117 |
| Horizontal regulatory density | 0.0946 |
| Max betweenness (SCSGC) | 0.367 |
| Max hub score (SCDNR SMS) | 1.000 |
| Data current as of | June 2026 |

---

## Theoretical Frameworks

**Advocacy Coalition Framework (ACF)** — Sabatier & Jenkins-Smith (1993). Actors are coded into four coalitions based on documented policy beliefs and behavioral evidence: pro-expansion, regulatory-cautious, conservation, neutral. Coalition membership determines node border color in the visualization.

**Herd & Moynihan Administrative Burden Framework** — Herd & Moynihan (2019). Edges are coded `burden_generating = TRUE` where the relationship imposes learning costs (navigating regulatory complexity), compliance costs (documentation, fees, time), or psychological costs (uncertainty, stigma) on shellfish operators.

**Gould-Fernandez Brokerage Analysis** — Gould & Fernandez (1989). Five role types (Coordinator, Gatekeeper, Representative, Itinerant, Liaison) classify how actors mediate flows between groups. Group membership = actor_type. Computed via `sna::brokerage()`.

---

## Repository Files

| File | Description |
|------|-------------|
| `index.html` | Interactive dashboard — main entry point |
| `network_full.html` | Self-contained visNetwork visualization, full 104-node network |
| `burden.html` | Self-contained visNetwork visualization, burden subgraph (40 nodes) |
| `README.md` | This file |

**Data and analysis files** (not in this repo — maintained in thesis working directory):

| File | Description |
|------|-------------|
| `edge_list_FINAL_June2026.csv` | 275 edges with relationship_type, direction, strength, evidence_tier, evidence_note, burden_generating |
| `node_roster_FINAL_June2026.csv` | 104 nodes with actor_type, coalition, governance_level, role, category, node_status |
| `centrality_results.csv` | Betweenness, hub score, in/out degree for all 104 nodes |
| `brokerage_results.csv` | Gould-Fernandez role counts for all 104 nodes |
| `thesis_network_pipeline_June2026.R` | Full R analysis pipeline — loads data, builds graph, runs metrics, renders HTML visualizations |
| `thesis_static_figures.R` | Generates static PNG/PDF figures for thesis submission |

---

## Methodology Notes

### Edge Construction

Edges are coded using a three-tier evidence hierarchy:
- **Tier 1:** Formal authority, statutory mandate, signed interagency agreement
- **Tier 2:** Co-membership, documented joint project, interview self-report
- **Tier 3:** Documented co-attendance, role-overlap inference, indirect documentation

Burden-generating edges were coded from role relationship and statutory context per Herd & Moynihan (2019). Regulatory authority edges are coded `burden_generating = TRUE` by default. The `burden_generating` flag reflects the structural relationship, not operator-reported experience.

### Boundary Specification

Network boundary follows a reputational-snowball approach seeded from SCDNR's shellfish mariculture permitting documentation and expanded through interview referrals and organizational mapping. Absence of an edge reflects absence of documentation, not confirmed absence of a relationship (Laumann, Marsden & Prensky, 1983).

Former actors (node_status = "historical") are retained per a governance path-dependency argument: regulatory structures shaped by departed actors remain operative in the current system. Former nodes are rendered with reduced opacity in visualizations.

**Brokerage roles.** Applying the Gould & Fernandez (1989) typology, SC Sea Grant Consortium
is the only actor scoring high across all five brokerage forms. SCDES Shellfish Sanitation
(74%) and the USACE Charleston office (98%) act almost entirely as Representatives, speaking
outward from the regulatory sector rather than controlling entry to it. SCDNR MRRI is 71%
Coordinator, brokering almost entirely within its own sector.

### SCDNR Internal Structure

SCDNR contains two analytically distinct sub-units relevant to mariculture:
- **Shellfish Management Section (SMS):** Administers culture permits, seed import permits, and harvest area leases. Primary regulatory interface for operators.
- **MRRI / Shellfish Research (MRRI):** Conducts mariculture science, disease surveillance, and extension at Waddell Mariculture Center. Science-to-management bridge node.

Both are coded as separate nodes with an intra-agency collaboration edge between them.

### R Analysis Stack

```r
library(igraph)       # Graph construction, centrality, hub scores
library(sna)          # Gould-Fernandez brokerage analysis
library(visNetwork)   # Interactive HTML visualization
library(readr)        # CSV I/O
library(dplyr)        # Data manipulation
library(stringr)      # String cleaning
```

Betweenness centrality: directed, normalized (`igraph::betweenness(g, directed=TRUE, normalized=TRUE)`).  
Hub score: HITS algorithm (`igraph::hits_scores(g)$hub`), measuring outbound structural influence.  
Network density: `igraph::edge_density(g)`.

---

## Citation

**Chatman, K. (2026).** *Unlocking South Carolina Mariculture: An Administrative Burden and Social Network Analysis of Shellfish Aquaculture Governance.* MPA/EVSS Thesis, College of Charleston / SC Sea Grant Consortium.

Interactive visualization: [chatmanka.github.io/sc-shellfish-network](https://chatmanka.github.io/sc-shellfish-network/)

---

## Key References

- Gould, R. V., & Fernandez, R. M. (1989). Structures of mediation: A formal approach to brokerage in transaction networks. *Sociological Methodology, 19*, 89–126.
- Henry, A. D. (2011). Ideology, power, and the structure of policy networks. *Policy Studies Journal, 39*(3), 361–383.
- Herd, P., & Moynihan, D. P. (2019). *Administrative burden: Policymaking by other means.* Russell Sage Foundation.
- Knoke, D., & Yang, S. (2008). *Social network analysis* (2nd ed.). SAGE.
- Laumann, E. O., Marsden, P. V., & Prensky, D. (1983). The boundary specification problem in network analysis. In R. S. Burt & M. J. Minor (Eds.), *Applied network analysis* (pp. 18–34). SAGE.
- Sabatier, P. A., & Jenkins-Smith, H. C. (Eds.). (1993). *Policy change and learning: An advocacy coalition approach.* Westview Press.
- Schneider, M., Scholz, J., Lubell, M., Mindruta, D., & Edwardsen, M. (2003). Building consensual institutions: Networks and the National Estuary Program. *American Journal of Political Science, 47*(1), 143–158.
