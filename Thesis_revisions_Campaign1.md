# Thesis revisions: adding Campaign 1 (4238A and 4238C) and the statistical analysis

How to use this file. Each change gives the file and section, the **existing text** (trimmed with `…` where it is long), and the **replacement or addition**. Everything is written in LaTeX so you can paste it straight in. Numbers come from `Thesis_Results_Master.xlsx`. Comments starting `% CHECK` mark things only you can confirm.

New citations needed: none. 4238A comes from the same Membrane Works report as 4238C (`MembraneWorks2025Desal`, PRJ4238).

**Six changes matter most:**
1. A third element, 4238A (1st-pass SWC5-LD), from the same desal plant as 4238C.
2. A second experimental campaign (Campaign 1). It contains the IP-without-cleaning arm that the experimental design describes.
3. Fresh coupons at every stage, so the design is independent groups. Statistics are Welch's t-test with 95% CIs.
4. IP behaved differently between campaigns, even though the protocol was identical.
5. 4238A met its specification as a whole element (99.65% rejection) but gave only 78% on the rig. So the gap between element and coupon is a coupon/rig-scale effect, not only 4238C damage. This changes your §4.2 argument.
6. Fixes: the "corner cut" wording, the mine C2 flux typo, untraceable rejection values in Table 4.4, and the "triplicate" claim.

---

## Part A: Chapter 3, Materials and Methods (`03_methods.tex`)

### A1. §3.1 Chemicals and Materials, first paragraph

**Existing:**
```latex
Two Spiral-wound end-of-life (EoL) RO elements were recovered from two full-scale Australian plants with different feed water and service histories (Table~ \ref{tab:membranes-source}). The first, labeled 4238C, was a Hydranautics ESPA2-MAX brackish-water element from the second pass of a seawater desalination plant (desal site). It was retired after \qty{4.5}{years} of service. …
```

**Replace with:**
```latex
Three spiral-wound end-of-life (EoL) RO elements were recovered from two full-scale Australian plants with different feed waters and service histories (Table~\ref{tab:membranes-source}). Two came from a seawater desalination plant (desal site), both retired after \qty{4.5}{years} of service. 4238A was a Hydranautics SWC5-LD seawater element from the first pass. 4238C was a Hydranautics ESPA2-MAX brackish-water element from the second pass. At this site, the second-pass feed is raised to pH~$\approx$~10 to enhance boron removal, and operators reported a progressive loss of boron rejection over service life \citep{MembraneWorks2025Desal}. Unused elements of each model (4238B, SWC5-LD; 4238D, ESPA2-MAX) were examined in the same autopsy and serve as new-membrane references.
```
(Keep your 4297B paragraph as it is. Minor typos there to fix: `\ce{KmnO4}` → `\ce{KMnO4}`, "singe-stage" → "single-stage", "The elements was" → "The element was".)

### A2. Table 3.1 (`tab:membranes-source`)

**Replace the tabular body with:**
```latex
    Label & Site  & Model                  & Type     & Position   & Service \\
    \hline
    4238A & Desal & Hydranautics SWC5-LD   & Seawater & 1st pass   & \qty{4.5}{y} \\
    4238C & Desal & Hydranautics ESPA2-MAX & Brackish & 2nd pass   & \qty{4.5}{y} \\
    4297B & Mine  & Filmtec SW30XLE-440    & Seawater & Single stage & \qty{2.75}{y} \\
```
(Change the column spec to `{|l|l|l|l|l|l|}`.)

### A3. §3.2 Experimental design (replace the first paragraph; keep your flagged paragraph on cleaning levels)

**Existing:**
```latex
Two sets of end-of-life (EoL) membranes were sourced for this study: one from a mine site and one from a desalination plant. Each of the two membranes was tested both with and without cleaning, giving four combinations in total. For each membrane, a coupon of the as-received EoL membrane was first tested to establish baseline performance. The membrane was then processed, where the membrane was cleaned using the protocol described in Section~\ref{sec:cleaning}, and a coupon was taken for testing before IP was performed. The regenerated coupons were compacted and tested again. Each coupon was cut into two pieces to serve as replicates.
```

**Replace with:**
```latex
The experiments were carried out in two campaigns (Table~\ref{tab:campaigns}). Four conditions were defined: as received (no clean, no IP), cleaned (Section~\ref{sec:cleaning}), IP without cleaning, and cleaned + IP (Section~\ref{sec:ip-method}). A fresh coupon was cut from the membrane sheet for every condition, so no coupon was tested more than once across conditions and the conditions are independent groups. Coupons were tested in pairs in the two-cell rig (Section~\ref{sec:rig performance}), and each coupon is one replicate.

Campaign~1 used the two desal-site elements, 4238A and 4238C, and covered all four conditions. The no-clean conditions were run three times on the same coupon pair. The cleaned conditions were run once, because the supply of membrane sheet ran out. Campaign~2 used 4238C and the mine-site element 4297B. It covered the as received, cleaned and cleaned + IP conditions with more coupons per condition (two to seven). An earlier, preliminary IP-without-cleaning test on 4238C is also reported. The IP protocol was identical in both campaigns. All measurements are reported, including single-run conditions. Where only one value exists for a quantity, its standard deviation is not available and is reported as such.

\begin{table}[htbp]
  \centering
  \caption{Experimental campaigns and number of coupons per condition.}
  \label{tab:campaigns}
  \begin{tabular}{llcccc}
    \toprule
    Campaign & Element & As received & Cleaned & IP (no clean) & Cleaned + IP \\
    \midrule
    1 & 4238A (desal, 1st pass) & 2 (3 runs) & 2 (1 run) & 2 (3 runs) & 2 (1 run) \\
    1 & 4238C (desal, 2nd pass) & 2 (3 runs) & 2 (1 run) & 2 (3 runs) & 2 (1 run) \\
    2 & 4238C (desal, 2nd pass) & 4 & 7 & 2\textsuperscript{a} & 4 \\
    2 & 4297B (mine)            & 4 & 6 & --- & 2 \\
    \bottomrule
  \end{tabular}
  \par\smallskip
  \footnotesize \textsuperscript{a}Preliminary test, PWP and rejection only.
\end{table}
```
Also replace "Two sets of … membranes were sourced" with "Three elements" wherever it comes up again (Introduction aim, Abstract).

### A4. §3.3 Fouling characterisation: intro sentence and Table 3.2

**Existing:**
```latex
The condition of each element before cleaning was established via autopsy at Membrane Works Pty Ltd. The two elements were autopsied separately and covered various fields, detailed in Table~\ref{tab:autopsy-coverage}
```
**Replace with:**
```latex
The condition of each element before cleaning was established by autopsy at Membrane Works Pty Ltd. The two desal-site elements (4238A and 4238C) were autopsied together, alongside unused elements of the same models (4238B and 4238D) \citep{MembraneWorks2025Desal}. The mine-site element was autopsied separately \citep{MembraneWorks2026Mine}. The techniques applied are listed in Table~\ref{tab:autopsy-coverage}.
```
**Table 3.2:** add a `4238A` column (`{lccc}`). Its entries are the same as 4238C's: ✓ for visual, standardised flux/rejection, dye test, SEM-EDS, ATR-FTIR, zeta/IEP and contact angle; --- for the rest.

### A5. §3.3 "Performance and dye penetration" paragraph

**Existing:**
```latex
The performance of the 4238C was measured on an in-situ test rig using the manufacturer's conditions of (\qty{1500}{mg.L^{-1}} NaCl, \qty{10.3}{bar}, \qty{25}{\celsius}, \qty{15}{\percent} recovery, pH~7). …
```
**Replace with:**
```latex
The performance of 4238A and 4238C was measured as whole elements on a single-element 8-inch test rig. 4238C was tested at the manufacturer's standard conditions for the ESPA2-MAX (\qty{1500}{mg.L^{-1}} NaCl, \qty{10}{bar}, \qty{25}{\celsius}, \qty{15}{\percent} recovery, pH~7). 4238A was tested at brackish-water conditions (\qty{2000}{mg.L^{-1}} NaCl, \qty{15}{bar}) and the results normalised to the seawater conditions specified for the SWC5-LD \citep{MembraneWorks2025Desal}. Flux and rejection (from conductivity) were compared against the manufacturer's expected values. Coupons of each element were then dye-tested with \qty{10}{mg.L^{-1}} methyl violet under pressure in a static flat-sheet cell, and the permeate side was inspected for dye passage through defects in the PA layer.
```
In the FTIR paragraph, change "Spectra of 4238C were compared against the unused reference element 4238D." to:
```latex
Spectra of 4238A and 4238C were compared against the unused elements of the same model, 4238B and 4238D respectively.
```

### A5b. §3.4 Cleaning protocol: separate the two protocols

**Naming used throughout from now on:** *commercial clean* (Campaign 1, 4238A and 4238C) and *extensive clean* (Campaign 2, 4238C and 4297B). The appendix already uses these names. In the main-text tables below (C, D1, E1), rename the "Cleaned" rows in the same way: "Cleaned" → "Commercial clean" / "Extensive clean", and "Cleaned + IP" → "Commercial clean + IP" / "Extensive clean + IP".

**Existing (§3.4, first line):**
```latex
The EoL membranes were chemically cleaned before IP so that …
```
**Add above it:**
```latex
Two cleaning protocols were used. In Campaign~1, coupons of 4238A and 4238C received a commercial clean (Section~\ref{sec:cleaning-commercial}). In Campaign~2, coupons of 4238C and 4297B received an extensive clean designed for the consolidated fouling expected on EoL elements (Section~\ref{sec:cleaning-extensive}). Results from the two protocols are reported separately and are not pooled.

\subsection{Commercial clean (Campaign 1)}
\label{sec:cleaning-commercial}
% CHECK: describe the commercial protocol here: cleaning chemicals and their concentrations, pH, temperature, contact time, agitation, rinse, and the source of the protocol (manufacturer guideline or the plant's CIP).

\subsection{Extensive clean (Campaign 2)}
\label{sec:cleaning-extensive}
```
Your existing text, from "The EoL membranes were chemically cleaned before IP…" to the final rinse, then sits under the extensive-clean subsection. In its first paragraph, change "modifications were made to the standard protocol" to "the commercial protocol was modified as follows".

In D4 (§4.3.5) and E3 (§4.5), wherever the Campaign 1 results are discussed, change "cleaned" to "commercially cleaned". Add this sentence to §4.5:
```latex
Because the two campaigns used different cleaning protocols, the comparison of IP with and without cleaning (Campaign~1) tests the commercial clean only; the extensive clean was not paired with an uncleaned IP arm.
```

### A6. §3.5 In-situ IP: add one sentence at the end
```latex
The same monomer concentrations, contact times and curing conditions were used for every IP run in both campaigns.
```
% CHECK: also add here anything you can confirm stayed the same or changed between campaigns: MPD solution age, the method and time for drying after MPD, lab humidity, and the TMC batch. Section D2 explains why this matters.

### A7. §3.6 Performance test: three small corrections

| Existing | Replace with |
|---|---|
| `Feed temperature was held at \qty{25}{\degreeCelsius}` | add the missing full stop |
| `Each coupon had PWP measured in triplicate.` | `PWP was measured two to three times on each coupon, and the transmembrane pressure was recorded for each measurement.` |
| `Three repeated readings were taken from each permeate samples and the average was calculated.` | `Three conductivity readings were taken from each permeate sample and averaged. Most coupons had one permeate sample; where a second sample was collected, both are reported.` |

Also: "deionised ater" → "deionised water"; "aconcentration" → "concentration".

In §3.6.4 (B), add after Eq.~\ref{eq:b-methods}:
```latex
Where the water flux during the salt test was measured, it was used directly. Otherwise it was estimated from the PWP as $J_w = A(\Delta P - R\,\Delta\pi_f)$, with the feed osmotic pressure $\pi_f$ estimated from the feed conductivity, assuming NaCl at \qty{25}{\celsius}. Where both values were available, the measured flux was 78--97\,\% of the estimate, so estimated values of $B$ may be up to about \qty{10}{\percent} high. Comparisons between conditions are less affected than absolute values. Because recovery in the coupon cell is negligible, the log-mean correction to the bulk concentration is not needed, and concentration polarisation was neglected.
```

### A8. New section: §3.8 Data treatment and statistical analysis (add before §3.7, "Post-regeneration autopsy")
```latex
\section{Data treatment and statistical analysis}
\label{sec:stats}
Repeat readings on a coupon were first averaged to give a coupon mean. The coupon is the unit of replication. For each element and condition, results are reported as the mean $\pm$ sample standard deviation (SD) of the coupon means, with $n$ the number of coupons. The relative standard deviation (RSD) is used to compare precision between conditions. Where 95\,\% confidence intervals are given, they are $\bar{x} \pm t_{0.975,\,n-1}\,s/\sqrt{n}$. The scatter of repeat readings within a coupon (within-coupon SD) was compared with the scatter between coupons to check that the coupon, not the reading, is the appropriate replicate.

Because fresh coupons were used for every condition, conditions were compared as independent groups using Welch's two-sample $t$-test, which does not assume equal variances. A Mann--Whitney $U$ test was used as a distribution-free check. Each comparison reports the difference in means with its 95\,\% confidence interval and the $p$-value, and differences are described as significant at $\alpha = 0.05$. With $n = 2$ per group the critical $t$ is 12.7 ($n = 4$: 3.2), so only very large effects can reach significance. These comparisons are therefore described as indicative. Suspected outlying coupons were assessed with Grubbs' test ($\alpha = 0.05$, $n \geq 3$). A coupon was excluded only where there was independent physical evidence, and results are then given with and without it. Campaign~1 and Campaign~2 were analysed separately. Data were compiled in Excel, and the statistics were calculated in Python (pandas, SciPy).
```
(Mention the AI-assisted scripts in your acknowledgements, as you did for CEIC8341.)

---

## Part B: Chapter 4, §4.1 Fouling profiles (`04_results_and_discussion.tex`)

### B1. Section intro

**Existing:**
```latex
… Both elements were lightly fouled. 4238C mainly showed damage to the active layer with loss of separation performance while 4297B has light particle and biological fouling, but the polyamide layer was mostly intact.
```
**Replace with:**
```latex
… All three elements were lightly fouled. 4238A, the first-pass desal element, was in good condition and still performed to specification. 4238C, the second-pass desal element, mainly showed damage to the active layer with loss of separation performance. 4297B had light particle and biological fouling, but its polyamide layer was mostly intact.
```

### B2. New subsection, inserted before `\subsection{Desal-site element (4238C)}`
```latex
\subsection{Desal-site first-pass element (4238A)}
\label{sec:res-fouling-4238A}

\paragraph{Deposits.}
4238A was in good condition. A very light brown fouling layer was visible only when the membrane was wiped, the membrane had a yellow-to-pink colour that did not wipe off, and there was a slight odour. The brine seal and permeate tube were clean, there was no sign of delamination or backpressure damage, and the permeate side was clean. The fibreglass at the lead end was separating from the anti-telescoping device, which Membrane Works attributed to manufacture and did not expect to affect performance \citep{MembraneWorks2025Desal}.

SEM-EDS found iron mixed with aluminosilicate (clay) particles, up to about 13 at.\% Fe, 12 at.\% Si and 11 at.\% Al. Regions without deposits showed mainly C, O and S from the polysulfone support. The FTIR spectra of used 4238A and new 4238B were very similar.

\paragraph{Active-layer condition.}
4238A still met its specification as an element: normalised flux was \qty{26.6}{LMH} against \qty{22.1}{LMH} expected, and salt rejection was \qty{99.65}{\percent} against \qty{99.68}{\percent} expected \citep{MembraneWorks2025Desal}. In the dye test it showed only minor pinholing along the lines of brine-spacer contact, similar to the new elements, with \qty{91}{\percent} rejection in the dye cell. Its contact angle (\qty{25.1}{\degree} against \qty{44.2}{\degree} for new 4238B) and zeta potential at pH~7 (\qty{-30}{mV} against \qty{-8}{mV}) were both different from the new element. Membrane Works attributed the lower contact angle to adsorbed organic or biological material. The new 4238B was itself stained, however, so its values may not represent a typical new membrane \citep{MembraneWorks2025Desal}.
```

### B3. In the 4238C dye-test paragraph

**Existing:** `Of the four desalination site membranes tested, 4238C let the most dye through, …`
**Add after the sentence on permeate conductivity:**
```latex
By comparison, the used first-pass element 4238A showed low dye penetration, similar to both new elements (\qty{91}{\percent} rejection in the dye cell).
```

### B4. Table 4.1 (`tab:fouling-profiles`): add a 4238A column
Use `p{2.6cm}p{3.8cm}p{3.8cm}p{3.8cm}` and add the column after the label:
```latex
& 4238A (desal, 1st pass) & 4238C (desal, 2nd pass) & 4297B (mine) \\
Service & \qty{4.5}{y}; 1st pass SWRO & … & … \\
Visual deposit & Very light brown, visible only on wiping; yellow--pink colour & … & … \\
Dominant deposits (SEM-EDS) & Fe oxide with aluminosilicate clay & … & … \\
Extractable loading & --- & --- & … \\
Biological activity & Not assessed & … & … \\
Physical damage & None; low dye passage & … & … \\
Chemical change & FTIR unchanged; IEP 3.96\,$\to$\,3.27; $\zeta_{\mathrm{pH\,7}}$ \qty{-8}{}\,$\to$\,\qty{-30}{mV}; contact angle \qty{44.2}{}\,$\to$\,\qty{25.1}{\degree}\textsuperscript{a} & … & … \\
As-received performance & \qty{26.6}{LMH}, \qty{99.65}{\percent} (expected \qty{22.1}{LMH}, \qty{99.68}{\percent}) & … & … \\
```
Footnote `a`: "Reference 4238B was stained; its values may not represent a typical new membrane." Also remove the `\flag{AI GENERATED SUMMARY TABLE-- CHECK}` once you have checked it.

### B5. "Comparison of both EoL membranes"
Rename to `\subsection{Comparison of the EoL membranes}` and add as a first sentence:
```latex
4238A gives a within-plant control for 4238C: both came from the same plant and served the same \qty{4.5}{years}, but 4238A sat in the first pass at neutral pH and showed light fouling with no loss of performance. The damage to 4238C therefore cannot be attributed to the age of the plant or the plant's feed water alone. It is more likely linked to its second-pass duty, including the pH~10 feed.
```

---

## Part C: §4.2 Performance of the as-received membranes

### C1. Replace Table 4.2 (`tab:baseline`)
```latex
  \begin{table}[htbp]
  \centering
  \caption{Performance of the as-received membranes (no clean, no IP). Mean $\pm$ SD across coupons.}
  \label{tab:baseline}
    \begin{tabular}{llcccc}
    \toprule
    Campaign & Membrane & Flux (\unit{LMH}) & PWP (\unit{LMH.bar^{-1}}) & NaCl rejection (\%) & $n$ \\
    \midrule
    1 & 4238A (desal, 1st pass) & $1.23 \pm 0.27$ & $0.082 \pm 0.018$ & $78.1 \pm 2.8$ & 2 \\
    1 & 4238C (desal, 2nd pass) & $0.56 \pm 0.08$ & $0.038 \pm 0.006$ & not measured & 2 \\
    2 & 4238C (desal, 2nd pass) & $3.21 \pm 0.32$ & $0.208 \pm 0.011$ & $76.6 \pm 3.1$ & 4 \\
    2 & 4297B (mine)            & $5.22 \pm 1.00$ & $0.330 \pm 0.062$ & $81.9 \pm 8.6$ & 4 \\
    \bottomrule
  \end{tabular}
  \par\smallskip
  \footnotesize $n$ = number of coupons. Flux and PWP at \qtyrange{14}{16}{bar}; rejection with $\sim$\qty{2000}{mg.L^{-1}} NaCl (\qtyrange{3800}{4000}{\micro S.cm^{-1}}).
  \end{table}
```
Note: two values change from your current table. Mine flux 5.24 → 5.22 is a transcription fix (§F2). Desal rejection 76.5 ± 3.6 → 76.6 ± 3.1 because the run-sheet data are used (§F3).

### C2. Add after the table
```latex
In Campaign~2, PWP was higher for the mine-site element than for 4238C (0.330 against \qty{0.208}{LMH.bar^{-1}}; Welch's $t$-test, $p = 0.028$), while rejection did not differ significantly (81.9 against \qty{76.6}{\percent}, $p = 0.31$). The as-received PWP of 4238C differed by a factor of about five between campaigns (0.038 against \qty{0.208}{LMH.bar^{-1}}), although both sets of coupons came from the same element. Within each campaign the spread between coupons was small (RSD 15\,\% and 5\,\%). The difference therefore lies between regions of the membrane sheet sampled in each campaign, not in the measurement itself. This is discussed below.
```

### C3. §4.2.1 "Comparison with element test": add a paragraph for 4238A
```latex
4238A provides a useful check because it still met its specification as an element (\qty{99.65}{\percent} rejection; Section~\ref{sec:res-fouling-4238A}). Its coupons nevertheless gave a PWP of only \qty{0.082}{LMH.bar^{-1}} and a rejection of \qty{78.1}{\percent}, which is 21 percentage points below the element test. This gap is the same as for the damaged 4238C (about 21~pp). The difference between coupon and element performance therefore cannot be explained by the damage to 4238C alone.
```

### C4. §4.2.2 "Why coupon results differ": replace from "A 76.5\% rejection measured here would consistent with…" to the end
**Existing (end of section):**
```latex
… A 76.5\% rejection measured here would consistent with the laboratory's small-area result. Additionally, smaller samples are more sensitive to local defects \flag{…}. Moreover, … Considering the massive difference in membrane flux between element and coupon,
```
**Replace with:**
```latex
4238A shows that this explanation is incomplete. It performed to specification as an element (\qty{99.65}{\percent}) and in the dye cell (\qty{91}{\percent}), yet gave \qty{78.1}{\percent} on the rig, essentially the same as damaged 4238C (\qty{76.6}{\percent}). Coupon PWP was likewise 15 to 35 times lower than the corresponding element values for all three membranes. A gap of similar size for a healthy and a damaged membrane points to an effect of coupon scale or the rig, applied on top of any real differences between membranes. Three mechanisms are likely to contribute:
\begin{itemize}
  \item \textbf{Flux dependence of observed rejection.} At constant salt permeability, observed rejection $R = J_w/(J_w + B)$ falls as water flux falls. Coupon fluxes of \qtyrange{0.5}{6}{LMH} are an order of magnitude below element fluxes, so much lower observed rejection is expected even for an intact layer.
  \item \textbf{Salt bypass independent of flux,} through cut edges, the O-ring seal or local defects. A small coupon area (\qty{0.0139}{m^2}) makes any such leak a large fraction of the permeate.
  \item \textbf{Local heterogeneity.} The five-fold difference in as-received 4238C PWP between campaigns shows that small coupons sample local variation that is averaged out over a \qty{37}{}--\qty{41}{m^2} element.
\end{itemize}
Because this offset applies to every condition tested on the rig, comparisons between conditions within a campaign remain valid, but absolute values should not be compared with element or datasheet values. % CHECK: if you have a rig run on a new flat-sheet coupon (e.g. 4238B/D), cite it here as the rig control; otherwise list it in future work.
```

---

## Part D: §4.3 Cleaning outcomes

### D1. §4.3.4 Performance after cleaning: replace Table 4.3 (`tab:clean-compare`)
```latex
\begin{table}[htbp]
  \centering
  \caption{As-received versus extensively cleaned coupons (no IP). Mean $\pm$ SD across coupons; change with Welch's $t$-test $p$-value.}
  \label{tab:clean-compare}
  \small
  \begin{tabular}{lllccc c}
    \toprule
    Campaign & Membrane & Condition & Flux (\unit{LMH}) & PWP (\unit{LMH.bar^{-1}}) & Rejection (\%) & $n$ \\
    \midrule
    1 & 4238A & As received & $1.23 \pm 0.27$ & $0.082 \pm 0.018$ & $78.1 \pm 2.8$ & 2 \\
      &       & Cleaned     & $2.81 \pm 1.02$ & $0.198 \pm 0.072$ & $86.9 \pm 9.2$ & 2 \\
      &       & Change ($p$) & & $+142\%$ (0.25) & $+8.8$\,pp (0.39) & \\
    \midrule
    1 & 4238C & As received & $0.56 \pm 0.08$ & $0.038 \pm 0.006$ & not measured & 2 \\
      &       & Cleaned     & $13.10 \pm 0.35$ & $0.922 \pm 0.025$ & $96.2 \pm 1.1$ & 2 \\
      &       & Change ($p$) & & $\times 24$ (0.009) & --- & \\
    \midrule
    2 & 4238C & As received & $3.21 \pm 0.32$ & $0.208 \pm 0.011$ & $76.6 \pm 3.1$ & 4 \\
      &       & Cleaned, all & $4.55 \pm 4.42$ & $0.295 \pm 0.290$ & $79.7 \pm 9.7$ & 7 \\
      &       & Change ($p$) & & $+42\%$ (0.46) & $+3.1$\,pp (0.46) & \\
      &       & Cleaned, excl.\ C5--C6 & $2.04 \pm 1.16$ & $0.130 \pm 0.077$ & $84.3 \pm 6.9$ & 5 \\
      &       & Change ($p$) & & $-37\%$ (0.086) & $+7.7$\,pp (0.069) & \\
    \midrule
    2 & 4297B & As received & $5.22 \pm 1.00$ & $0.330 \pm 0.062$ & $81.9 \pm 8.6$ & 4 \\
      &       & Cleaned     & $5.60 \pm 1.41$ & $0.359 \pm 0.073$ & $80.5 \pm 11.6$ & 6 \\
      &       & Change ($p$) & & $+9\%$ (0.52) & $-1.4$\,pp (0.83) & \\
    \bottomrule
  \end{tabular}
  \par\smallskip
  \footnotesize Flux and PWP at \qtyrange{14}{16}{bar}; rejection with $\sim$\qty{2000}{mg.L^{-1}} NaCl. Campaign~1 cleaned conditions were tested in a single run (two coupons, one rejection reading each).
\end{table}
```

### D2. C5/C6 paragraph: add one sentence after "These two coupons should not be treated as measurment outliers."
```latex
Grubbs' test confirms this: neither coupon is a statistical outlier among the seven ($G = 1.63$ against $G_{\mathrm{crit}} = 2.02$ at $\alpha = 0.05$). Their exclusion is therefore justified on physical grounds, namely the high-flux, low-rejection signature of defects and the pinholes seen in the autopsy, not on statistical grounds, and results are reported with and without them.
```
In the next paragraph, change `rejection of 84.1 $\pm$ \qty{6.5}{\percent}` to `84.3 $\pm$ \qty{6.9}{\percent}` (see §F3).

### D3. Table 4.4 (`tab:clean-desal-coupons`): rejection column
| Coupon | Existing | Run-sheet value |
|---|---|---|
| C3 | 92.4 | 93.2 |
| C4 | 89.3 | 89.9 |
| Bottom rows | 84.1 ± 6.5 / 79.6 ± 9.4 | 84.3 ± 6.9 / 79.7 ± 9.7 |

% CHECK §F3 before changing these. Also C6 PWP: existing 0.713, data give 0.768. Use 0.768.

### D4. §4.3.5 Comparison with the as-received membranes: replace the whole subsection body (including both `\flag`s)
```latex
For 4297B, the extensive clean made no significant difference: PWP rose by \qty{9}{\percent} ($p = 0.52$) and rejection fell by \qty{1.4}{pp} ($p = 0.83$), both well within the spread between coupons. This agrees with the low extractable loading found in the autopsy and with the iron oxide and silica that HCl and NaOH were not expected to remove (Section~\ref{sec:res-cleaning}).

For 4238C in Campaign~2, the result depends on whether C5 and C6 are included. With all seven coupons, PWP rose by \qty{42}{\percent} ($p = 0.46$). Without them, PWP fell by \qty{37}{\percent} ($p = 0.086$) and rejection rose by \qty{7.7}{pp} ($p = 0.069$). Neither direction is significant at $\alpha = 0.05$. The trend without C5 and C6, lower permeability with higher rejection, is consistent with the acid step tightening the polyamide layer. It is not consistent with removal of foulant, of which the autopsy found little.

Campaign~1 gave a different picture. Cleaned 4238C coupons reached a PWP of \qty{0.92}{LMH.bar^{-1}}, 24 times their as-received value ($p = 0.009$), with \qty{96.2}{\percent} rejection, the highest measured in this work. Cleaned 4238A coupons also trended towards higher PWP (+\qty{142}{\percent}) and rejection (+\qty{8.8}{pp}), though with $n = 2$ neither change was significant. A higher PWP together with higher rejection cannot be explained by defects being opened up. The likely explanation is that the as-received Campaign~1 coupons had unusually low permeability (\qty{0.038}{LMH.bar^{-1}}, five times below Campaign~2), so cleaning restored part of a permeability that had been lost to deposits or compaction. These Campaign~1 cleaned results rest on a single run of two coupons with one rejection reading each, so they are treated as indicative.
```
% CHECK: does your lab book record anything different about the Campaign 1 as-received coupons, such as where on the leaf they were cut or their storage time? If so, add it here.

---

## Part E: §4.4 Regeneration by IP and §4.5 Effect of cleaning on regeneration

### E1. Replace Table 4.5 (`tab:ip-results`). The current version repeats the baseline rows under an IP caption.
```latex
  \begin{table}[htbp]
  \centering
  \caption{Performance after IP, with and without prior cleaning. Mean $\pm$ SD across coupons; $n$ = number of coupons.}
  \label{tab:ip-results}
  \small
    \begin{tabular}{lllcccc}
    \toprule
    Campaign & Membrane & Condition & Flux (\unit{LMH}) & PWP (\unit{LMH.bar^{-1}}) & NaCl rejection (\%) & $n$ \\
    \midrule
    1 & 4238A & IP (no clean)  & $2.00 \pm 0.44$ & $0.138 \pm 0.030$ & $85.6 \pm 0.8$ & 2 \\
      &       & Cleaned + IP   & $1.32 \pm 0.17$ & $0.093 \pm 0.012$ & $87.1 \pm 0.7$ & 2 \\
    1 & 4238C & IP (no clean)  & $0.95 \pm 0.16$ & $0.061 \pm 0.010$ & $86.9 \pm 0.5$ & 2 \\
      &       & Cleaned + IP   & $7.51 \pm 2.30$ & $0.514 \pm 0.157$ & $91.1 \pm 3.6$ & 2 \\
    \midrule
    2 & 4238C & IP (no clean)\textsuperscript{a} & $4.92 \pm 2.77$ & $0.337 \pm 0.190$ & $80.9 \pm 9.2$ & 2 \\
      &       & Cleaned + IP   & $0.35 \pm 0.20$ & $0.023 \pm 0.013$ & $76.2 \pm 7.9$ & 4 \\
    2 & 4297B & Cleaned + IP   & $0.69 \pm 0.19$ & $0.046 \pm 0.012$ & $80.5 \pm 11.1$ & 2 \\
    \bottomrule
  \end{tabular}
  \par\smallskip
  \footnotesize \textsuperscript{a}Preliminary test. Flux and PWP at \qtyrange{14}{16}{bar}; rejection with $\sim$\qty{2000}{mg.L^{-1}} NaCl. In Campaign~1, IP (no clean) 4238C rejection is from a single run.
  \end{table}
```

### E2. New text under §4.4.1 "Performance after IP"
```latex
IP had opposite effects in the two campaigns (Table~\ref{tab:ip-results}), even though the protocol was identical.

In Campaign~2, IP cut permeability sharply on both elements without improving rejection. For 4297B, PWP fell by \qty{87}{\percent} relative to the cleaned coupons ($p = 0.0001$), while rejection was unchanged (80.5 against \qty{80.5}{\percent}, $p > 0.99$). For 4238C, PWP fell by \qty{89}{\percent} relative to as received ($p < 0.0001$), and by \qty{82}{\percent} relative to cleaned excluding C5--C6 ($p = 0.034$). Rejection was again unchanged relative to as received (76.2 against \qty{76.6}{\percent}, $p = 0.92$). Because rejection stayed constant while water permeability fell tenfold, the apparent salt permeability $B$ must have fallen by the same factor (\qty{-90}{\percent}, $p = 0.0001$ for 4238C). In other words, the new layer added a resistance in series to both water and salt transport without improving the membrane's selectivity. This is consistent with a thick or dense polyamide film formed over the substrate, while salt still passes through pathways that the new film did not seal.

In Campaign~1, IP did not reduce permeability and was associated with higher rejection. On 4238A, IP without cleaning raised rejection from 78.1 to \qty{85.6}{\percent} ($+7.5$~pp, $p = 0.14$), and PWP did not fall (0.082 to \qty{0.138}{LMH.bar^{-1}}, $p = 0.19$). Cleaned + IP 4238A reached \qty{87.1}{\percent}. All Campaign~1 IP coupons gave 85--\qty{91}{\percent} rejection, above every as-received coupon in either campaign. With $n = 2$, none of these changes is significant on its own, but their direction is consistent across both elements and both cleaning arms.

The difference between campaigns cannot come from the IP recipe, which was the same. Possible causes are variables the protocol did not control: the age of the MPD solution, how long and by what method the membrane was dried between the MPD and TMC steps (which controls how much MPD is left at the interface), ambient humidity (TMC hydrolyses in contact with moisture), and the state of the substrate itself, since the as-received Campaign~1 coupons were five times less permeable. % CHECK: add whatever your lab notes show differed between the campaign 1 and 2 IP runs. If nothing was recorded, say that these variables were not controlled and list them in Limitations.
```

### E3. §4.5 Effect of cleaning on regeneration: replace the bullet placeholder
```latex
Campaign~1 provides the direct test of whether the substrate must be cleaned before IP, because it is the only campaign with both IP arms on the same elements. For 4238A, cleaning before IP gave slightly higher rejection (87.1 against \qty{85.6}{\percent}, $p = 0.18$) and a lower PWP (0.093 against \qty{0.138}{LMH.bar^{-1}}, $-32\%$, $p = 0.26$), so the apparent salt permeability fell by about \qty{42}{\percent} ($p = 0.15$). For 4238C, cleaning before IP gave higher rejection (91.1 against \qty{86.9}{\percent}, $p = 0.34$) and a much higher PWP (0.514 against \qty{0.061}{LMH.bar^{-1}}, $p = 0.15$).

For both elements, therefore, cleaning before IP produced a regenerated membrane with equal or better rejection, which is the direction expected if residual foulant hinders the formation of a continuous polyamide film (Section~\ref{sec:fouling-ip}). The uncleaned arm did not, however, produce the defective, high-permeability, low-rejection film anticipated in Section~\ref{sec:fouling-ip}. Uncleaned IP coupons were tight (0.06--\qty{0.14}{LMH.bar^{-1}}) and gave 85--\qty{87}{\percent} rejection with the smallest spread between coupons of any condition (SD 0.5--0.8~pp). The effect of cleaning on regeneration is therefore smaller than expected for these lightly fouled desal elements, which is consistent with their autopsies (Section~\ref{sec:res-fouling}).

With two coupons per arm, a difference in rejection would need to exceed roughly 10~pp to reach significance at $\alpha = 0.05$. The observed differences of 1.5--4~pp are below this. None of the regenerated coupons approached commercial RO rejection (\qty{99.5}{\percent} and above), so on these substrates IP improved rejection by up to about 10~pp but did not restore RO-grade performance.
```
% CHECK the 10 pp figure if you change the analysis. It comes from $t_{0.975,1}\sqrt{s_1^2/2+s_2^2/2}$ with SD ≈ 0.7–0.8, which gives about 13 pp. "Roughly 10 pp" is a fair round number; give "about 13 pp" if you want to be exact.

### E4. §4.8 Limitations: replace the bullets with prose
```latex
The main limitation is the number of replicates. Campaign~1 has two coupons per condition, and its cleaned conditions come from a single run with one rejection reading per coupon, so most Campaign~1 comparisons are indicative only. All measurements are nevertheless reported (Appendix~\ref{app:exp-data}).

Second, the difference between coupon-scale and element-scale performance (Section~\ref{sec:res-baseline}) means absolute values cannot be compared with datasheet or element values. No new commercial membrane was run on the rig as a control. % CHECK
Third, the spread between coupons from the same element was large: as-received 4238C PWP differed five-fold between campaigns, and one condition had an RSD of up to \qty{98}{\percent}. This limits how far differences between elements can be generalised.

Fourth, IP responded differently between campaigns under an identical recipe, which points to process variables that were not controlled: MPD solution age, drying between the MPD and TMC steps, and humidity.

Finally, the apparent salt permeability $B$ uses an estimated salt-test flux for most coupons (Section~\ref{sec:stats}), and the work was done at coupon scale over short test durations.
```

---

## Part F: Corrections to existing content

### F1. "Corner cut" footnotes (Appendix, mine IP tables, both instances)
**Existing:** `\textsuperscript{a}Coupon corner cut during handling.`
**Replace with:** `\textsuperscript{a}Corner cut as a coupon identification marker.` Or delete the footnote and the superscript entirely. Remove the same note from any desal IP rows that carry it.

### F2. Mine as-received C2 flux (only matters if you rebuild tables from `Results Summary (2)`)
In the workbook, the third reading for C2 is 5.0288 (copied from C1). The correct value is 4.7698, which gives a C2 mean of 4.96 LMH and a condition mean of 5.22 LMH, not 5.24. Your appendix PWP table already shows 4.77, which is correct. Update: Table 4.2 (done in C1), Table 4.3 (done in D1), and the text "Flux rose by 6.7%" → "+7.2%" if you quote flux.

### F3. Rejection values that can't be traced to the run sheets
`Results Summary (2)` contains a second rejection value for several coupons that is not in the Mine Site and Desal Site run sheets:

| Coupon | Summary sheet | Run sheet |
|---|---|---|
| Desal cleaned C3 | 93.2, 91.5 | 93.19 only (91.5 is the left/right average, O56) |
| Desal cleaned C4 | 89.9, 88.7 | 89.88 only |
| Desal as received C1–C4 | two values each | one value each |
| Mine as received C1–C4 | two values each | one value each |

% CHECK your lab book. If these second readings are real measurements, add their raw conductivities to the run sheets and the appendix. If not, use the single run-sheet values, which all the numbers in this file already do.

### F4. Other `\flag`s these changes resolve
- §4.3.5 "Welch's t-test?": resolved by D4.
- §4.4: the comment `% PWP and rejection … compared with same coupons before` should read "compared with as-received and cleaned coupons (fresh coupons for each condition)".

---

## Part G: Appendix (`01_appendix_experimental_data.tex`)

1. Replace `01_appendix_experimental_data.tex` with **`01_appendix_experimental_data_v2.tex`** (supplied). It covers all four element/campaign sets. Each has a coupon table (coupon means, within-coupon SD, and condition mean ± SD with n), a raw PWP table and a raw rejection table. It also includes the preliminary IP (no clean) test, and footnotes the two-pass series runs as excluded. Point the `\input` in `00_appendix_a.tex` to the new file, or rename it.
2. Add `\usepackage{longtable}` to `main.tex` (the long PWP tables break across pages).
3. Optional: add the statistical tables (Welch's tests, Grubbs, repeatability) as a short `\subsection{Statistical analysis}`, or point to the supplementary workbook.

---

## Part H: Conclusions (`05_conclusion_and_future_work.tex`), draft findings
```latex
\begin{itemize}
  \item In-situ IP on EoL substrates raised coupon rejection by up to about 10~pp (78.1 to \qty{87.1}{\percent} for 4238A) but did not restore RO-grade rejection on any element.
  \item The IP outcome varied between campaigns under an identical recipe. Campaign~2 IP reduced PWP by 87--\qty{89}{\percent} with no change in rejection, showing that the new layer added resistance without adding selectivity. This identifies uncontrolled process variables as the main barrier to reproducible regeneration.
  \item Cleaning before IP gave equal or better rejection than IP alone on both desal elements (+1.5 and +4.2~pp), but the uncleaned film was not defective, and with $n = 2$ the effect was not significant.
  \item Extensive cleaning alone produced no significant change on the mine-site or Campaign~2 desal coupons, consistent with lightly fouled elements whose remaining deposits (iron oxide, silica) resist HCl and NaOH.
  \item Coupon tests underestimated element rejection by about 21~pp for both a healthy (4238A) and a damaged (4238C) element, so results at coupon scale are valid as comparisons within a campaign only.
\end{itemize}
```
Future work, add as the first item: *a rig control using new commercial flat-sheet membrane, and tighter control of the time between MPD and TMC steps, MPD solution age and humidity during IP.*
