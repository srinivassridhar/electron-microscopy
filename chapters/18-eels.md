# Chapter 18 — Electron Energy Loss Spectroscopy (EELS)

> **STUB CHAPTER** — No dedicated source lecture for EELS exists in the course materials (weeks 1–15 reviewed). This chapter is drafted from the outline scope plus standard textbook material. Every technical claim should be considered provisional and verified against Egerton's *Electron Energy-Loss Spectroscopy in the Electron Microscope* (Springer, current edition) or equivalent reference before publication. Marked content with [verify] is especially provisional.

## Title options

1. **Reading the Inelastic Loss: EELS in the TEM**
2. **From Plasmon to Core-Loss: What an EELS Spectrum Says**
3. **The Analytical Companion to HAADF: EELS at Atomic Resolution**

## TL;DR

Electron energy-loss spectroscopy measures the energy lost by beam electrons as they traverse the specimen, producing a spectrum from which elemental composition, chemical bonding state, thickness, and electronic structure can be read. EELS is most powerful in STEM mode at near-atomic spatial resolution, complementary to EDS in light-element sensitivity and chemical-state information.

---

## 1. Chapter Opening

A graduate student has prepared a thin oxide multilayer on a TEM grid and wants to identify the chemical state of the cation in each layer. EDS gives the elemental composition — confirms which metals are present, in roughly what ratios — but cannot distinguish $\text{Mn}^{2+}$ from $\text{Mn}^{3+}$ in the same Mn-O peak. The student switches to STEM-EELS mode, parks the focused probe on each layer in turn, and acquires a spectrum across the Mn $L_{2,3}$ edge near 640 eV energy loss. The fine structure of the edge — the shapes and intensities of the white lines — encodes the oxidation state. The student can read which layers are $\text{Mn}^{2+}$ and which are $\text{Mn}^{3+}$, plus the spatial distribution between them.

This is what EELS adds to TEM/STEM: chemical-state information at near-atomic spatial resolution. EDS tells you which elements are present; EELS tells you what those elements are doing.

### Learning objectives

By the end of this chapter you can:

- **Describe** the structure of an EELS spectrum: zero-loss peak, low-loss region (plasmon), core-loss region (element-specific edges).
- **Compare** EELS to EDS in spatial resolution, light-element sensitivity, and chemical-bonding sensitivity.
- **Identify** elemental edges in core-loss spectra.
- **Recognize** thickness-effect artifacts, multiple-scattering artifacts, and background-subtraction errors.
- **Choose** between EDS and EELS for a given analytical question.

### Prerequisites

Chapter 17 (STEM, HAADF). Chapter 9 (EDS — for comparison). Chapter 6 (inelastic scattering, energy loss).

### Why this chapter matters

Modern STEM-EELS is a workhorse of nanoscale chemical analysis. Reading published papers in materials and nanomedicine routinely requires understanding EELS spectra and chemical maps.

---

## 2. The EELS spectrum: zero-loss, low-loss, core-loss [verify all numerical values]

When a beam electron passes through a thin specimen, it can lose energy through several mechanisms:

- **No loss (or near-zero loss).** Most electrons traverse without significant energy loss. Forms the **zero-loss peak (ZLP)** at $E = 0$ in the EELS spectrum. The ZLP width is set by the gun's energy spread (Chapter 3): ~3 eV for tungsten, ~0.3 eV for Schottky/cold-FE.
- **Plasmon loss** at energies of 5–30 eV [verify]. Beam electron excites collective oscillations of the valence electrons in the solid. Bulk plasmons appear as a broad peak at a material-specific energy. Surface plasmons at lower energies.
- **Single-electron excitations** at 5–50 eV [verify]. Beam electron excites individual valence electrons across the band gap. Material-specific.
- **Core-loss edges** at energies characteristic of inner-shell ionization, typically 50 eV to 2,000+ eV. Beam electron ionizes a core-shell electron of a specific atom; the energy loss equals (approximately) the core-shell binding energy. Each element has characteristic edges (K, L, M).

The spectrum runs from $E = 0$ to several keV. The dominant features are the ZLP (typically $10^4$–$10^6$ counts), the plasmon (similar magnitude on a log scale), and the core-loss edges (orders of magnitude weaker, on a steeply declining background).

### Reading the spectrum

For each element of interest, the operator looks at the appropriate core-loss edge:

- Light elements (B, C, N, O, F): K-edges at ~190, 285, 400, 530, 690 eV [verify].
- Mid-Z elements: L-edges at hundreds of eV.
- Heavier elements: M-edges or higher at energies above the typical EELS range.

Reading an edge's onset energy identifies the element. Reading the **near-edge fine structure** (ELNES) within ~30 eV of the onset gives chemical-bonding information: oxidation state, coordination, bond environment. The detailed shape of the Mn L₂,₃ edge differs systematically between Mn²⁺, Mn³⁺, and Mn⁴⁺ — this is how oxidation states are read [verify].

---

## 3. EELS vs. EDS [verify all comparative claims]

| Property | EDS | EELS |
|---|---|---|
| Detected radiation | X-rays | electrons |
| Detection limit | ~0.1 wt% | ~0.01 wt% [verify] |
| Light-element sensitivity (Z<11) | poor (low fluorescence yield) | excellent |
| Chemical-state info | minimal | rich (edge fine structure) |
| Spatial resolution | ~1 μm in SEM; ~1 nm in STEM | ~0.1 nm in STEM-EELS |
| Energy resolution | ~125 eV | ~0.1–1 eV with monochromator |
| Specimen thickness | bulk OK | thin needed (<100 nm) |
| Acquisition speed | fast | slower [verify] |

The two are complementary. EDS is faster and gives reliable major-element quantification; EELS is more sensitive to light elements and resolves chemical state. Modern STEM-EELS with a high-resolution monochromator can distinguish chemical bonds at the single-atom-column level.

---

## 4. EFTEM and spectrum imaging [verify]

**Energy-filtered TEM (EFTEM)** uses an energy filter (post-specimen prism) to select electrons of a specific energy loss for image formation. The result is an image where contrast comes from a specific energy window — typically a particular element's core-loss edge. EFTEM elemental maps are 2D arrays where intensity at each pixel reflects how much of that element is present at that location.

**Spectrum imaging (SI)** is the STEM analogue: scan the focused probe across the specimen, acquire a full EELS spectrum at each pixel, and post-process to extract per-pixel elemental and chemical-state maps.

Modern STEM-SI sessions can produce datasets with millions of pixels, each with a full EELS spectrum. Data volumes are TB-scale; analysis is software-driven.

---

## 5. What Goes Wrong Here [verify]

- **Thickness effects.** Thin-specimen approximation breaks down for thicker specimens; multiple scattering smears the spectrum. Recognition: multiple-scattering features in low-loss; "thick" labels appearing in software. Fix: thinner specimens or deconvolution.
- **Channeling artifacts.** STEM-EELS along low-index zone axes gives orientation-dependent signals. Fix: image off-axis or use simulation.
- **Background-subtraction errors.** Core-loss edges sit on a steeply declining background; small fitting errors give wrong concentrations. Fix: longer pre-edge windows; improved fitting routines.
- **Beam damage during long EELS acquisition.** Prolonged dwell on beam-sensitive specimens damages them. Fix: low-dose protocols; fresh fields.

### Hazards and Safe Practice

- **Prolonged dwell-time damage** to beam-sensitive specimens during EELS acquisition. The same hazards as Chapter 6 + Chapter 13 apply; cross-reference Appendix A.

---

## 6. Quick-Reference Table [verify]

| Spectral region | Energy range | Information |
|---|---|---|
| Zero-loss peak | -1 to +1 eV | gun energy spread, focus reference |
| Low-loss / plasmon | 5–50 eV | plasmon, dielectric properties |
| Core-loss edges | 50–2000 eV | elemental ID, chemical state |

---

## 7. Connections Forward

Chapter 19 covers tomography and low-dose imaging. Chapter 23 returns to artifacts comparatively across techniques.

---

**What would change my mind:** This chapter is a stub. The professor's revision will add the genuine teaching content that source materials and lecture content provide. All [verify] markers reflect provisional values pending source confirmation.

**Tags:** `EELS`, `inelastic-scattering`, `STEM-EELS`, `chemical-state`, `core-loss`

---

### Note to the professor

This chapter is **stub-only**. No dedicated EELS lecture exists in weeks 1–15 of the source materials. The chapter is drafted from the outline scope plus standard textbook material from Egerton (3rd ed., Springer 2011) and similar references. Numerical values, comparative claims, and technical specifics carry [verify] markers throughout.

For the full chapter, the professor will need to add:
- Detailed discussion of inelastic scattering physics.
- Description of post-specimen EELS spectrometer and prism geometry.
- Specific edge-onset energies for elements likely to appear in the course's example specimens.
- ELNES fine-structure interpretation with worked examples.
- EFTEM elemental mapping protocol.
- STEM-SI workflow.
- Comparison with EDS in operational terms.
- Worked exercises tied to course-relevant specimens.
- Hazards callout content specific to EELS operation.

The 300-500 word target stub is exceeded here to provide the professor with a more complete starting structural shell, but the actual teaching content remains to be developed. Stub flag set to `true` in the log row.

Voice anchoring: anchored, but the chapter is short (~1,000 words) and structurally truncated. Professor may want to expand to the full 4,000-7,000 word emma chapter format with course-appropriate worked examples once source material is in hand.
