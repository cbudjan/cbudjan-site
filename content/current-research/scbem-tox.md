---
title: "Stem Cell-Based Embryo Models as Pre-Clinical Toxicity Platforms"
tag: "Translational · Collaboration"
image: "/img/projects/scbem-tox-banner.jpg"
image_alt: "Two human gastruloids at 48 and 72 hours with TBXT, SOX2 and SOX17 reporter cells in separate domains at one end"
weight: 3
description: "Human gastruloids with a built-in genetic control for cereblon, built to detect developmental toxicity of targeted protein degraders that animal studies cannot reliably predict."
---

## Summary

A central and unresolved problem in drug development is predicting whether a therapeutic compound will harm an embryo. Standard pre-clinical safety studies rely on rodent and rabbit embryo-fetal development studies, but for a growing class of modern therapeutics these species cannot answer the question — not because the experiments are poorly designed, but because the relevant biology differs between species.

We are building a developmental toxicity assay from **human gastruloids**, three-dimensional stem cell aggregates that model gastrulation, with a genetic control built into the assay itself. This work is carried out in collaboration with the laboratory of **Drs. Li Chai and Jun Liu** at Brigham and Women's Hospital, Boston.

### Why this matters now

The problem is most acute for **targeted protein degraders**, small molecules that recruit the cell's own degradation machinery to eliminate a disease-causing protein. Most of them work through **cereblon (CRBN)**, a protein that selects targets for an E3 ubiquitin ligase. More than 27 cereblon-engaging drugs are in registered interventional trials.

They all bind the same pocket that thalidomide binds. Degraders that raise **fetal hemoglobin** make the question urgent: raising fetal hemoglobin can reduce the severity of sickle cell disease and β-thalassemia, degraders of the repressors WIZ and ZBTB7A offer a route to do so [1,2], and WIZ-degrader programs have entered Phase 1/2 trials. These are treatments that could be taken for years, across reproductive years — and a 2026 review found no developmental safety data for any of them [3].

### How a drug can remove proteins an embryo needs

{{< figure
  src="/img/projects/scbem-mechanism.jpg"
  alt="Diagram: cereblon-engaging degraders bind the tri-tryptophan pocket of CRBN, which then recruits a zinc-finger neosubstrate for ubiquitination and degradation, removing SALL4, TP63 and PLZF and causing human embryopathy"
  caption="**One pocket, every drug.** Thalidomide-like molecules bind the tri-tryptophan pocket of cereblon and change its binding surface, so that it recruits additional proteins — neosubstrates — for destruction. Many carry a zinc-finger domain with the structural feature cereblon recognises. Among them are SALL4, TP63 and PLZF, transcription factors that control human development."
>}}

Thalidomide acts through cereblon and caused an estimated 10,000 cases of birth defects. It does so by changing cereblon's binding surface so that it recruits proteins it would not normally touch, including the developmental transcription factors **SALL4**, **TP63** and **PLZF** [4–6]. The link to human malformations is direct: inherited *SALL4* mutations cause Duane-radial-ray and acro-renal-ocular syndromes, whose features overlap those caused by thalidomide [7].

So a degrader can remove developmental proteins alongside its intended target. The question is how to detect that before a drug reaches patients.

### Why animal studies miss it

{{< figure
  src="/img/projects/scbem-species.jpg"
  alt="Table comparing human, rabbit, mouse and Crbn I391V mouse for a permissive CRBN pocket and a degradable SALL4 degron, with outcomes embryopathy, malformation, none and fetal loss only"
  caption="**Rodents resist thalidomide for two independent reasons.** A check mark denotes a permissive cereblon pocket or a substrate that can be degraded. Mice carrying the humanising I391V substitution gain a permissive pocket but still have a resistant Sall4 degron, and show fetal loss without limb defects."
>}}

Rodent resistance has **two independent genetic causes**, and correcting one does not correct the other. The rodent cereblon binding pocket differs from the human pocket; the single I391V substitution is enough to make mice sensitive to some thalidomide effects [8]. But the target proteins differ too: mouse Sall4 resists degradation even in mice that express human cereblon [4,9]. Fixing the receptor therefore leaves the substrate problem untouched.

Metabolism adds a third difference — rabbit responses involve the active metabolite 5-hydroxythalidomide. And the broader record is sobering: in a European Medicines Agency analysis of 369 pharmaceuticals, rat and rabbit developmental findings agreed for only about 55% of compounds [10].

### Human gastruloids close the species gap

{{< figure
  src="/img/projects/scbem-species-gap.jpg"
  alt="Plot of adverse-effect concentrations: retinoic acid and valproate affect human and mouse gastruloids equally, while thalidomide acts at 0.4 micromolar in human gastruloids and shows no effect above 100 micromolar in mouse gastruloids"
  caption="**Only cereblon-dependent teratogens show a species gap.** Human and mouse gastruloids respond to retinoic acid and valproate at the same concentrations. For thalidomide the two models differ by at least 250-fold, and a mouse gastruloid assay also failed to detect pomalidomide at 400 µM. Open symbols with arrows mark no effect at the highest concentration tested."
>}}

Human gastruloids are self-organised aggregates of human pluripotent stem cells that reproduce early events of human development: they elongate, form an anterior–posterior axis, and produce cells of all three germ layers within 72 hours [11].

The published comparison is striking. Human gastruloids respond to thalidomide at **0.4 µM**, while mouse gastruloids show no effect at **100 µM** [12]. A mouse gastruloid assay also missed pomalidomide at 400 µM [13]. Both species respond identically to retinoic acid and valproate — so the gap is specific to the cereblon-dependent compounds, which is exactly what the biology predicts.

Regulators are actively looking for human-relevant alternatives. The ICH S5(R3) guideline permits alternative assays within a weight-of-evidence assessment, the FDA Roadmap to Reducing Animal Testing supports new approach methodologies, and the ISTAND programme provides a route to qualify them. A 2026 Health and Environmental Sciences Institute consensus co-authored by FDA scientists called for rigorous safety assessment of cereblon-recruiting degraders and for methods that distinguish intended from unintended degradation [14]. An IQ Consortium report had already found no established best practices, and cautioned that SALL4 loss alone is unlikely to explain every effect [15].

### Our approach: a genetic control inside the assay

Existing human assays provide a foundation but lack a genetic test of mechanism. Our central idea is to compare drug responses in **genetically matched human gastruloids with and without cereblon**.

We use RUES2-GLR, a human embryonic stem cell line carrying fluorescent reporters for TBXT, SOX2 and SOX17, which mark mesoderm, ectoderm and endoderm [16]. From it we are generating an **isogenic CRBN-null** line — identical apart from the deletion — together with a wild-type rescue that re-introduces cereblon. If a drug response disappears or shifts in the null cells and returns on rescue, the effect depends on cereblon. If it persists, it does not.

This matters because a fixed panel of protein measurements can miss the relevant target. More than 1,600 human proteins are predicted to be compatible with cereblon recruitment [17], and proteomic studies keep finding neosubstrates that lack the canonical recognition motif. Morphology and germ-layer reporters instead measure the **combined developmental consequence** of whatever is lost.

### What we are testing

Two things in parallel. First, **qualifying the assay**: measuring how CRBN deletion affects untreated development, then running a panel of reference teratogens and non-teratogens through both genotypes to estimate sensitivity, specificity and how far each response shifts when cereblon is removed.

Second, **applying it to fetal-haemoglobin degraders**: SH6, a non-IMiD degrader of ZBTB7A developed by the Chai lab [2,18], alongside the WIZ degraders dWIZ-1 and dWIZ-2 [1], with thalidomide and lenalidomide as class positives and decitabine — which raises fetal haemoglobin without cereblon — as a mechanism control. Where both numbers can be estimated, we will compare the concentration that disturbs development with the published concentration that induces fetal haemoglobin in erythroid cells, as an exploratory developmental therapeutic index. The point is to test whether therapeutic potency and developmental effect can be separated between compounds that do the same job.

---

{{< callout >}}
**In plain terms:** Some of the most promising new medicines work by instructing a cell to destroy a disease-causing protein. They are showing real results for blood diseases and cancer. But nearly all of them work through one protein, cereblon — the same protein thalidomide hijacked to cause birth defects in the 1950s and 60s. Safety tests in rats and rabbits cannot settle the question, because those animals are resistant for two separate genetic reasons that do not apply to people. We grow tiny, embryo-like structures from human stem cells that carry out the first steps of development in a dish, and we are making a matched version with cereblon removed. Comparing the two tells us not only whether a drug disturbs development, but whether it does so through cereblon — which is the thing a drug developer can actually act on. The goal is to flag risk early, in human biology, long before anyone is exposed.
{{< /callout >}}

---

## Interested in collaborating?

We are actively seeking collaborations with academic laboratories and industry partners interested in early developmental safety assessment of therapeutic compounds. This includes groups developing cereblon-engaging or other targeted protein degraders, as well as programmes in any therapeutic area where human-specific developmental toxicity is a concern and standard animal models may not provide adequate safety information. If you would like to discuss a potential collaboration, please [get in touch]({{< relref "contact" >}}).

---

## Selected references

[1] Ting PY, Borikar S, Kerrigan JR, et al. A molecular glue degrader of the WIZ transcription factor for fetal hemoglobin induction. *Science.* 2024;385(6704):91–99. doi:[10.1126/science.adk6129](https://doi.org/10.1126/science.adk6129)

[2] Liu J, Shen Z, Park SY, et al. A non-IMiD multi-target degrader reactivates fetal hemoglobin. *Exp Hematol Oncol.* 2026;15. doi:[10.1186/s40164-026-00846-5](https://doi.org/10.1186/s40164-026-00846-5)

[3] Arji S, Shen Z, Welch S, et al. Targeted protein degradation for fetal hemoglobin induction: a new paradigm in β-hemoglobinopathy therapy. *Biomark Res.* 2026;14(1):59. doi:[10.1186/s40364-026-00911-5](https://doi.org/10.1186/s40364-026-00911-5)

[4] Matyskiela ME, Couto S, Zheng X, et al. SALL4 mediates teratogenicity as a thalidomide-dependent cereblon substrate. *Nat Chem Biol.* 2018;14(10):981–987. doi:[10.1038/s41589-018-0129-x](https://doi.org/10.1038/s41589-018-0129-x)

[5] Asatsuma-Okumura T, Ando H, De Simone M, et al. P63 is a cereblon substrate involved in thalidomide teratogenicity. *Nat Chem Biol.* 2019;15(11):1077–1084. doi:[10.1038/s41589-019-0366-7](https://doi.org/10.1038/s41589-019-0366-7)

[6] Yamanaka S, Murai H, Saito D, et al. Thalidomide and its metabolite 5-hydroxythalidomide induce teratogenicity via the cereblon neosubstrate PLZF. *EMBO J.* 2021;40(4):e105375. doi:[10.15252/embj.2020105375](https://doi.org/10.15252/embj.2020105375)

[7] Kohlhase J, Schubert L, Liebers M, et al. Mutations at the SALL4 locus on chromosome 20 result in a range of clinically overlapping phenotypes. *J Med Genet.* 2003;40(7):473–478. doi:[10.1136/jmg.40.7.473](https://doi.org/10.1136/jmg.40.7.473)

[8] Fink EC, McConkey M, Adams DN, et al. Crbn I391V is sufficient to confer in vivo sensitivity to thalidomide and its derivatives in mice. *Blood.* 2018;132(14):1535–1544. doi:[10.1182/blood-2018-05-852798](https://doi.org/10.1182/blood-2018-05-852798)

[9] Gemechu Y, Millrine D, Hashimoto S, et al. Humanized cereblon mice revealed two distinct therapeutic pathways of immunomodulatory drugs. *Proc Natl Acad Sci USA.* 2018;115(46):11802–11807. doi:[10.1073/pnas.1814446115](https://doi.org/10.1073/pnas.1814446115)

[10] Roos P, Anggasta C, Piersma AH, et al. Evaluation of rat and rabbit embryofetal development studies with pharmaceuticals: the added value of a second species. *Crit Rev Toxicol.* 2024;54(9):619–633. doi:[10.1080/10408444.2024.2374281](https://doi.org/10.1080/10408444.2024.2374281)

[11] Moris N, Anlas K, van den Brink SC, et al. An in vitro model of early anteroposterior organization during human development. *Nature.* 2020;582(7812):410–415. doi:[10.1038/s41586-020-2383-9](https://doi.org/10.1038/s41586-020-2383-9)

[12] Mantziou V, Baillie-Benson P, Jaklin M, et al. In vitro teratogenicity testing using a 3D, embryo-like gastruloid system. *Reprod Toxicol.* 2021;105:72–90. doi:[10.1016/j.reprotox.2021.08.003](https://doi.org/10.1016/j.reprotox.2021.08.003)

[13] Huntsman MC, Kurashima CK, Marikawa Y. Validation of a mouse 3D gastruloid-based embryotoxicity assay in reference to the ICH S5(R3) guideline chemical exposure list. *Reprod Toxicol.* 2024;125:108558. doi:[10.1016/j.reprotox.2024.108558](https://doi.org/10.1016/j.reprotox.2024.108558)

[14] Garside H, Aslamkhan A, Daniels DL, et al. Safety considerations for cereblon-recruiting targeted protein degraders. *Nat Rev Drug Discov.* 2026;25(8):648–662. doi:[10.1038/s41573-026-01426-2](https://doi.org/10.1038/s41573-026-01426-2)

[15] Loberg LI, Proctor WR, Burdick AD, et al. Nonclinical teratogenicity safety assessment of CRBN-engaging targeted protein degraders: Points to consider. *Regul Toxicol Pharmacol.* 2025;158:105793. doi:[10.1016/j.yrtph.2025.105793](https://doi.org/10.1016/j.yrtph.2025.105793)

[16] Martyn I, Kanno TY, Ruzo A, Siggia ED, Brivanlou AH. Self-organization of a human organizer by combined Wnt and Nodal signalling. *Nature.* 2018;558(7708):132–135. doi:[10.1038/s41586-018-0150-y](https://doi.org/10.1038/s41586-018-0150-y)

[17] Petzold G, Gainza P, Annunziato S, et al. Mining the CRBN target space redefines rules for molecular glue-induced neosubstrate recognition. *Science.* 2025;389(6755):eadt6736. doi:[10.1126/science.adt6736](https://doi.org/10.1126/science.adt6736)

[18] Liu BH, Liu M, Radhakrishnan S, et al. Targeting transcription factors through an IMiD-independent zinc finger domain. *EMBO Mol Med.* 2025;17(6):1393–1416. doi:[10.1038/s44321-025-00241-3](https://doi.org/10.1038/s44321-025-00241-3)
