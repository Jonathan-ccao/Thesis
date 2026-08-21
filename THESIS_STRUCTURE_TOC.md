# Thesis Structure — Table of Contents & Word Budget

**Thesis:** *Uplifting End-of-Life RO Membranes via Polyamide Regeneration*
**Author:** Jonathan Cao · UNSW Chemical Engineering Honours
**Supervisor:** Prof. Pierre Le-Clech · Co-supervisor: John Ogbe

Status key: `[ ]` not started · `[~]` drafting · `[x]` done

---

## Word budget

Target **20,000 words** — midpoint of the 15,000–25,000 bracket, and consistent with a 50–70 pp body. Planning figure: **350 words per page** (12pt Times, A4, 30 mm margins, 1.5 spacing). Check this against your own pages once you have three or four written.

| Chapter | Bracket | Chosen | Words | ≈ Pages |
|---|---|---|---|---|
| 1 Introduction | 3–10% | 7% | 1,400 | 4 |
| 2 Literature Review | 8–30% | **21%** | **4,150** | **12** |
| 3 Methods | 8–20% | 14% | 2,800 | 8 |
| 4 Results & Discussion | 15–60% | 42% | 8,400 | 24 |
| 5 Conclusions | 1% | 2% | 400 | 1 |
| References | 2% | 2% | 400 | — |
| | | | **17,550** | **49** |

Discussion sits at 0% because it is folded into Chapter 4 — that is what lets Results run at 42%. The total leaves ~2,400 words of headroom; spend it in Chapter 4 as the data warrants, not in Chapter 2.

**Chapter 2 is at the upper-middle of its bracket**, justified because the fouling→IP argument is the novelty. It is a ceiling, not a target.

### Two things that buy the most words back

1. **Tables, not prose.** The prior-work comparison (§2.6.1) and the EoL routes comparison (§2.5) are tables in the current scaffold. A six-row table does in ~150 words what 800 words of prose does worse. The prior-work table earns its place twice over because a "substrate condition: fouled / pristine" column makes your gap visible at a glance.
2. **Delete the explainer sentences before submission.** The one-liner under each heading is scaffolding — roughly 450 words across Chapter 2 alone.

---

## Chapter 1 — Introduction *(1,400 w · ~4 pp)*
Funnel: water context → membrane waste → the gap → the aim.

- [ ] **1.1 Background & motivation** *(prose exists)* — 400 w
- [ ] **1.2 Problem statement** — 250 w · ⚠️ *see note below on merging this into 1.1*
- [ ] **1.3 Research aim** — one sentence, unjustified, no citations — 100 w
- [ ] **1.4 Objectives** — 5 numbered — 150 w
- [ ] **1.5 Scope & limitations** — 300 w · ⚠️ fouling profiling now IN scope
- [ ] **1.6 Thesis outline** — 200 w

> **Open question you raised:** whether to keep a headed "Problem statement" at all. The case for merging it into 1.1 is that the problem lands harder in prose that builds to it. Keep the **Aim** and **Objectives** headings regardless — those are navigation, and an examiner will flip to find them.

---

## Chapter 2 — Literature Review *(4,150 w · ~12 pp)*

**Design change (Aug 2026):** three cleaning arms collapsed to two — no clean vs extensive clean. §2.4.3, §3.2, §4.6 and the Ch. 1 objectives all reflect the binary design. An optional one-sentence acknowledgement of the earlier intermediate-cleaning runs sits commented out in §3.2 of `03_methods.tex`; see the note there before deciding.

**Restructured Aug 2026** — collapsed from 8 sections / 30 subsections to 7 / 15. At 4,150 words the old structure gave each subsection ~140 words, which reads as a checklist rather than an argument.

### 2.1 The end-of-life RO membrane problem — **350 w**
- [ ] One continuous section, no subsections. Scale of the waste stream *(prose exists)*, then one paragraph on disposal routes, environmental persistence and the value objection.
  > Do not expand into LCA, waste policy, or disposal regulation. Establishing the concern is enough.

### 2.2 Thin-film composite RO membranes — **650 w**
- [ ] **2.2.1** Architecture and layer functions — 150 w *(prose exists)* · a labelled cross-section figure replaces ~200 words
- [ ] **2.2.2** Polyamide formation by interfacial polymerisation — 250 w
- [ ] **2.2.3** The PSF substrate and its control over film formation — 250 w
  > 2.2.3 is the pivot of the chapter. Do not compress further.

### 2.3 Ageing and fouling of RO membranes — **550 w**
- [ ] **2.3.1** Chemical and mechanical degradation — 275 w *(merged from three former subsections)*
- [ ] **2.3.2** Fouling classes and the fouling–cleaning cycle — 275 w · four foulant classes at roughly a sentence each
  > The EoL performance signature (PWP, rejection, LRV, TMP) goes in the Ch. 4 baseline table, not in prose here.

### 2.4 Fouling as a constraint on regeneration — **1,150 w** ← *largest section, protected*
- [ ] **2.4.1** What cleaning removes and what it leaves behind — 300 w · *justifies the two levels*
- [ ] **2.4.2** Residual foulants as a barrier to IP — 400 w · **the most important block in the chapter**; five mechanisms, then the expected experimental signatures
- [ ] **2.4.3** Substrate preparation as a precondition for regeneration — 250 w · *your specific question, now binary: is cleaning necessary, and is a standard clean sufficient?*
- [ ] **2.4.4** Characterising fouling profiles — 200 w, or 120 w plus a small table

### 2.5 End-of-life management routes — **450 w** ← *largest single cut, was 3–4 pp*
- [ ] **Comparison table** — reuse / mechanical / solvent / downcycling × principle, product, performance, limitation
- [ ] **2.5.1** Reuse and material recovery — 120 w for both
- [ ] **2.5.2** Chemical downcycling to NF and UF — 200 w · *framing 1: competing endpoint*
- [ ] **2.5.3** Why current routes are insufficient — 130 w · the pivot

### 2.6 Polyamide regeneration — **750 w** ← *protected; merged from former §2.6 + §2.7*
- [ ] **2.6.1** Concept and prior work — 250 w *(one sentence of prose exists)* + **the prior-work table**
- [ ] **2.6.2** Stripping PA without destroying the substrate — 250 w · *framing 2: same chemistry as §2.5.2, now as a process step*
- [ ] **2.6.3** Re-forming PA on a recovered substrate — 250 w
  > **Cut entirely:** the sustainability / techno-economic outlook. Out of experimental scope — one line in Ch. 5 instead.

### 2.7 Research gaps and how this thesis responds — **250 w**
- [ ] Gap 1 — regeneration demonstrated on pristine substrates; real fouling uncharacterised
- [ ] Gap 2 — cleaning treated as fixed pre-treatment; whether it is necessary at all, or sufficient, is unestablished
- [ ] Gap 3 — fouling profile and outcome rarely measured on the same membrane
- [ ] Map each to a numbered objective from §1.4. No new literature.

---

## Chapter 3 — Materials & Methods *(2,800 w · ~8 pp)*
Ordered as the work was performed. ~280 w per section.

- [ ] **3.1 Materials** · **3.2 Experimental design** — **2 membranes × 2 arms = 4 conditions** (no clean / extensive clean); justify the wide level separation against §2.4.1
- [ ] **3.3 Fouling characterisation of as-received membranes** — **NEW**
- [ ] **3.4 Cleaning protocols** · **3.5 In-situ IP** · **3.6 Rig and compaction**
- [ ] **3.7 Performance characterisation** (3.7.1 PWP, 3.7.2 rejection)
- [ ] **3.8 Post-regeneration autopsy** — same techniques as 3.3 so before/after compare directly
- [ ] **3.9 Safety** · **3.10 Deviations from protocol**

---

## Chapter 4 — Results & Discussion *(8,400 w · ~24 pp)*
The largest chapter by design. Sequence follows the causal chain, not the lab calendar. ~760 w per section.

- [ ] **4.1 Fouling profiles of as-received membranes** — **NEW**; everything later is conditioned on this
- [ ] **4.2 Cleaning outcomes** — did the extensive clean visibly strip the fouling layer, or leave the predicted residuals?
- [ ] **4.3 PWP** — 4238C 0.92 → 0.52 LMH/bar
- [ ] **4.4 Salt rejection** — treat replicate scatter as data
- [ ] **4.5 Permeability–rejection trade-off** — the headline plot
- [ ] **4.6 Effect of cleaning** — Arm 1 (no clean) vs Arm 2 (extensive); necessity and sufficiency are separate claims
- [ ] **4.7 Membrane A vs C** — does fouling profile predict outcome better than cleaning?
- [ ] **4.8 Autopsy findings** — pair a high- and a low-performing coupon
- [ ] **4.9 Discussion synthesis** — answer each gap from §2.7 explicitly
- [ ] **4.10 Limitations** · **4.11 Summary tables**

---

## Chapter 5 — Conclusions & Future Work *(400 w · ~1 pp)*
- [ ] **5.1 Conclusions** — answer §1.3 directly; no new data
- [ ] **5.2 Future work** — ordered by how much each would change the conclusion; include the techno-economic line cut from §2.6

---

## Back Matter
- [ ] References · Appendix A raw data · B SOP · C risk assessment · D calibration and spectra

---

## Writing order
1. **Ch. 3 Methods** — including new §3.3, while procedures are fresh
2. **Ch. 2 §2.4** — longest lead time; needs new reading
3. **Ch. 2 §2.6** — regeneration
4. **Ch. 2 §2.1–2.3, §2.5** — largely assembly
5. **Ch. 4**, then **Ch. 1**, then **Ch. 5**, then the **Abstract**

## Notes
- **Citations:** `\citep{}` throughout. The old `(\cite{})` produced double parentheses under natbib author-year.
- **Labels:** every section has one. `ch:Results and Discussion` → `ch:results`; `ch:conclusion_and_future_work` → `ch:conclusion`; `sec:regeneration-detail` → `sec:cleaning-intensity`.
- **Biggest reading gap:** `references.bib` has 9 entries and almost nothing on fouling mechanisms or cleaning efficiency. `Molinaa2018` is the only one touching fouling characterisation on EoL elements. §2.4 is 28% of the chapter and has the thinnest source base.
- Every figure/table referenced in text before it appears.
- Still to resolve: NaCl feed concentration, final autopsy technique list, coupon dimensions, extensive-clean duration.
