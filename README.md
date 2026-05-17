SC Shellfish Aquaculture Governance Network
Kate Chatman | MPA/EVSS | College of Charleston / SC Sea Grant Consortium
May 2026
About This Network
This interactive visualization maps the governance network for shellfish aquaculture in South Carolina. It is a component of an MPA/EVSS dual-degree thesis examining why South Carolina — a state with significant biophysical capacity for shellfish mariculture — has substantially less acreage in active production than its ecological potential would support.

The analysis applies two complementary theoretical frameworks:

Advocacy Coalition Framework (ACF) — to identify actor coalitions organized around shared policy beliefs about mariculture expansion
Herd & Moynihan’s administrative burden framework — to identify which governance relationships generate learning, compliance, and psychological costs for shellfish operators
Node size reflects betweenness centrality — actors who sit between otherwise disconnected parts of the network and therefore hold disproportionate influence over information and resource flows. Red-orange edges indicate burden-generating relationships. Use the dropdown menus to filter by actor type or search for a specific node.

Full Governance Network
🌐 Interactive Network — opens in new tab

The full governance network (49 connected nodes, 158 edges) is hosted interactively at the link below. Use the dropdown to filter by actor type, search for a specific node, or hover for centrality details.

This subgraph isolates the 109 burden-generating edges in the network — relationships where one actor’s regulatory authority, compliance requirement, or administrative process imposes learning, compliance, or psychological costs on the receiving actor (Herd & Moynihan, 2019).

Centrality Results
Top Brokers — Betweenness Centrality
Betweenness centrality identifies actors whose network position mediates flows between otherwise disconnected actors. High betweenness nodes are structural brokers — their removal would disconnect parts of the governance system.

Actor	Actor Type	Coalition	Betweenness	Degree (All)	Degree (In)	Degree (Out)
South Carolina Shellfish Growers Association (SCSGA)	advocacy	pro-expansion	0.1325	20	17	3
SCDNR Shellfish Management Section	regulatory	regulatory-cautious	0.1221	42	11	31
Emily Osborne	science-extension	neutral	0.1186	26	22	4
SCDES Shellfish Sanitation Section	regulatory	regulatory-cautious	0.0913	34	3	31
Andrew Richard	regulatory	regulatory-cautious	0.0513	4	2	2
Caitlyn Mayer	industry	pro-expansion	0.0153	8	5	3
College of Charleston (institutional)	science-extension	neutral	0.0134	6	5	1
USC Geography Department	science-extension	neutral	0.0063	2	1	1
Matt Gorstein	science-extension	neutral	0.0061	5	2	3
Minorities in Aquaculture (MIA)	advocacy	pro-expansion	0.0048	2	1	1
Clemson University (institutional)	science-extension	neutral	0.0048	5	4	1
University of South Carolina (institutional)	science-extension	neutral	0.0046	3	2	1
Mike Marshall	regulatory	regulatory-cautious	0.0039	2	1	1
William Green	industry	pro-expansion	0.0032	5	4	1
East Coast Shellfish Growers Association (ECSGA)	advocacy	pro-expansion	0.0018	2	1	1
Thomas (Tom) Bierce	industry	pro-expansion	0.0015	6	5	1
Andrew Speaker	industry	pro-expansion	0.0008	6	4	2
Julie Davis	industry	pro-expansion	0.0004	5	4	1
Trey McMillan	industry	pro-expansion	0.0004	5	4	1
Jeff Massey	industry	pro-expansion	0.0004	6	4	2
Most Connected Nodes — Degree Centrality
Actor	Actor Type	Coalition	Degree (All)	Degree (In)	Degree (Out)	Betweenness
SCDNR Shellfish Management Section	regulatory	regulatory-cautious	42	11	31	0.1221
SCDES Shellfish Sanitation Section	regulatory	regulatory-cautious	34	3	31	0.0913
Emily Osborne	science-extension	neutral	26	22	4	0.1186
U.S. Army Corps of Engineers Charleston Regulatory Office	regulatory	regulatory-cautious	25	0	25	0.0000
SCDES Bureau of Coastal Management (OCRM)	regulatory	regulatory-cautious	25	0	25	0.0000
South Carolina Shellfish Growers Association (SCSGA)	advocacy	pro-expansion	20	17	3	0.1325
Caitlyn Mayer	industry	pro-expansion	8	5	3	0.0153
College of Charleston (institutional)	science-extension	neutral	6	5	1	0.0134
Thomas (Tom) Bierce	industry	pro-expansion	6	5	1	0.0015
Andrew Speaker	industry	pro-expansion	6	4	2	0.0008
Jeff Massey	industry	pro-expansion	6	4	2	0.0004
Larry Toomer	industry	pro-expansion	6	4	2	0.0004
Matt Gorstein	science-extension	neutral	5	2	3	0.0061
Clemson University (institutional)	science-extension	neutral	5	4	1	0.0048
William Green	industry	pro-expansion	5	4	1	0.0032
Julie Davis	industry	pro-expansion	5	4	1	0.0004
Trey McMillan	industry	pro-expansion	5	4	1	0.0004
Bob Baldwin	industry	pro-expansion	5	4	1	0.0004
Jeff Spahr	industry	pro-expansion	5	4	1	0.0000
Carrie Spahr	industry	pro-expansion	5	5	0	0.0000
Coalition Structure
Coalition	Actor Type	N	Mean Betweenness	Mean Degree
conservation	advocacy	5	0.0000	0.8
neutral	science-extension	22	0.0070	3.2
neutral	industry	2	0.0000	5.0
neutral	regulatory	1	0.0000	1.0
pro-expansion	advocacy	9	0.0155	3.3
pro-expansion	industry	29	0.0008	4.4
regulatory-cautious	regulatory	26	0.0103	5.5
Network Summary Statistics
Metric	Value
Active nodes	94.0000
Edges	193.0000
Network density	0.0221
Average path length	2.5600
Diameter	5.0000
Clustering coefficient (global)	0.1488
Burden-generating edges	109.0000
Non-burden edges	84.0000
Regulatory authority edges	112.0000
Collaboration edges	38.0000
Information edges	42.0000
Methods Note
This network was constructed using a hybrid observed-plus-survey methodology. Edges were coded from documented relationships using a three-tier evidence hierarchy: Tier 1 (formal authority, statutory mandate, signed agreement), Tier 2 (co-membership, documented joint project, survey self-report), and Tier 3 (documented co-attendance, role-overlap inference). Conflict edges require behavioral evidence from the documentary record per codebook Rule 8. Historical nodes (actors no longer active but instrumental in establishing current regulatory structures, including Peter Kingsley-Smith, departed May 2026) are retained in the node roster but excluded from centrality calculations.

Coalition encoding follows the Advocacy Coalition Framework (Sabatier & Jenkins-Smith, 1993): pro-expansion, regulatory-cautious, conservation, and neutral. Administrative burden coding follows Herd & Moynihan (2019): learning, compliance, and psychological burden types assigned by role relationship rather than self-report.

All analysis conducted in R using igraph (Csárdi & Nepusz, 2006) and visNetwork (Almende B.V., 2022). Data current as of May 2026.

Chatman, K. (2026). SC Shellfish Aquaculture Governance Network. MPA/EVSS Thesis, College of Charleston / SC Sea Grant Consortium. Beta visualization: rpubs.com/chatmanka

