# Fractal Adaptive Ontology Generation (FAOG): Research Plan

**Document status:** Phase-1 validated research plan  
**Evidence cutoff:** 2026-08-24  
**Scope:** Research and experimental design only. This document does not authorize a production implementation or a 300 GB ingestion run.

## Executive position

FAOG should not begin from the premise that enterprise knowledge is fractal. Most proposed components already exist as intrinsic-dimension estimation, multiresolution community detection, density cluster trees, hierarchical stochastic block models, information-bottleneck or minimum-description-length model selection, and hyperbolic representation learning. The scientifically defensible first question is narrower:

> Can a local controller using measured semantic complexity, persistent community structure, and information gain make better split, merge, keep, and prune decisions than a tuned hierarchical Leiden system under the same ontology-node and compute budgets?

The initial controller will use intrinsic dimension as its primary complexity measure. A box-counting feature may enter the controller only after it passes the synthetic scaling-evidence gate in Section 15. Failure is informative: if tuned hierarchical Leiden, hierarchical stochastic block models, intrinsic dimension alone, or hyperbolic geometry explain the result equally well, the specifically fractal interpretation will be rejected.

---

## 1. Problem Statement

### 1.1 Enterprise ontology problem

An enterprise corpus is a heterogeneous, permissioned, temporally changing collection of documents, tickets, incidents, messages, source code, policies, tables, logs, and knowledge-base material. At 300 GB or more, a useful ontology must:

1. represent different semantic regions at different depths rather than impose a fixed number of levels;
2. preserve document, chunk, entity, relation, and extraction provenance;
3. support retrieval and knowledge navigation rather than optimize visual tree shape;
4. update affected regions incrementally;
5. operate on partitions rather than a single in-memory dataframe; and
6. inherit source permissions so that inferred nodes, labels, summaries, and graph paths cannot reveal inaccessible evidence.

A shallow representation may be sufficient for a coherent policy domain, while a technically diverse incident domain may require several additional levels. The research problem is to decide, from held-out evidence, whether local measured structure is useful for choosing that resolution.

### 1.2 Proposed object, not an assumed law

Represent the corpus as:

\[
K=(X,G,T)
\]

where \(X\) is an embedding representation of traceable semantic units, \(G\) is a provenance-bearing knowledge graph, and \(T\) is temporal evolution. For candidate region \(C\), record the uncollapsed signature:

\[
\Phi(C)=[
D_{\text{box}},D_{\text{corr}},D_{\text{intrinsic}},
H,\rho,P,Q,S,\Delta I
]
\]

where \(H\) is entropy, \(\rho\) density, \(P\) cross-resolution persistence, \(Q\) modularity or conductance information, \(S\) stability or silhouette information, and \(\Delta I\) information or description-length gain. A later, broader signature may add graph and temporal features:

\[
\Psi(C)=\{D_s,D_i,D_q,H_t,P,S,\Delta I,G_C\}.
\]

These signatures are proposed predictors. They are not evidence that knowledge is fractal, and the components will not initially be collapsed into an arbitrarily weighted score.

Each semantic unit must retain at least `document_id`, `chunk_id`, `source_type`, source location, timestamp when available, owner where permitted, business domain, inherited access-control metadata, embedding model/version, extracted entities and relations, and processing provenance.

### 1.3 Security invariant

An ontology node is a view over supporting evidence, not a new authorization boundary. At query time, node visibility, counts, labels, summaries, representative documents, relations, and graph paths must be recomputed or filtered against the requesting principal's accessible evidence. Deletion or access revocation must propagate from source units to embeddings, indexes, graph edges, cached summaries, evaluation artifacts, and affected ontology ancestors. Aggregate output requires a minimum accessible-support threshold and disclosure review to prevent inference from restricted documents.

### 1.4 Terms that must remain distinct

Hierarchy is nested organization. Self-similarity is similarity under an explicit scale transformation. A power law is a distributional tail model. Scale-free structure usually concerns degree distributions. Fractal dimension concerns scaling of covering mass or counts under a defined metric. Intrinsic dimension estimates local degrees of freedom. Multifractality concerns a spectrum of scaling exponents. Community structure, hierarchical clustering, and persistent topology are separate constructions. None implies another without additional tests.

### 1.5 Established facts, plausible extrapolations, and open hypotheses

- **Established facts:** enterprise corpora are heterogeneous, permissioned, temporally changing, and provenance-sensitive; ontology induction, hierarchical clustering, persistent clustering, GraphRAG-style graph retrieval, intrinsic-dimension estimation, MDL model selection, and hyperbolic hierarchy representations already exist as separate methods.
- **Plausible extrapolations:** some local complexity signals may correlate with where an ontology should split, merge, or stop; chronological and cross-domain holdouts may reveal whether that control policy generalizes better than a single global resolution.
- **Open hypotheses:** the proposed \(\Phi\) and \(\Psi\) signatures, any claim that semantic box-counting carries stable incremental value, any claim of fractal-like scaling in enterprise semantic regions, and the primary claim that a calibrated local controller improves held-out retrieval or cost-quality tradeoffs beyond tuned hierarchical Leiden at matched budgets.

---

## 2. Novelty Assessment

### 2.1 Which parts already exist under different names?

| Proposed FAOG part | Established neighboring idea | Consequence |
|---|---|---|
| Automatic concept and `IS_A` induction | Pattern-, distribution-, and graph-based taxonomy induction | Extraction itself is not novel. |
| Variable hierarchy depth | Nested topic models, density cluster trees, hierarchical Bayesian models, nested stochastic block models | Adaptive depth alone is not novel. |
| Communities over multiple resolutions | Multiresolution modularity, Leiden sweeps, consensus clustering | A gamma sweep is not a contribution. |
| Persistent concepts | Cluster stability, HDBSCAN persistence, topological persistence, bootstrap consensus | Persistence requires a task-linked operational definition. |
| Local semantic complexity | Intrinsic dimension, local intrinsic dimensionality, effective rank, participation ratio | A renamed dimension estimate is not novel. |
| Information-gain stopping | Information bottleneck, MDL, Bayesian model selection | Split/stop by compression already has strong prior art. |
| Graph-derived hierarchy for RAG | GraphRAG and related graph-memory retrieval | The baseline must be implemented strongly. |
| Hierarchical geometry | Poincare, Lorentz, entailment-cone, and hyperbolic KG embeddings | Hyperbolic geometry is a direct alternative explanation. |
| Adaptive compute allocation | Active learning, adaptive sampling, multilevel methods, budgeted inference | Compute allocation must show an empirical Pareto improvement. |

### 2.2 What could still be meaningful?

The credible contribution is a **closed-loop local resolution controller** that jointly uses:

1. a calibrated local complexity estimate;
2. child-community persistence across resolution and bootstrap perturbations; and
3. validation-safe information or description-length gain;

to select `KEEP`, `SPLIT`, `MERGE`, or `PRUNE` under fixed compute and ontology-node budgets. Meaningful novelty would require all of the following:

- the decision rule is local and produces nonuniform depth;
- thresholds transfer to held-out domains rather than being hand-tuned per department;
- the full controller beats tuned hierarchical Leiden, nested-SBM/MDL, and single-signal controllers;
- any box-counting contribution survives representation, metric, scale-window, bootstrap, and surrogate tests; and
- the gain appears in retrieval, stability, or compute efficiency rather than only in an attractive tree.

### 2.3 Novelty risks

The highest risk is that the proposed method is a rebranding of multiresolution clustering plus MDL. A second risk is that intrinsic dimension, not fractal scaling, contains all predictive signal. A third is that hyperbolic embeddings represent the hierarchy more efficiently without a fractal feature. These are explicit rival explanations, not implementation details.

---

## 3. Literature Review

The table records high-value primary sources or official proceedings. "Data" reports the evaluation setting described by the source; it does not imply suitability for enterprise deployment. Where an official proceedings page or publisher URL was available, it is listed directly; otherwise a canonical DOI or arXiv identifier is listed and should be treated as the bibliographic record even if an automated resolver blocks nonbrowser requests.

| Reference | Major finding, data, and methodology | Relationship to FAOG and novelty risk |
|---|---|---|
| Hearst, **"Automatic Acquisition of Hyponyms from Large Text Corpora"** (1992), COLING. [DOI](https://doi.org/10.3115/992133.992154), [ACL](https://aclanthology.org/C92-2082/) | Lexico-syntactic patterns recover hyponym relations from large text corpora; no modern fixed benchmark. | Direct taxonomy edge baseline. Pattern-based induction predates FAOG. **Risk: high.** |
| Snow, Jurafsky, Ng, **"Semantic taxonomy induction from heterogeneous evidence"** (2006), COLING/ACL. [DOI](https://doi.org/10.3115/1220175.1220276) | Combines lexical and distributional evidence; evaluated against WordNet-style taxonomy structure. | Multi-signal taxonomy induction is established. **Risk: high.** |
| Velardi, Faralli, Navigli, **"OntoLearn Reloaded: A Graph-Based Algorithm for Taxonomy Induction"** (2013), Computational Linguistics. [DOI](https://doi.org/10.1162/COLI_a_00146) | Constructs a hypernym graph and derives taxonomy structure; evaluated by building and reconstructing taxonomies. | Graph-based ontology induction is prior art; FAOG must improve branching control. **Risk: high.** |
| Blei, Griffiths, Jordan, **"The nested Chinese restaurant process and Bayesian nonparametric inference of topic hierarchies"** (2010), JACM. [DOI](https://doi.org/10.1145/1667053.1667056) | Nonparametric document paths through topic trees; demonstrated on scientific abstract corpora. | Adaptive topic hierarchy and nonfixed depth are established. **Risk: high.** |
| Teh, Jordan, Beal, Blei, **"Hierarchical Dirichlet Processes"** (2006), JASA. [DOI](https://doi.org/10.1198/016214506000000302) | Nonparametric sharing of mixture components across grouped document collections. | Adaptive model complexity does not require fractality. **Risk: high.** |
| Campello, Moulavi, Sander, **"Density-Based Clustering Based on Hierarchical Density Estimates"** (2013), PAKDD. [DOI](https://doi.org/10.1007/978-3-642-37456-2_14) | Density hierarchy and cluster persistence; evaluated on clustering benchmarks. | Persistent cluster selection is established in density space. **Risk: high.** |
| Lewis et al., **"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"** (2020), NeurIPS/arXiv. [arXiv](https://arxiv.org/abs/2005.11401) | Combines retrieved nonparametric memory with a generator across knowledge-intensive NLP tasks. | Defines the vector/RAG baseline family. **Risk: medium.** |
| Edge et al., **"From Local to Global: A Graph RAG Approach to Query-Focused Summarization"** (2024), arXiv. [Paper](https://arxiv.org/abs/2404.16130), [official docs](https://microsoft.github.io/graphrag/) | Entity graph, Leiden hierarchy, and community summaries for global corpus questions; demonstrated on roughly million-token corpora. | Closest GraphRAG-style comparator. **Risk: high.** |
| Gutiérrez et al., **"HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models"** (2024), arXiv. [arXiv](https://arxiv.org/abs/2405.14831) | Graph memory retrieval evaluated on long-horizon knowledge tasks, with reported cost and latency advantages over iterative retrieval. | Strong graph-retrieval efficiency comparator. **Risk: medium.** |
| Blondel, Guillaume, Lambiotte, Lefebvre, **"Fast unfolding of communities in large networks"** (2008), Journal of Statistical Mechanics. [DOI](https://doi.org/10.1088/1742-5468/2008/10/P10008) | Louvain modularity optimization demonstrated on synthetic and very large phone/web networks. | Establishes scalable hierarchical graph partitioning. **Risk: high.** |
| Reichardt, Bornholdt, **"Statistical mechanics of community detection"** (2006), Physical Review E. [DOI](https://doi.org/10.1103/PhysRevE.74.016110) | Introduces a resolution-parameter formulation for community detection on network benchmarks. | Much of adaptive depth may reduce to resolution selection. **Risk: high.** |
| Traag, Van Dooren, Nesterov, **"Narrow scope for resolution-limit-free community detection"** (2011), Physical Review E. [DOI](https://doi.org/10.1103/PhysRevE.84.016114) | Gives theoretical limits on resolution-limit-free objectives. | Warns against claims of a universal resolution-free controller. **Risk: high.** |
| Traag, Waltman, van Eck, **"From Louvain to Leiden: guaranteeing well-connected communities"** (2019), Scientific Reports. [DOI](https://doi.org/10.1038/s41598-019-41695-z), [arXiv](https://arxiv.org/abs/1810.08473) | Leiden addresses disconnected Louvain communities and improves optimization on real and benchmark networks. | Required graph baseline. **Risk: high.** |
| Peixoto, **"Hierarchical Block Structures and High-Resolution Model Selection in Large Networks"** (2014), Physical Review X. [DOI](https://doi.org/10.1103/PhysRevX.4.011047) | Hierarchical stochastic block modeling with MDL-based model selection on large networks. | Strongest non-fractal split/stop alternative. **Risk: high.** |
| Nickel, Kiela, **"Poincare Embeddings for Learning Hierarchical Representations"** (2017), NeurIPS. [arXiv](https://arxiv.org/abs/1705.08039) | Hyperbolic embeddings represent symbolic and text hierarchies with low distortion. | Direct alternative to Euclidean/fractal explanations. **Risk: high.** |
| Ganea, Becigneul, Hofmann, **"Hyperbolic Entailment Cones for Learning Hierarchical Embeddings"** (2018), ICML. [PMLR](https://proceedings.mlr.press/v80/ganea18a.html) | Hyperbolic cones encode partial orders and hierarchical generalization on graph/hierarchy tasks. | Strong parent-child representation comparator. **Risk: high.** |
| Nickel, Kiela, **"Learning Continuous Hierarchies in the Lorentz Model of Hyperbolic Geometry"** (2018), ICML/arXiv. [arXiv](https://arxiv.org/abs/1806.03417) | Lorentz optimization improves numerical behavior for large taxonomies; evaluated on taxonomy and hierarchy datasets. | Direct rival for efficient variable-depth representation. **Risk: high.** |
| Chami et al., **"Low-Dimensional Hyperbolic Knowledge Graph Embeddings"** (2020), ACL. [DOI](https://doi.org/10.18653/v1/2020.acl-main.617) | Hyperbolic transformations model hierarchical, multi-relational KG benchmarks in low dimension. | Hyperbolic KG baseline can erase the need for fractal features. **Risk: high.** |
| Levina, Bickel, **"Maximum Likelihood Estimation of Intrinsic Dimension"** (2004), NeurIPS. [Proceedings](https://proceedings.neurips.cc/paper/2004/hash/74934548253bcab8490ebd74afed7031-Abstract.html) | kNN-distance MLE evaluated on synthetic and manifold data. | More defensible primary local-complexity feature than box counting. **Risk: high.** |
| Facco et al., **"Estimating the intrinsic dimension of datasets by a minimal neighborhood information"** (2017), Scientific Reports. [DOI](https://doi.org/10.1038/s41598-017-11873-y) | TwoNN estimates intrinsic dimension from first/second-neighbor ratios; evaluated on molecular and image data. | Cheap controller feature and estimator-agreement check. **Risk: high.** |
| Houle, **"Local Intrinsic Dimensionality I: An Extreme-Value-Theoretic Foundation for Similarity Applications"** (2017), SISAP. [DOI](https://doi.org/10.1007/978-3-319-68474-1_5) | Formalizes local neighborhood expansion for similarity applications. | Strong theoretical basis for local retrieval difficulty. **Risk: high.** |
| Grassberger, Procaccia, **"Measuring the Strangeness of Strange Attractors"** (1983), Physica D. [DOI](https://doi.org/10.1016/0167-2789%2883%2990298-1) | Correlation dimension for dynamical-system attractors. | Classic estimator, but transfer to semantic embeddings is speculative. **Risk: medium.** |
| Edelsbrunner, Letscher, Zomorodian, **"Topological Persistence and Simplification"** (2002), Discrete & Computational Geometry. [DOI](https://doi.org/10.1007/s00454-002-2885-2) | Defines persistence as a robust multiscale topological summary on geometric data. | Supports persistence concepts, not semantic ontology validity by itself. **Risk: medium.** |
| Song, Havlin, Makse, **"Self-similarity of complex networks"** (2005), Nature. [DOI](https://doi.org/10.1038/nature03248) | Reports box-covering self-similarity in selected web, actor, and biological networks. | Inspiration for graph diagnostics, not evidence about enterprise semantics. **Risk: medium.** |
| Clauset, Shalizi, Newman, **"Power-Law Distributions in Empirical Data"** (2009), SIAM Review. [DOI](https://doi.org/10.1137/070710111) | MLE, goodness-of-fit, and likelihood-ratio workflow shows many apparent power laws are unsupported; evaluated on 24 datasets. | Required guardrail against visual line fitting. **Risk: high.** |
| Broido, Clauset, **"Scale-free networks are rare"** (2019), Nature Communications. [DOI](https://doi.org/10.1038/s41467-019-08746-5) | Tests about 1,000 empirical networks and finds strong scale-free evidence uncommon. | Heavy tails must not be called scale-free or fractal. **Risk: high.** |
| Piantadosi, **"Zipf's word frequency law in natural language: A critical review and future directions"** (2014), Psychonomic Bulletin & Review. [DOI](https://doi.org/10.3758/s13423-014-0585-6) | Reviews robust Zipfian frequency behavior and unsettled mechanisms across language corpora. | Zipf behavior is not proof of semantic-space fractality. **Risk: low as support; high as a misuse warning.** |
| Kantelhardt et al., **"Multifractal detrended fluctuation analysis of nonstationary time series"** (2002), Physica A. [DOI](https://doi.org/10.1016/S0378-4371%2802%2901383-3) | MFDFA estimates multifractal behavior in ordered nonstationary series. | Relevant only to ordered temporal streams, not unordered document bags. **Risk: low for the MVP.** |
| Tishby, Pereira, Bialek, **"The Information Bottleneck Method"** (1999/2000), Allerton/arXiv. [arXiv](https://arxiv.org/abs/physics/0004057) | Compresses one variable while preserving information about a target; general theoretical framework. | Principled split/merge utility measure. **Risk: high.** |
| Rissanen, **"Modeling by shortest data description"** (1978), Automatica. [DOI](https://doi.org/10.1016/0005-1098%2878%2990005-5) | Introduces minimum-description-length model selection. | Strong stopping and complexity-penalty family. **Risk: high.** |

### Literature conclusion and open review gaps

The literature supports the components but not the central empirical claim. Direct evidence is weak for stable box-counting dimension in modern semantic embedding spaces, semantic multifractality, and TDA-driven ontology control. The language literature supports frequency regularities, not a fractal semantic manifold. Before publication, a second independent bibliographic audit must search forward citations and work after the evidence cutoff; additions require a logged protocol amendment and cannot retroactively change the primary endpoint.

---

## 4. Mathematical Validity

### 4.1 Representation dependence

All geometric measurements are conditional on semantic-unit definition, encoder, preprocessing, normalization, metric, sampling, and time window. Cosine distance on unit-normalized embeddings and Euclidean distance on those same vectors are monotonically related, but whitening or removing dominant components can change neighborhoods. The plan therefore treats a dimension estimate as \(D(C \mid E,m,p,n)\), not an invariant property of concept \(C\).

Measurements occur in the original embedding or a preregistered transformed space. PCA may diagnose anisotropy and effective rank. UMAP is visualization only and will never supply a dimension, density, distance, scaling, or split decision.

### 4.2 Semantic box counting

For cluster \(C\), estimate an approximate covering number \(N_C(\epsilon)\) using a deterministic seeded greedy cover and, at small \(n\), compare it with multiple random orderings and a tighter approximation. Candidate epsilon values are log-spaced within empirically observed nondegenerate neighbor-distance bounds. Candidate scaling windows must:

- contain at least five scales;
- span at least one decade in \(1/\epsilon\) for a fractal-like claim;
- exclude the saturation region where every point is isolated and the coarse region where one ball covers almost everything;
- be selected by a preregistered penalized criterion, not maximum \(R^2\) alone; and
- remain stable under bootstrap resampling, scale-grid perturbation, encoder change, and metric sensitivity.

Fit:

\[
\log N_C(\epsilon)=a+D_{\text{box}}\log(1/\epsilon)+e.
\]

Report slope, bootstrap confidence interval, scaling interval, adjusted \(R^2\), residual diagnostics, number of scales, cover-order uncertainty, and null comparisons. A visually linear plot is insufficient. If no window satisfies the criteria, return "no scaling evidence" rather than a dimension.

### 4.3 Alternative estimators

| Estimator | Defensible use | Main failure modes and required checks |
|---|---|---|
| Correlation dimension | Secondary finite-scale scaling diagnostic | Duplicates, boundary effects, density mixtures; remove degenerate radii, bootstrap, compare local slopes and nulls. |
| Levina-Bickel kNN MLE | Primary intrinsic-dimension estimate | Sensitive to \(k\), curvature, nonuniform density; report a \(k\)-range, bias corrections where justified, and bootstrap CI. |
| TwoNN | Cheap estimator-agreement check | Assumes locally uniform sampling; inspect ratio fit and subsample stability. |
| Local intrinsic dimensionality | Local neighborhood-expansion feature tied to retrieval | High variance in small neighborhoods; enforce support minimum and tail-fit diagnostics. |
| Participation ratio/effective rank | Global or node-level covariance complexity diagnostic | Captures variance spectrum, not manifold dimension; regularize covariance and report sample-size sensitivity. |

"High semantic complexity" will be used only when several diagnostics agree qualitatively. Disagreement is a result and blocks a fractal interpretation.

### 4.4 Persistent multiscale communities

Run the same graph construction through a preregistered resolution grid \(\gamma_1<...<\gamma_k\). Match communities at adjacent scales using, in order:

1. membership overlap and Jaccard similarity;
2. centroid cosine similarity;
3. entity and graph-edge overlap; and
4. maximum-weight bipartite matching when local greedy matches conflict.

Record splits, merges, births, and deaths in a cluster-lineage DAG. Persistence is the fraction of eligible adjacent scale transitions in which a matched concept survives, supplemented by bootstrap stability under document and edge resampling. This is a robust hierarchy signal, but not evidence of fractality.

### 4.5 Information gain and adaptive decisions

The initial unlearned controller keeps components separate. A candidate split \(C\to\{C_j\}\) is eligible only when:

\[
n(C)\ge n_{\min},\quad
D_i(C)>\tau_D,\quad
P(\{C_j\})>\tau_P,\quad
\Delta I(C)>\tau_I,
\]

and its confidence bounds and budget constraint pass. \(\Delta I\) includes entropy reduction,

\[
H(C)-\sum_j p_jH(C_j),
\]

and a preregistered MDL reduction. A high dimension cannot force a split when useful separation or compression is absent.

Candidate siblings \(C_i,C_j\) are eligible to merge when semantic separation is below \(\tau_S\), persistence is below \(\tau_{P,\text{merge}}\), MDL gain from separation is nonpositive, cross-community edge density exceeds \(\tau_E\), and the distinction is unstable under bootstrap. All thresholds are tuned on validation data only.

### 4.6 Multifractal, graph, and temporal claims

- Generalized dimensions \(D_q\) and \(f(\alpha)\) are exploratory and excluded from the MVP. They require valid scaling ranges for several \(q\), stable estimates, and surrogate rejection. A wide \(\Delta\alpha\) alone may be a finite-sample or density-mixture artifact.
- Graph box covering depends strongly on entity resolution, edge definition, pruning, and approximate cover algorithms. It must be compared with configuration-model, degree-preserving, nested-SBM, and hyperbolic-random-graph nulls.
- Hurst exponents and DFA apply only to ordered series such as incident volume or concept density by time. They are invalid on an unordered document set. Any later temporal claim requires timestamp shuffles, matched short-memory processes, seasonality controls, and change-point sensitivity.
- Full Vietoris-Rips persistence is computationally inappropriate at enterprise \(n\). If TDA is explored later, use sparse filtrations, landmarks, local ego-nets, or graph filtrations with explicit approximation error.

### 4.7 Scaling-evidence component report

Do not initially compute a weighted "Fractal Evidence Score." Report:

1. scaling-fit quality and residuals;
2. usable scale span;
3. agreement among box, correlation, and intrinsic-dimension diagnostics;
4. bootstrap and subsample stability;
5. rejection or nonrejection of matched surrogates; and
6. multiscale community persistence.

A region may be called **fractal-like over the observed finite scale range** only when all six pass predefined thresholds. It may never be described as proof that enterprise knowledge is mathematically fractal.

---

## 5. Baseline Selection

Every method receives the same corpus manifest, security filtering, semantic-unit boundaries, train/validation/test split, and (where applicable) encoder and entity extraction. Hyperparameters are tuned with equal validation budget.

| ID | Baseline or experiment | Minimum strong implementation |
|---|---|---|
| A | BM25 | Tuned tokenizer/analyzer and BM25 parameters; metadata filters applied before scoring. |
| B | Vector similarity | Strong fixed encoder, normalized embeddings, exact-search audit sample, tuned ANN recall/latency. |
| C | Vector + flat clustering | Validation-tuned \(k\) or density clustering; cluster-aware retrieval without privileged labels. |
| D | Hierarchical agglomerative | Multiple linkage choices and validation-selected cut criteria; scalable sampling stated. |
| E | Hierarchical Leiden / GraphRAG-style | Provenance-bearing entity/text-unit graph, multiresolution Leiden hierarchy, community summaries, local and global retrieval. |
| E2 | Nested SBM / MDL | Hierarchical block model with description-length model selection; a required non-fractal rival. |
| F | Hyperbolic hierarchy | Poincare or Lorentz representation with parent-child and retrieval tuning. Deferred until after MVP. |
| G | FAOG | Dimension, persistence, and information-gain controller with split and merge. |
| H | Hyperbolic FAOG | Controller plus hyperbolic representation. Deferred until both components independently pass. |

The MVP primary comparison is B vs E vs G, with E2 and the single-signal controller ablations required before a novelty claim. BM25 remains a retrieval sanity check. Hyperbolic and multifractal work must not distract from a failed MVP.

---

## 6. Dataset Strategy

Exactly three public dataset tiers are selected. Sizes below are source-specific and are not interchangeable with decompressed or indexed size.

### 6.1 Small: BEIR CQADupStack Android

- **Official sources:** [BEIR repository](https://github.com/beir-cellar/beir), [ir-datasets CQADupStack Android documentation](https://ir-datasets.com/beir.html#beir/cqadupstack/android).
- **Verified reference slice:** Android contains 22,998 documents, 699 queries, and 1,696 relevance judgments. The benchmark has multiple topical subforums; the exact multi-subforum MVP manifest and post-chunk count will be frozen before fitting.
- **Modalities:** question title, body text, and tags; duplicate-question relevance judgments.
- **License/access:** public benchmark access; underlying Stack Exchange content requires attribution and compliance with current [public terms](https://stackoverflow.com/legal/terms-of-service/public). Redistribution review is mandatory.
- **Splits:** retrieval-ready evaluation slices. The processed benchmark does not provide a strong official temporal design.
- **Preprocessing burden:** low to moderate. The benchmark is already retrieval-oriented, but thread normalization, answer-passage segmentation, duplicate removal by content hash, and subforum manifest freezing are still required.
- **Privacy/security implications:** public data only, but attribution obligations and possible user-handle leakage require conservative redaction and provenance logging. This dataset does not test inherited enterprise ACL behavior.
- **Rationale:** Android is the smallest defensible slice with real retrieval judgments and a plausible path to cross-domain holdouts by subforum.
- **Use:** Android is the pipeline-calibration slice; a preregistered set of subforums supplies 100K-1M units and cross-domain holdouts.
- **Limit:** narrow community-QA language and weak temporal governance; no fractal claim may rest on this dataset alone.

### 6.2 Medium: KILT knowledge source and tasks

- **Official sources:** [KILT repository](https://github.com/facebookresearch/KILT), [KILT paper](https://aclanthology.org/2021.naacl-main.200/).
- **Verified source facts:** 5,903,530 Wikipedia pages and a 34.76 GiB processed knowledge source based on the 2019-08-01 Wikipedia dump.
- **Modalities:** paragraph text, anchors, categories, history information, and Wikidata metadata.
- **Labels:** QA, fact checking, entity linking, and other tasks with evidence provenance and official task splits.
- **License/access:** KILT code is MIT; the knowledge source inherits Wikipedia text reuse obligations (CC BY-SA / GFDL-compatible reuse terms) and Wikidata structured-data terms (CC0 where applicable).
- **Split suitability:** official task splits are strong for held-out evaluation, and the fixed 2019-08-01 snapshot gives a defensible temporal anchor, though it is not a native enterprise chronology benchmark.
- **Preprocessing burden:** moderate. The knowledge source is already structured, but semantic-unit normalization, paragraph-to-node lineage, graph extraction, and evaluation-manifest freezing remain necessary.
- **Privacy/security implications:** public corpus with no enterprise ACL inheritance; still useful for provenance and deletion bookkeeping, but not for validating tenant isolation or restricted-evidence trimming.
- **Rationale:** KILT provides medium-scale heterogeneous text plus provenance-aware evaluation tasks, which is closer to the intended ontology/retrieval setting than a plain text dump.
- **Use:** medium-scale replication, grounding evaluation, and a frozen temporal anchor.
- **Limit:** encyclopedic rather than enterprise-private.

### 6.3 Large: English Wikipedia + Wikidata public corpus bundle, evaluated with TREC CAR/KILT layers

- **Official sources:** [English Wikipedia dumps](https://dumps.wikimedia.org/enwiki/latest/), [Wikidata entity dumps](https://dumps.wikimedia.org/wikidatawiki/entities/), [TREC CAR](https://trec-car.cs.unh.edu/datareleases/), [Wikipedia reuse](https://en.wikipedia.org/wiki/Wikipedia:Reusing_Wikipedia_content), [Wikidata licensing](https://www.wikidata.org/wiki/Wikidata:Licensing).
- **Dataset definition:** treat this as one large public corpus bundle composed of a dated English Wikipedia snapshot plus the contemporaneous Wikidata entity dump, with TREC CAR and KILT used only as official evaluation layers rather than separate corpus substitutions.
- **Observed compressed examples at the evidence cutoff:** English pages/articles multistream XML bzip2 about 26.67 GB; category links about 2.51 GB; external links about 4.94 GB; Wikidata all-entity JSON bzip2 about 102.77 GB; Wikidata truthy N-Triples bzip2 about 43.29 GB. These dynamic "latest" artifacts must be recorded by URL, timestamp, checksum, and byte count in the run manifest.
- **Modalities:** text, categories, hyperlinks, structured triples, and lexemes.
- **License/access:** public download; Wikipedia text reuse requires attribution/share-alike compliance, while Wikidata structured data is CC0.
- **Labels:** raw dumps have no native retrieval qrels; use official TREC CAR and KILT task/provenance layers.
- **Splits:** dated snapshots permit chronological train/test evaluation.
- **Preprocessing burden:** high. XML/JSON dump parsing, semantic segmentation, entity normalization, graph extraction, index construction, and intermediate storage dominate the workload.
- **Privacy/security implications:** public data avoids enterprise privacy restrictions but does not validate inherited ACL trimming; the main governance risks are attribution, license tracking, and provenance correctness rather than confidential-data exposure.
- **Rationale:** this is the most defensible public path to a heterogeneous, graph-rich, temporally snapshot-able corpus whose processed footprint can plausibly exceed 300 GB.
- **Use:** path to 300 GB+ after decompression, semantic segmentation, embeddings, graph indexes, and intermediates.
- **Limit:** substantial preprocessing and external evaluation layers. Scale is not a reason to proceed unless the small and medium gates pass.

---

## 7. Primary Hypothesis

This is the only primary hypothesis.

### 7.1 Preregistered comparison

On the frozen held-out CQADupStack query set, compare:

- **Comparator:** the best validation-tuned hierarchical Leiden pipeline;
- **Treatment:** the local FAOG controller using calibrated intrinsic dimension, cross-resolution/bootstrap persistence, and MDL/information gain. \(D_{\text{box}}\) is included only if it passes the synthetic evidence gate; otherwise the project is explicitly renamed/reframed before the real-data run.

Both use the same semantic units, encoder, graph inputs, ANN backend, label-generation policy, query set, hardware class, and tuning budget. End-to-end compute must be within +/-5%, and ontology-node count within +/-2%.

### 7.2 H0 and H1

For held-out query \(i\):

\[
\Delta_i=NDCG@10_{\text{FAOG},i}-NDCG@10_{\text{Leiden},i}.
\]

- **H0:** \(E[\Delta]\le 0\); local multiscale features do not improve held-out NDCG@10 at matched budgets.
- **H1:** \(E[\Delta]>0\), with a minimum practically important point improvement of **0.02 absolute NDCG@10** at matched budgets.

### 7.3 Analysis and failure rule

The unit of analysis is the query. Report the paired mean difference, standardized paired effect, a 95% stratified bootstrap confidence interval over queries, and a paired randomization test. The primary claim passes only when:

1. the point estimate is at least +0.02;
2. the 95% CI excludes zero in the favorable direction;
3. compute and node budgets pass; and
4. the result is not erased by an exact-search audit or leakage check.

If the CI includes zero, if the effect is below +0.02, if extra compute or nodes are required, or if an LID-only, persistence-only, MDL/nested-SBM, or hyperbolic alternative is within 0.005 NDCG@10, the full FAOG mechanism is not supported.

---

## 8. Secondary Hypotheses

There are exactly three:

1. **Persistence reliability:** At matched NDCG@10 and node count, a persistent multiresolution ontology reduces bootstrap and cross-domain ontology drift by at least 10% relative to a single-resolution ontology.
2. **Compute allocation:** At matched NDCG@10 within 0.005, complexity-aware allocation uses at least 20% fewer node-analysis CPU/GPU hours than uniform allocation.
3. **Emerging knowledge:** On a later chronological dataset, structural change detects preregistered future high-volume topics earlier than the best keyword-frequency, TF-IDF burst, embedding-novelty, and topic-drift baseline, with positive median lead time and a CI excluding zero.

The third hypothesis is not tested on CQADupStack unless reliable timestamps and an event definition are established before model fitting.

---

## 9. Minimum Viable Experiment

### 9.1 Stage 0: synthetic validation

Generate 10K-100K objects per family with at least 20 independent seeds:

| Dataset | Purpose and known distinction |
|---|---|
| A. Isotropic and matched-covariance Gaussian embeddings | Nonfractal null; tests false scaling from finite samples and anisotropy. |
| B. Simple hierarchical Gaussian mixture | Hierarchy without self-similar scaling. |
| C. Known self-similar point set | Cantor-dust or Sierpinski-family positive calibration, embedded by an isometry or documented random projection. |
| D. Multiplicative-cascade point set | Heterogeneous multifractal-like positive calibration; used only to test estimator recovery. |
| E. Preferential-attachment scale-free graph | Heavy-tailed degree without assumed graph fractality. |
| F. Nested stochastic block model | Hierarchical graph with deliberately non-self-similar block sizes and densities. |

Estimator calibration must distinguish hierarchy, heavy-tailed degree, and finite-sample density mixtures from known self-similar scaling. Synthetic retrieval labels derive from generator-held latent concepts and are hidden from clustering.

### 9.2 Real-data scope

Use a frozen subset of CQADupStack subforums yielding 100K-1M traceable semantic units after segmentation. Produce a manifest before fitting with source version, checksums, counts, licenses, excluded records, and exact subforums.

Each question and answer passage is a semantic unit linked to its source thread; duplicate-query qrels remain query labels and never enter embeddings, graph construction, thresholds, node names, or summaries. PII scanning and public-license compliance occur before processing.

### 9.3 Pipeline

1. Normalize and segment by source-aware rules.
2. Write immutable semantic-unit Parquet partitions by source/domain/hash prefix.
3. Generate embeddings with two preregistered open models (one approximately 384-dimensional and one approximately 768-dimensional); record model checksum, tokenizer, pooling, normalization, dtype, and seed.
4. Measure anisotropy, hubness, neighborhood stability, PCA spectrum, local density, and intrinsic dimension in the original representation.
5. Build a mutual or symmetrized kNN semantic graph; tune \(k\) on validation only. Add entity/co-mention edges from one fixed extraction pipeline so GraphRAG and FAOG receive identical graph evidence.
6. Run Leiden on a log-spaced validation-frozen \(\gamma\) grid, initially \(\{0.25,0.5,0.75,1,1.5,2,3,4\}\), extending only through a documented amendment made before test evaluation.
7. Estimate cluster lineage and persistence across adjacent resolutions and bootstrap resamples.
8. Evaluate candidate split and merge operations with the uncollapsed signature and validation-tuned thresholds.
9. Name nodes from representative accessible evidence. LLM labels, if used, are names only and cannot create, validate, split, or merge a node.
10. Build retrieval indexes and evaluate on the untouched queries.

For box-counting diagnostics, use at least 12 log-spaced candidate epsilon values bounded by nondegenerate neighbor-distance quantiles. Search only contiguous windows meeting Section 4.2. The scale grid and window-selection penalty are fixed before test data is opened.

### 9.4 Split, merge, and compute budget

For each node, calculate components of \(\Phi(C)\) and confidence intervals. Split only if all required criteria and budget pass. Merge unstable, weakly separated siblings as defined in Section 4.5. The adaptive budget is:

\[
B(C)\propto g(D_i(C),U(C),n(C),P(C)),
\]

where \(U\) is estimator uncertainty. The function is a monotone, capped validation-tuned rule, not a learned policy. Uniform allocation receives the same total budget.

### 9.5 Data separation

- **Training:** fits no retrieval qrels; it calibrates embeddings/extractors only if required.
- **Validation:** tunes all thresholds, graph parameters, resolution grids, node budgets, and retrieval fusion weights.
- **Test:** one locked execution. No test-derived labels or ontology edits.
- **Cross-domain:** tune on designated subforums and evaluate on never-tuned subforums.
- **Chronological:** deferred to dated KILT/Wikipedia snapshots or raw timestamped dumps; older snapshots build \(O_t\), newer snapshots evaluate update quality and emerging topics.

Threshold transfer is itself measured. Department-specific retuning on test domains invalidates the generalization claim.

### 9.6 Ablations

Run full FAOG and:

- without dimension;
- without persistence;
- without information/MDL gain;
- without graph features;
- LID-only;
- persistence-only;
- MDL-only/nested-SBM;
- random split/merge policy.

Multifractal, temporal, and hyperbolic ablations are added only if those features later pass their own admission gates. Removing the purported fractal feature without degradation requires concluding that it is unnecessary.

### 9.7 Reproducibility

Use deterministic seeds where libraries allow, record nondeterministic kernels, pin environment and model hashes, version all configuration, store lineage and cost records, and checkpoint each partition. Every table and figure must be regenerable from an experiment manifest. Results are written only from scripts, never hand-copied from notebooks.

---

## 10. Metrics

### 10.1 Preregistered endpoints

- **Primary:** NDCG@10.
- **Secondary retrieval:** Recall@5, Recall@10, Recall@20, Precision@5/10/20, MRR, MAP, query latency, ANN recall, and index size.
- **RAG:** not a primary MVP endpoint. If generation is added later, evaluate blinded answer correctness, groundedness, citation precision/recall, context relevance, and unsupported-claim rate.

### 10.2 Ontology quality

- **Structural coherence:** blinded parent-child narrowing judgments plus centroid/entity diagnostics.
- **Sibling separation:** blinded distinction judgments, inter/intra similarity, and conductance.
- **Coverage:** fraction of test concepts/qrels mapped to at least one accessible node.
- **Redundancy:** near-duplicate node rate under a frozen similarity and evidence-overlap rule.
- **Stability:** variation of information, adjusted mutual information, lineage survival, and tree-edit or ancestor-set stability under bootstrap.
- **Temporal stability:** retained/matched nodes and retrieval change on chronological replay.
- **Compression:** semantic units divided by ontology nodes, always reported with retrieval quality.
- **Security:** restricted-evidence exposure count must be zero in red-team tests.

### 10.3 Hierarchical partial credit

Represent each relevant and predicted concept by its ancestor set. Report hierarchical precision, recall, and F1 over ancestor-expanded labels, plus path-distance error. A prediction that omits an intermediate `Identity` node but recovers `Authentication -> MFA` receives partial rather than zero credit. The ancestor expansion and root handling are frozen before evaluation.

### 10.4 Statistical reporting

Use paired query-level bootstrap intervals and paired randomization tests for retrieval. Use seed-level or resample-level intervals for ontology stability. Report absolute differences, relative differences, standardized effects, sample sizes, and all exclusions. The primary endpoint needs no multiplicity correction; secondary families use Benjamini-Hochberg false-discovery-rate control. Exploratory tests are labeled and cannot replace the primary result. Report means and distributional summaries, never means alone.

---

## 11. Negative Controls

| Control | Expected result | Failure implication |
|---|---|---|
| Randomized or independently permuted embeddings | Geometry evidence and retrieval benefit collapse toward chance/baseline. | Leakage, label contamination, or controller using nonsemantic artifacts. |
| Shuffled cluster membership with sizes preserved | Persistence and ontology quality collapse. | Metrics reward cluster size or labels rather than structure. |
| Erdos-Renyi/configuration graph preserving node/edge counts | Claimed graph scaling and task gain disappear. | Graph statistic is driven by size/density. |
| Degree-preserving graph rewiring | Community semantics and graph-fractal evidence weaken. | Apparent result may be explained solely by degree distribution. |
| Randomized timestamps | Emerging-topic lead time and temporal dependence disappear. | Temporal leakage, seasonality artifact, or invalid event definition. |
| Synthetic hierarchical nonfractal corpus | Hierarchy is recovered but fractal-like evidence is rejected. | Estimator confuses hierarchy with fractality. |
| Known self-similar synthetic structure | Dimension recovered within tolerance and evidence gate passes. | Estimator lacks sensitivity or implementation is wrong. |
| Gaussian mixture matched on covariance and cluster size | Real-corpus scaling fit exceeds the matched null. | Density mixture or anisotropy explains the slope. |
| Query-label shuffle | All retrieval improvements disappear. | Evaluation leakage or invalid statistics. |
| Random split/merge controller at equal budget | Performs below the proposed controller. | Budget or depth alone, not the proposed signals, explains gains. |

Controls are run before the primary test. A failed control blocks interpretation and triggers debugging or no-go; it is not removed post hoc.

---

## 12. Scaling Plan

### 12.1 Stages

| Stage | Objects | Purpose | Architecture decision |
|---|---:|---|---|
| 0 | 10K-100K synthetic | Validate estimators and false-positive behavior | NumPy/Polars, exact neighbors on audit subsets, NetworkX only for small graph checks. |
| 1 | 100K-1M real | Test primary hypothesis | Partitioned Parquet, PyArrow, DuckDB, Polars, FAISS/Qdrant-compatible index abstraction, igraph. |
| 2 | 10M | Scalability and medium replication | Sharded vector indexes, streaming joins, igraph/graph-tool or out-of-core graph representation, distributed jobs only where profiling justifies them. |
| 3 | 100M+ and 300 GB+ source | Enterprise-scale evaluation | Object storage, immutable manifests, distributed embedding/extraction, partition-local metrics, compressed/disk ANN, distributed graph or batch edge processing. |

### 12.2 Data layout

Store raw references separately from normalized units. Parquet partitions contain metadata and vector references, not unrestricted raw content copied into every artifact. Embeddings are sharded by model/version and source partition. Entities and relations use stable IDs and provenance tables. Access-control principals are represented by references to the enterprise authorization system, not flattened into public summaries.

DuckDB and Polars perform predicate pushdown and streaming scans. PyArrow defines interoperable schemas. No stage creates one dataframe for the full corpus. NetworkX is limited to prototypes. Dask, Ray, or Spark is introduced only after a measured single-node bottleneck and a partitionable job definition.

### 12.3 Partitionable jobs

Embedding, entity extraction, relation extraction, local-neighborhood calculation, dimension estimation, clustering by subgraph/level, temporal features, and evaluation are checkpointed jobs. Each job records input manifest, code/config hash, seed, resource use, retries, output checksums, and provenance. Retry must be idempotent.

### 12.4 Hierarchical sampling and adaptive refinement

Start with coarse clusters and stratified samples. Estimate complexity and uncertainty, then refine only eligible regions. Compare adaptive allocation with uniform allocation at equal total cost. Sampling strata include source, domain, time, security class, density, and provisional cluster. Sampling weights and finite-population corrections are recorded.

### 12.5 Incremental updates

For incoming batch \(B_t\):

1. normalize and index \(B_t\);
2. identify affected ontology nodes through nearest neighbors, entities, and graph endpoints;
3. recompute local signatures and lineage only for affected nodes plus ancestors and boundary siblings;
4. evaluate local split/merge changes;
5. version \(O_{t+1}\), retain a reversible change log, and propagate access/deletion changes.

A periodic full audit estimates drift and verifies that accumulated local updates have not diverged materially from a sampled rebuild.

---

## 13. Compute Requirements

All values use decimal GB and are planning ranges, not vendor promises.

### 13.1 Auditable storage formulas

Raw embedding bytes:

\[
S_{\text{emb}}=Ndb,\quad b=2\text{ for fp16},\;4\text{ for fp32}.
\]

| Objects | fp16 384d | fp16 768d | fp16 1536d | fp32 384d | fp32 768d | fp32 1536d |
|---:|---:|---:|---:|---:|---:|---:|
| 100K | 0.0768 GB | 0.1536 GB | 0.3072 GB | 0.1536 GB | 0.3072 GB | 0.6144 GB |
| 1M | 0.768 GB | 1.536 GB | 3.072 GB | 1.536 GB | 3.072 GB | 6.144 GB |
| 10M | 7.68 GB | 15.36 GB | 30.72 GB | 15.36 GB | 30.72 GB | 61.44 GB |
| 100M | 76.8 GB | 153.6 GB | 307.2 GB | 153.6 GB | 307.2 GB | 614.4 GB |

Approximate HNSW structural overhead:

\[
S_{\text{HNSW}}\approx N(4M\alpha+16),
\]

with \(M=16\) to \(32\) and \(\alpha\approx1.2\), or about 93-170 bytes/object: 0.009-0.017 GB at 100K, 0.093-0.170 GB at 1M, 0.93-1.70 GB at 10M, and 9.3-17.0 GB at 100M. Actual libraries may store levels, labels, deleted flags, alignment, and vectors differently; measure serialized index size.

For a directed \(k\)-NN graph storing two uint32 IDs and an fp32 weight:

\[
S_{\text{graph}}=12kN.
\]

At \(k=20\), this is 0.024, 0.24, 2.4, and 24 GB at the four scales. At 100M objects, uint32 IDs remain sufficient, but library/container overhead and reverse edges must be measured.

One typical steady-state case (fp16 768d + HNSW \(M=24\) + \(k=20\) graph + 64 bytes/object metadata) is about 1,971 bytes/object: 0.197 GB, 1.97 GB, 19.7 GB, and 197 GB. Build headroom is 1.5x-3x. Raw/normalized text, entity tables, checkpoints, and replicas are additional.

### 13.2 Planning envelope

Assumptions:

- average 256 encoder tokens per semantic unit;
- measured encoder throughput \(\rho\) is provisionally 3K-15K tokens/s/GPU and must be replaced by a pilot measurement;
- \(T_{\text{embed}}=N\times256/\rho\);
- graph and local-ID work is approximately \(O(Nk)\) after neighbor construction;
- Leiden is approximately \(O(E)\) per sweep in practice, but the number of sweeps/resolutions is measured;
- public text preprocessing is provisionally 10-200 units/s per 32-core node; PDFs, OCR, and code parsing require separate pilots.

| Scale | Suggested active RAM | Build-time disk, including text/intermediates | Embedding GPU-hours at assumed throughput | Graph/analysis CPU-node-hours | Practical wall-clock target |
|---:|---:|---:|---:|---:|---|
| 100K | 8-32 GB | 2-10 GB | 0.5-2.4 | 1-8 on one 32-core node | 2-12 hours including repeated scales/bootstrap |
| 1M | 32-128 GB | 20-100 GB | 4.7-23.7 | 8-80 | 1-4 days on one GPU and one/two CPU nodes |
| 10M | 128-512 GB aggregate | 0.2-1.0 TB | 47-237 | 80-800 | 3-14 days with 4-16 GPUs and several CPU nodes |
| 100M+ | 0.5-2 TB aggregate working memory; prefer out-of-core | 2-10 TB including replicas/checkpoints | 474-2,370 | 800-8,000 | 1-6 weeks with 16-64 GPUs and distributed CPU/storage |

The broad ranges intentionally include repeated resolutions and selected bootstraps but not unrestricted all-pairs or Vietoris-Rips computation. GPU wall time is GPU-hours divided by device count and parallel efficiency. Before each scale-up, a pilot reports throughput with confidence bounds and updates the estimate without changing outcome thresholds.

### 13.3 Economic records

Every run reports CPU-hours, GPU-hours by accelerator type, peak and median RAM, bytes read/written, persistent and temporary disk, wall-clock duration, vector-index build/query cost, embedding API cost if any, and LLM input/output tokens. API cost is:

\[
\text{cost}=\sum_m
\left(
\frac{\text{input tokens}_m}{1000}p^{in}_m+
\frac{\text{output tokens}_m}{1000}p^{out}_m
\right),
\]

using the price captured in the run manifest. Local encoders are preferred for reproducibility and privacy.

---

## 14. Risks

| Risk | Mitigation | Stop or reframe condition |
|---|---|---|
| No valid semantic scaling range | Synthetic calibration, penalized window selection, matched nulls, multiple encoders/metrics | No window or nulls fit equally well: remove fractal claim and \(D_{\text{box}}\). |
| Intrinsic dimension mistaken for fractal dimension | Report estimators separately; use LID-only comparator | LID-only matches within 0.005 NDCG@10: reframe as intrinsic-dimension control. |
| Existing multiresolution/MDL method explains gains | Strong Leiden and nested-SBM baselines; equal tuning budget | Baseline matches quality/cost: no FAOG novelty claim. |
| Hyperbolic geometry is the better model | Deferred but mandatory hyperbolic comparison before broad claim | Hyperbolic-only matches: attribute result to hierarchy geometry. |
| Encoder anisotropy or hubness artifact | Whitening/centering sensitivity, hubness diagnostics, alternate encoder | Effect changes sign or disappears across defensible representations. |
| Cluster-resolution cherry-picking | Freeze gamma/epsilon grids and window rules before test | Any test-informed selection invalidates confirmatory analysis. |
| Approximate ANN changes communities | Exact-neighbor audit sample and ANN-recall threshold | Conclusions change under exact audit. |
| Entity extraction errors dominate graph | Fixed extractor, provenance, confidence calibration, extraction ablation | Gain disappears without one noisy extractor or violates precision floor. |
| Evaluation leakage | Content-hash deduplication, qrel isolation, source/thread group splits | Any label/test leakage requires a full rerun with a new locked test set. |
| Domain or temporal nontransfer | Held-out subforums and later dated snapshots | Per-domain retuning is required to maintain effect. |
| Privacy or ontology inference leakage | Security trimming at every output, minimum support, red-team tests, deletion propagation | Any reproducible unauthorized disclosure blocks deployment. |
| 100M graph/index infeasibility | Shards, disk ANN, hierarchical samples, measured adaptive budget | Cost exceeds Section 15 ceiling without proportional benefit. |
| Nondeterministic or irreproducible results | Manifests, seeds, pinned environments, repeated runs | Effect is not stable across seeds/reruns. |
| Annotation subjectivity | Blinded raters, rubric, inter-rater agreement, adjudication | Agreement below preregistered minimum; human metric becomes exploratory. |
| Economic nonviability | Cost Pareto curve and uniform-budget comparison | No quality, node, or compute advantage at medium scale. |

---

## 15. Go / No-Go Criteria

### 15.1 Synthetic -> real MVP

Proceed only if all conditions pass:

1. Known self-similar point sets recover the expected dimension with median absolute relative error <=15% across eligible sizes and at least 80% interval coverage for nominal 95% bootstrap intervals.
2. The false fractal-like classification rate is <=5% across Gaussian, hierarchical-mixture, scale-free-only, and nested-SBM negative controls.
3. Eligible local ID estimates have median bootstrap coefficient of variation <15% in nodes above \(n_{\min}\).
4. Split/merge decisions achieve ROC AUC >=0.75 against generator-known useful decisions.
5. The full controller beats each single-signal controller by >=0.01 synthetic held-out NDCG@10 on at least one preregistered heterogeneous family and produces <0.005 improvement on semantic-destruction nulls.

If (1) or (2) fails, \(D_{\text{box}}\) and fractal language are removed. The non-fractal adaptive-controller study may continue only through a documented reframe.

### 15.2 MVP -> medium

Proceed only if:

1. the Section 7 primary result passes;
2. no negative control, leakage audit, or security test fails;
3. the sign is consistent across the two preregistered encoders;
4. the full controller beats LID-only, persistence-only, and MDL/nested-SBM by at least 0.01 NDCG@10, or demonstrates the preregistered 20% compute reduction at matched quality;
5. peak MVP cost is within 2x the pre-run resource envelope; and
6. all ontology outputs remain traceable and deletion/security propagation tests pass.

A merely significant but practically smaller effect does not pass.

### 15.3 Medium -> 10M/100M+

Proceed only if KILT replication has the same effect direction, its paired CI excludes zero, and either:

- NDCG@10 improves by at least 0.01 at fixed budgets;
- ontology stability improves by at least 10% at matched retrieval; or
- total indexing/analysis cost falls by at least 20% at matched retrieval.

Projected 100M processing must fit the planning ceiling of 10 TB persistent/build storage, 64 contemporary GPUs, 8,000 32-core CPU-node-hours, and six weeks wall time. These are stop ceilings, not targets. A deployment security review must approve tenant isolation, access-control inheritance, audit logging, and deletion propagation.

### 15.4 Interpretation decision tree

1. **No estimator calibration:** stop mathematical claims; fix implementation once, then no-go or reframe.
2. **Calibration passes but real scaling evidence fails:** state that the corpus shows no supported fractal-like scaling; continue only with intrinsic-dimension/persistence/MDL terminology.
3. **Scaling evidence passes but FAOG does not beat Leiden:** conclude that measured scaling is not useful for the primary ontology task.
4. **FAOG beats Leiden but not single-signal or nested-SBM controls:** attribute the gain to the simpler winning mechanism.
5. **FAOG beats all controls at fixed budget but fails cross-domain/encoder replication:** report a dataset-specific result, not a general mechanism.
6. **All gates and replications pass:** state only that multiscale structural features provided additional useful information for adaptive ontology resolution. Do not state that enterprise knowledge was proven fractal.

### 15.5 Preregistration and change control

Before execution, timestamp and hash this plan, dataset manifests, query splits, scale grids, metrics, thresholds/search spaces, exclusion rules, seeds, and statistical scripts. Any amendment records date, rationale, affected analyses, and whether it occurred before or after test access. Post-test changes are exploratory and cannot replace the confirmatory result. Null results, failed controls, resource overruns, and excluded runs remain in the final report.

### 15.6 Phased deliverables

| Phase | Deliverable | Gate |
|---|---|---|
| Research | This plan, verified bibliography, novelty analysis, frozen hypotheses | Independent review accepts falsifiability and baseline strength. |
| Synthetic | Estimator calibration report and control results | Section 15.1. |
| Small MVP | Vector vs hierarchical Leiden vs FAOG report with ablations | Section 15.2. |
| Medium | KILT replication, chronological design, cost model update | Section 15.3. |
| Large | Partitioned 10M then 100M+ evaluation | Each scale must pass quality, cost, and privacy gates. |
| Application | Local web exploration and enterprise integration | Only after a positive, reproducible research gate; UI must enforce security trimming. |

## Final recommendation

Proceed only to synthetic validation. Do not yet build the production corpus pipeline, hyperbolic FAOG, multifractal analysis, reinforcement learning, or a 300 GB deployment. The first likely publishable contribution is not a "fractal ontology"; it is a rigorously tested local resolution-control policy. The default expectation should be that ordinary multiresolution clustering, nested-SBM/MDL, or intrinsic dimension explains the data until the preregistered experiments show otherwise.

**Go / no-go posture:** conditional go for synthetic validation and the small public-data MVP only; no-go for production implementation or scale-up until the preregistered synthetic, retrieval, stability, security, and compute gates are met.
