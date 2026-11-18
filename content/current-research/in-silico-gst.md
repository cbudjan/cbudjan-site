---
title: "In Silico Modeling of Gastruloid Morphogenesis"
tag: "Modeling + experiment · bioRxiv 2026"
image: "/img/projects/in-silico-banner.png"
weight: 2

# Optional: per-page description for SEO / OG tags
description: "Agent-based modeling and human gastruloid merging experiments show that forming a single body axis requires both short-range adhesion and long-range attraction between cells."
---

## Summary

Establishing the anterior–posterior (head-to-tail) axis is a key symmetry-breaking event in mammalian development. Gastruloids, our 3D stem cell-based embryo models, undergo a similar process: aggregates of human embryonic stem cells start out roughly spherical and, after Wnt pathway stimulation, reliably elongate and form a single posterior pole within 72 hours. Recent work shows that gastruloids do not get there from a uniform state. They first establish an *inside–outside* difference: outer cells have higher Wnt activity and tend toward primitive streak-like fates, while inner cells have higher Nodal activity and remain more pluripotent. A radial pattern like this has no preferred direction on the surface of the aggregate. The question we asked is what cell–cell interactions convert it into **one** stable axis.

### Human gastruloids reproducibly form a single axis

We first quantified how reproducible this process is. Using a germ-layer reporter line (RUES2-GLR), we segmented the anterior and posterior domains of each gastruloid and computed a separation score: the distance between the two domain centers, normalized by aggregate size. Across 10 gastruloids the score was 1.38 ± 0.10, corresponding to a clearly polarized geometry. This gave us an experimental reference against which to compare simulations.

### A two-population model

We built a coarse-grained **agent-based computational model** in which each cell is a point agent. Simulations start from a compact sphere of 1,500 cells with a radial prepattern: 25% *outer* cells forming a peripheral shell and 75% *inner* cells forming the core. Cells interact through two classes of forces: short-range contact forces that capture adhesion between neighbors, and an optional long-range attraction or repulsion. The long-range term is phenomenological. It stands for any process that biases cells toward or away from other cells over distances longer than direct contact, without committing to a molecular mechanism. We scanned 177,957 combinations of interaction parameters and asked which ones produce one stable axis while keeping the cells in a single aggregate.

### Differential adhesion alone is not enough

The classical explanation for cell sorting invokes **differential adhesion**: cells of the same type stick to each other more strongly than to cells of a different type. In our simulations, the best adhesion-only settings followed exactly this logic, but they did not reliably produce a single axis. Runs ended in weak separation, small displaced clusters, or fragmentation, and this held across noise levels. With adhesion alone, no parameter setting met our criterion for axis formation. This is consistent with synthetic multicellular systems built from engineered adhesion molecules, which sort cells but tend to produce variable numbers of clusters rather than one axis.

### Long-range attraction between outer cells produces one axis

We then added one long-range interaction at a time. One stood out: **attraction among outer cells**. With it, the outer cells collect into one pole, the inner cells form the opposite domain, and most cells stay in one aggregate. Outer-to-outer attraction was present in 99.94% of the top 1% of parameter sets, and as its strength increased, the fraction of adhesion settings that formed an axis rose from 0% to 18%. Rescored the same way as the experimental images, successful simulations gave a separation score of about 1.46, close to the measured 1.38.

The two kinds of interaction play different roles. Adhesion provides local cohesion and sorting: strong inner–inner adhesion keeps the core together, weak inner–outer adhesion lets the populations separate, and moderate outer–outer adhesion keeps outer cells associated while still letting them rearrange. Long-range attraction provides the global coordination that selects a single direction, and it makes the outcome far less dependent on fine-tuned adhesion. The result also does not depend on a perfect initial shell: what matters is that cells at the periphery can coordinate over distances longer than direct contact.

### Testing the prediction: merging gastruloids

The model makes a prediction that can be tested directly. If two polarized gastruloids are brought together in *opposite* orientations, adhesion alone should leave their two posterior poles at opposite ends of the fused aggregate. Long-range attraction should instead make the poles travel around the surface and join. In simulations, the fraction of pairs ending with one continuous posterior domain went from 0% without long-range attraction to 97% with it.

Human gastruloid merging experiments showed the predicted behavior. Pairs that met in the same orientation fused quickly, usually within 6 hours. Pairs that met in opposite orientations fused over about 30 hours, as their posterior regions moved around the periphery of the fused aggregate and converged. In all 12 pairs examined (6 of 6 at each of two CHIR doses), the merged aggregate ended with a single posterior domain. This does not identify the molecular basis of the interaction, but it supports the idea that an attraction-like interaction coordinates posterior cells over distances longer than cell–cell contact.

### From mechanics to genetics: a minimal regulatory circuit

Finally, we asked whether gene regulation could generate both the cell states and the mechanical interactions, starting from a uniform population with no pre-assigned cell types. We designed a minimal three-gene circuit. A *timer* gene starts high and decays, separating an early pattern-establishment stage from a later mechanical stage. Spatial information comes from the geometry of the aggregate: cells at the center receive more distance-dependent signal than cells at the surface. A *mutually inhibitory switch* between the other two genes, an abstract counterpart of the opposing Wnt and Nodal activities seen in gastruloids, converts this radial difference into two stable cell states, and a *lock-in* module preserves them. The gene state then sets each cell's adhesion and long-range attraction.

In this model, an initially uniform spherical aggregate forms radial gene-expression differences and then a single polarized axis, without pre-specified cell types or an externally imposed direction.

### DevSim: an open simulation platform

The three-gene circuit is one point in a much larger design space. To make that space easier to explore, we built **DevSim**, a MATLAB-based platform for simulating coupled gene-regulatory and mechanical models of multicellular patterning. Users can change the cell population, gene network, signaling and mechanical parameters, and noise levels, and DevSim visualizes gene expression, cell positions and aggregate shape over time. It runs on a personal computer, on a computing cluster, or through MATLAB Online. By changing the network topology and parameters, the same framework also produces layered, bilobed, multilobed and striped patterns. Code and data are available at [github.com/hormoz-lab/Symmetry-Breaking](https://github.com/hormoz-lab/Symmetry-Breaking).

### Why it matters

Adhesion can sort cells locally, but our results suggest that building one reproducible axis also requires a way for cells to coordinate across the whole aggregate. For synthetic developmental biology, this points to a design rule: programmable adhesion may need to be combined with engineered signaling, motility or attraction-like interactions that act over longer distances.

---

{{< callout >}}
**In plain terms:** When stem cells form a tiny ball in a dish, they reliably work out which end will become the "tail" end, even though the ball starts out round. We ran nearly 180,000 computer simulations testing different rules for how the cells might push and pull on each other. The usual explanation, that cells simply stick preferentially to their own kind, turned out not to be enough. The missing ingredient is that cells on the *outside* of the ball also need to attract each other over longer distances. With this long-range pull, the outer cells gather at one pole every time, setting up the body axis. The model then made a prediction we could test in the lab: if two of these structures are pushed together facing opposite ways, their two "tail" ends should travel around the surface and merge into one. That is what we saw. We also showed that a simple three-gene program can generate the whole sequence from scratch, and built a free simulation tool so others can explore these principles.
{{< /callout >}}

---

## Representative figures

{{< figure
  src="/img/projects/in-silico-fig1c.jpg"
  alt="Two human gastruloids at 48 and 72 hours with SOX2, TBXT and SOX17 reporter cells clustered in adjacent domains at one end"
  caption="**Fig. 1C.** Fluorescence images of two gastruloids at 48 h and 72 h made from RUES2-GLR germ-layer reporter cells. SOX2 (yellow) labels neuroectoderm-like cells, TBXT/BRA (cyan) primitive streak/mesoderm-like cells, and SOX17 (magenta) endoderm-like cells. The three germ layers form spatially organized domains. Scale bar: 100 µm."
>}}

{{< figure
  src="/img/projects/in-silico-fig4d.jpg"
  alt="Simulated cell aggregates in five replicates: without long-range attraction red outer cells stay scattered around a blue core; with it, red and blue cells separate into two poles"
  caption="**Fig. 4D.** Final states from five simulation replicates with the same adhesion parameters, without (top) and with (bottom) long-range outer-to-outer attraction (β<sub>o→o</sub> = 0.135). Outer cells: red; inner cells: blue. Adding long-range attraction converts weak or local separation into one stable axis."
>}}

{{< figure
  src="/img/projects/in-silico-fig5b.jpg"
  alt="Brightfield time course of two pairs of merging human gastruloids from 48 to 78 hours, with arrowheads marking the posterior poles; the same-orientation pair fuses quickly, while in the opposite-orientation pair the poles move around the aggregate"
  caption="**Fig. 5B.** Two merging human gastruloids imaged every 6 h. The first column shows TBXT/BRA fluorescence at 48 h, before merging, marking the initial posterior poles (orange and red arrowheads). Same-orientation pairs merge rapidly; opposite-orientation pairs merge more slowly as the posterior poles move around the periphery of the fused aggregate. Scale bars: 100 µm."
>}}

{{< figure
  src="/img/projects/in-silico-fig6e.jpg"
  alt="Simulation snapshots over time of a cell aggregate colored by expression of three genes; an initially uniform sphere develops an inside–outside pattern and then a single red pole"
  caption="**Fig. 6E.** Pattern formation driven by the three-gene circuit, starting from a uniform spherical aggregate (gray = low expression, red = high). Row 1 shows the whole aggregate colored by G2; rows 2–4 show cross-sections colored by G1, G2 and G3. The circuit first generates radial differences in gene expression, then activates the mechanical interactions that move the outer population into one pole."
>}}

---

## Citation

Guan G.<sup>†</sup>, Wang S.<sup>†</sup>, Shields T.G.<sup>†</sup>, Pahng S.H., Shao C.X., Ye J., **Budjan C.**<sup>‡</sup>, Hormoz S.<sup>‡</sup> (2026). Robust axis formation requires both short-range adhesion and long-range attraction. *bioRxiv* 2025.09.27.678924. doi: [10.1101/2025.09.27.678924](https://doi.org/10.1101/2025.09.27.678924)

<sup>†</sup> Equal contribution &nbsp;&nbsp; <sup>‡</sup> Co-corresponding authors (S. Hormoz is lead contact)
