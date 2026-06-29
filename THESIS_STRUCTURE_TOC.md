# Thesis Structure — Table of Contents (Writing Plan)

**Thesis:** *Uplifting End-of-Life RO Membranes via Polyamide Regeneration*
**Author:** Jonathan Cao · UNSW Chemical Engineering Honours
**Supervisor:** Prof. Pierre Le-Clech · Co-supervisor: John Ogbe
**Purpose of this file:** A section-by-section skeleton to write into manually. Tick boxes as you draft. Each bullet is a *prompt for one paragraph or short block* — not a heading to copy verbatim. Target lengths are rough guides for an experimental Honours thesis (~50–70 pp body).

Status key: `[ ]` not started · `[~]` drafting · `[x]` done

---

## Front Matter
- [ ] Title page *(already scaffolded in LaTeX)*
- [ ] Abstract — 250–300 words: problem, what you did, key result, what it means *(write LAST)*
- [ ] Acknowledgements
- [ ] Table of Contents *(auto)*
- [ ] List of Figures / List of Tables *(auto)*
- [ ] List of Abbreviations — RO, EoL, TFC, PA, PSF, IP, MPD, TMC, PWP, NaCl rejection, LRV, TMP

---

## Chapter 1 — Introduction  *(~4–6 pp)*
A funnel: broad water context → membrane waste problem → the specific gap → your aim. Keep it short and punchy; the depth lives in Ch. 2.

- [ ] **1.1 Background & motivation** — water scarcity, RO as the dominant desal technology, the resulting EoL membrane waste stream
- [ ] **1.2 Problem statement** — EoL membranes are landfilled/incinerated; downcycling (RO→NF→UF) wastes the asset; regeneration is under-explored
- [ ] **1.3 Project aim** — *one sentence*: evaluate whether EoL RO membranes (A and C) can be uplifted by depositing a new polyamide layer via in-situ IP, and how cleaning intensity beforehand affects the result
- [ ] **1.4 Objectives** — numbered list (clean → in-situ IP → PWP + NaCl rejection across 3 arms × 2 membranes; autopsy selected coupons)
- [ ] **1.5 Scope & limitations** — in scope vs out of scope (no fouling profiling, no IP/cleaning optimisation, no LCA); pull straight from Project Plan Rev 2 §2
- [ ] **1.6 Thesis outline** — one short paragraph mapping the chapters

---

## Chapter 2 — Literature Review  *(~18–25 pp — the heart of the report)*
Sequenced in the **background → importance → current methods → limitations → new method → detail** flow you asked for. Your existing draft maps onto this cleanly; the mapping is noted per section.

### 2.1 Background — the EoL RO membrane problem *(your "Global Context" section)*
- [ ] **2.1.1** Global installed RO capacity & membrane replacement rates
- [ ] **2.1.2** Estimated annual EoL waste volumes
- [ ] **2.1.3** Current disposal practices — landfill / incineration / recycling

### 2.2 Why it matters — environmental & economic stakes *(the "Why important" beat)*
- [ ] **2.2.1** Environmental concerns — polymer persistence, landfill burden
- [ ] **2.2.2** Economic stakes — cost per element, replacement cycle (frames why recovery is worth it)
- [ ] **2.2.3** Sustainability framing — value lost when a high-grade asset is downcycled or dumped

### 2.3 Membrane fundamentals *(needed before you can discuss degradation/regeneration)*
- [ ] **2.3.1** TFC architecture & layer functions — polyester (strength), PSF (porous support), polyamide (rejection)
- [ ] **2.3.2** Polyamide selective-layer chemistry — IP reaction, MPD + TMC monomers, mechanism, crosslink density, thickness, roughness, hydrophilicity
- [ ] **2.3.3** Role of the PSF substrate — pore-size distribution; why substrate condition decides whether regeneration is even possible

### 2.4 Degradation mechanisms — why membranes reach EoL *(sets up what regeneration must overcome)*
- [ ] **2.4.1** Chemical degradation — chlorination of polyamide, hydrolysis/oxidation → ↑permeability, ↓rejection
- [ ] **2.4.2** Mechanical & operational ageing — compaction, pressure damage (delamination, support collapse)
- [ ] **2.4.3** Fouling & surface modification — organic, scaling, biofouling; fouling triggers cleaning that accelerates degradation
- [ ] **2.4.4** Net impact on performance — flux, salt rejection, LRV, TMP

### 2.5 Current EoL management methods *(the "Current methods" beat)*
- [ ] **2.5.1** Direct reuse — secondary desalination, industrial filtration
- [ ] **2.5.2** Mechanical recycling — module dismantling, polymer recovery; mixed-material / low-value problem
- [ ] **2.5.3** Chemical downcycling — RO→NF→UF via controlled oxidation (NaOCl, KMnO₄)

### 2.6 Limitations of current methods *(the "Limitations" beat — make the gap explicit)*
- [ ] **2.6.1** Downcycling discards rejection capability — one-way, value-destroying
- [ ] **2.6.2** Recycling economics are weak; reuse is short-lived
- [ ] **2.6.3** → Motivates *restoring* RO performance rather than degrading to a lower grade

### 2.7 Polyamide regeneration / membrane uplifting *(broad overview of the new method)*
- [ ] **2.7.1** Concept — rebuild rather than degrade the selective layer; recover RO performance, extend lifetime
- [ ] **2.7.2** Prior work — Garcia-Pacheco, Ogbe et al., and others (position your work against them)

### 2.8 Regeneration in detail *(more depth on the new method — the techniques you actually use)*
- [ ] **2.8.1** Polyamide removal techniques — oxidative, solvent dissolution, enzymatic; challenge: don't damage the PSF
- [ ] **2.8.2** Rebuilding PA via interfacial polymerisation — controlling film formation, substrate surface chemistry, pore size, wetting, monomer diffusion
- [ ] **2.8.3** Substrate influence on regeneration — PSF pore size, roughness, hydrophilicity, oxidation damage
- [ ] **2.8.4** *(optional)* Techno-economic / sustainability outlook — keep brief; it's out of your experimental scope

### 2.9 Research gaps & how this thesis responds
- [ ] State the specific unanswered questions (esp. effect of pre-IP cleaning intensity), then link each to an objective from §1.4

---

## Chapter 3 — Materials & Methods  *(~10–14 pp — write this EARLY, while procedures are fresh)*
Pull from the Lab Manual, Project Plan Rev 2 §3–4, and the Experiment Tracker. Write so a competent reader could reproduce it. Past tense, passive where natural.

- [ ] **3.1 Materials** — membranes A & C (MemBrane Works, first/second pass); MPD, TMC, n-hexane, NaOH, EDTA, citric acid, HCl, NaCl; grades & suppliers
- [ ] **3.2 Experimental design** — 2 membranes × 3 arms = 6 conditions; arm definitions (1 no-clean, 2 standard clean, 3 extensive clean); coupon → cut into 2–3 pieces = replicates; *include a design schematic/table*
- [ ] **3.3 Cleaning protocols** — base (0.1% NaOH + 0.8–1% EDTA) → rinse → acid (2% citric acid + HCl to pH 1–2); durations/temperature; Arm 3 = extended time
- [ ] **3.4 In-situ interfacial polymerisation** — MPD 1.5 wt% (3 min, waste-first flush) → TMC 0.2 wt% in hexane (60 s) → heat cure (compressed air via 98 °C bath, ~60 °C at membrane, 5 min); coupon orientation marking
- [ ] **3.5 High-pressure crossflow rig & compaction** — rig description + diagram; compaction 30 min at 15 bar
- [ ] **3.6 Performance characterisation**
  - [ ] 3.6.1 Pure water permeability — PWP = V/(A·t·ΔP); A = 0.0139 m²; record ΔP & temperature
  - [ ] 3.6.2 NaCl rejection — R = 1 − (κ_p/κ_f); feed concentration; conductivity method
- [ ] **3.7 Membrane autopsy** — analyses (FTIR/XPS/SEM-EDS — confirm) and coupon-selection criteria
- [ ] **3.8 Safety & waste handling** — hexane (respirator, no heating with hexane present), TMC storage, acid/base handling, waste routes
- [ ] **3.9 Deviations from protocol** — note where execution differed (cross-ref Tracker deviation log)

---

## Chapter 4 — Results & Discussion  *(~12–18 pp — combined is usual for Honours)*
Organise by *theme/metric*, not by chronological lab day. Each block: present data → interpret → connect to literature.

- [ ] **4.1 Cleaning outcomes** — visual/observational effect of each arm before IP
- [ ] **4.2 Pure water permeability** — PWP across arms & membranes; figure (bar/scatter) + table; compare vs new-membrane / EoL baselines
- [ ] **4.3 Salt rejection** — R across arms & membranes; figure + table
- [ ] **4.4 Permeability–rejection trade-off** — the key plot; where do regenerated coupons land vs commercial RO?
- [ ] **4.5 Effect of cleaning intensity** — Arm 1 vs 2 vs 3: does more cleaning help, hurt, or not matter? *(your central question)*
- [ ] **4.6 Membrane A vs C** — differences attributable to first- vs second-pass origin
- [ ] **4.7 Autopsy findings** — surface chemistry/morphology supporting the performance story
- [ ] **4.8 Discussion synthesis** — reconcile results with Ch. 2; what worked, what surprised you, mechanisms
- [ ] **4.9 Limitations & sources of error** — replicate count, compaction time, rig variability, measurement uncertainty

---

## Chapter 5 — Conclusions & Future Work  *(~3–4 pp)*
- [ ] **5.1 Conclusions** — answer the aim directly; restate the 2–3 headline findings (no new data)
- [ ] **5.2 Recommendations / future work** — IP & cleaning optimisation, more replicates, longer compaction, LCA/techno-economics, scale-up, the open questions you didn't close

---

## Back Matter
- [ ] **References** — EndNote/BibTeX; keep `references.bib` current as you cite
- [ ] **Appendix A** — full Experiment Tracker data / raw PWP timings & conductivities
- [ ] **Appendix B** — Lab Manual SOP (or cross-reference)
- [ ] **Appendix C** — risk assessment / safety data
- [ ] **Appendix D** — additional figures, calibration, autopsy spectra

---

## Suggested writing order (not document order)
1. **Ch. 3 Methods** — easiest; do it now while the lab work is live.
2. **Ch. 2 Literature Review** — you already have the skeleton; flesh it out in parallel with lab weeks.
3. **Ch. 4 Results** — as data lands (rig work done ~7 Aug).
4. **Ch. 1 Introduction** — once the story is clear.
5. **Ch. 5 Conclusions**, then the **Abstract** last.

## Notes
- This maps onto the existing LaTeX scaffold: `01_introduction → Ch.1`, add `02_literature.tex` for Ch.2, `02_methods → Ch.3`, `03_results → Ch.4`, `04_conclusion → Ch.5`.
- Keep figures numbered per chapter; every figure/table must be referenced in text before it appears.
- Resolve before/while writing Methods: NaCl feed concentration, autopsy analyses, coupon dimensions, Arm 3 durations (see `open-questions.md`).
