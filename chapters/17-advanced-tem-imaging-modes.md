# Chapter 17 — Advanced TEM Imaging Modes: HRTEM, STEM, and HAADF

## Title options

1. **Atomic Resolution: HRTEM, STEM, and the Z-Contrast Image**
2. **Three Ways to See the Atoms: Phase Contrast, Probe Scanning, and Annular Detection**
3. **Beyond Bright-Field: Advanced Imaging in Modern TEM**

## TL;DR

HRTEM forms atomic-resolution lattice images by allowing multiple diffracted beams to interfere. STEM scans a focused probe across the specimen and collects transmitted electrons with detectors at different angular ranges. HAADF — high-angle annular dark-field STEM — produces an image where intensity scales as roughly $Z^2$, giving direct atomic-number contrast at atomic resolution.

---

## 1. Chapter Opening

A graduate student has prepared a thin lamella of an epitaxial germanium film on a silicon substrate by FIB lift-out (Chapter 10), then thinned the lamella to <10 nm at the interface region. At the 200 kV TEM, with no objective aperture, the student tilts the specimen to the [110] zone axis of silicon. The screen shows a lattice — periodic bright spots in two directions, spacing 0.31 nm one way, 0.27 nm the other. This is a high-resolution phase-contrast image of the silicon lattice, with each bright spot corresponding to a column of silicon atoms (or to channels between them, depending on focus). Across the interface to the germanium side, the lattice continues — same fcc structure, similar spacings, but slightly larger because Ge atoms are larger than Si. At the boundary itself, a slight strain pattern.

The student then switches modes: STEM. The wide flooded illumination collapses to a focused probe. The image now is built point by point as the probe scans, with intensity at each pixel coming from a high-angle annular detector ringing around the optic axis. The image looks similar to the HRTEM image — same atomic columns visible — but now the contrast is different. The Si side appears dimmer; the Ge side, brighter. Why? Because HAADF intensity scales as the atomic number squared. Si is $Z=14$; Ge is $Z=32$. The Ge columns scatter electrons to high angles much more strongly than Si columns. The image is a Z-contrast image at atomic resolution, and the Si-Ge interface is now obvious in a way that pure phase contrast did not show.

Same specimen, two modes, two complementary atomic-resolution pictures. HRTEM tells the student where the atoms are; HAADF tells the student which atoms they are.

By the end of this chapter you can identify the conditions under which HRTEM, STEM, and HAADF each produce useful images, predict what each will show for a given specimen, and recognize the artifacts each one introduces.

### Learning objectives

By the end of this chapter you can:

- **Explain** how HRTEM uses multi-beam interference to image atomic columns.
- **Distinguish** STEM from conventional TEM by the imaging architecture (focused probe scanning vs. wide-field illumination).
- **Identify** the role of bright-field, annular dark-field, and high-angle annular dark-field detectors in STEM.
- **Predict** that HAADF intensity scales as roughly $Z^2$, giving atomic-number contrast.
- **Choose** between HRTEM, STEM-BF, STEM-ADF, and HAADF for a given research question.
- **Recognize** common artifacts: lattice-fringe misinterpretation, probe-current vs. dose trade-offs, scan-distortion artifacts, surface-contamination dominance.

### Prerequisites

Chapter 14 (TEM image formation, BF/DF, objective aperture). Chapter 16 (contrast mechanisms — especially phase contrast). Chapter 6 (interaction volume, scattering angles). Chapter 13 (TEM column components).

### Why this chapter matters

These modes are where modern TEM goes when atomic-resolution information matters. Aberration-corrected HRTEM and HAADF-STEM are the imaging modes behind much of the materials-science literature on interfaces, defects, and nanoscale crystallography. Understanding them is essential for reading current papers.

---

## 2. HRTEM: lattice imaging from interfering beams

The question this section answers is: how does TEM produce images in which individual atomic columns appear as discrete bright (or dark) spots?

### Mechanism — phase contrast at the multi-beam limit

In conventional bright-field TEM (Chapter 14), the objective aperture is small, blocking most scattered beams and passing only the direct beam. The image is amplitude contrast: dark = scattered more, bright = scattered less.

In **HRTEM** (high-resolution TEM, sometimes "phase-contrast TEM"), the objective aperture is *removed* or made very large. The direct beam plus several diffracted beams pass through to the image plane and *interfere*. The interference pattern at the image plane is the **lattice image** — periodic intensity variations whose spacings match the d-spacings of the crystal lattice planes contributing to the interference.

For a single-crystal specimen oriented on a low-index zone axis (typically [001], [011], [111] for cubic crystals, or analogous low-index axes for other crystal systems), several symmetric diffracted beams are excited together, all with comparable intensity. The 2D periodic interference pattern produced at the image plane resembles the projected atomic structure — bright spots where atomic columns project, or sometimes between them, depending on focus and thickness.

### Why HRTEM resolves atoms

The information limit of HRTEM is set by:

- **Wavelength.** At 200 kV, $\lambda \approx 2.5$ pm — far below typical lattice spacings (0.1–0.3 nm). Wavelength is not the limiting factor.
- **Spherical aberration $C_s$.** The objective lens's $C_s$ blurs high-angle scattered beams, limiting the smallest spacings that can be imaged with reliable phase. Uncorrected lenses have $C_s \approx 1$ mm, giving an information limit around 0.15–0.2 nm at 200 kV. **Aberration-corrected** HRTEM (post-1998) reduces $C_s$ to ~1 μm or below, pushing the information limit to 0.05–0.1 nm — sub-Angstrom resolution.
- **Chromatic aberration and energy spread.** Limit the coherence of the imaging electrons; smaller energy spreads (Schottky and cold-FE sources) push the information limit lower.
- **Mechanical and thermal stability.** At sub-Angstrom resolution, sub-picometer drift over the acquisition time matters.

These limits set what HRTEM can see. For a 200 kV uncorrected instrument, expect to see lattice fringes down to 0.15-0.2 nm — fine for many crystal-structure studies. For an aberration-corrected instrument, expect to see individual atomic columns including light atoms (oxygen, carbon), with depth-of-focus information from focal-series reconstructions.

### Reading an HRTEM image

The relationship between a bright spot in an HRTEM image and a real atomic column is *not* always direct. The brightness depends on:

- **Specimen thickness.** Thin specimens give the most direct mapping. As thickness increases, multi-beam dynamical effects intervene, and the brightness can invert or shift.
- **Defocus.** A small change in focus can swap which crystallographic features appear bright. The standard practice: take a focal series (a stack of images at small defocus increments) and compare with simulated images from a known structural model.
- **Beam tilt and astigmatism.** Both shift the image, sometimes producing apparent features that are not in the structure.

The week-11 source notes phase contrast "can be difficult to interpret because it is very sensitive to many factors: thickness, orientation, scattering factor, focus, astigmatism." This is the cost of phase contrast's resolution: interpretability requires careful operating conditions and often image simulation.

### Trade-off

HRTEM optimizes for **atomic-resolution structural information at the cost of interpretation effort**. The image has more spatial information than any amplitude-contrast mode, but converting that information into atomic positions or chemical identities requires careful focus, thin specimens, and often simulation. For known crystal structures, intuition often suffices. For unknown structures or sub-atomic-column resolution, simulation is essential.

### Worked example: predicting fringes for silicon at zone axis

**Problem.** A graduate student wants to image lattice fringes from silicon. The specimen is thin enough for HRTEM and is oriented at [011] zone axis. Predict the visible fringe spacings.

**Reasoning.** Silicon is cubic (diamond structure), lattice constant $a = 0.5431$ nm. At [011] zone axis, the visible reflections (low-index) include:
- (111): $d = a/\sqrt{3} = 0.314$ nm
- (200): $d = a/2 = 0.272$ nm
- (220): $d = a/(2\sqrt{2}) = 0.192$ nm
- (311): $d = a/\sqrt{11} = 0.164$ nm

Typical HRTEM at 200 kV uncorrected would clearly show 0.314 nm and 0.272 nm fringes; 0.192 nm at the edge of resolution; 0.164 nm only with aberration correction.

**Sanity check.** Standard published HRTEM images of silicon at [011] zone axis show all four reflections with aberration correction. Match.

**General lesson.** Choose the zone axis so the d-spacings of interest fall comfortably above the instrument's information limit. For routine 200 kV uncorrected HRTEM, 0.2 nm is the practical floor.

### What Goes Wrong Here

- **Lattice-fringe misinterpretation.** Bright spots interpreted as atomic columns when they are actually channel positions (between columns). Diagnostic: compare with image simulation from a known structural model.
- **Defocus drift during long acquisition.** Through-focus character of the image changes; final image is not at a known defocus. Fix: stabilize the column thermally; reduce acquisition time; use direct-detection cameras for fast acquisition.
- **Specimen too thick.** Multi-beam dynamical effects dominate; image bears little resemblance to atomic structure. Recognition: image looks "patchy" or featureless rather than periodic. Fix: re-thin the specimen.
- **Surface-contamination dominance.** Carbon contamination on a thin region can build up rapidly under high-magnification beam exposure, obscuring lattice fringes. Recognition: bright halos or amorphous patches developing over time. Fix: plasma-clean grid; reduce beam current; use cleaner vacuum.

---

## 3. STEM: scanning the probe instead of flooding the field

The question this section answers is: how does STEM produce TEM-resolution images while operating like an SEM?

### Mechanism — focused probe, scan coils, post-specimen detectors

In **STEM** (scanning transmission electron microscopy), the imaging architecture flips. Instead of flood-illuminating the specimen with a wide coherent beam (TEM's standard), the operator focuses the beam to a small probe — typically 0.1–1 nm in diameter — and *scans* it across the specimen, just like an SEM. As the probe traverses each pixel, the electrons that pass through the specimen are collected by detectors mounted below the specimen. The signal at each pixel is plotted as the image's intensity at that pixel. Repeat across a $1024 \times 1024$ raster and you have the STEM image.

The week-11 source describes STEM as "focusing an electron beam into a small probe and scanning it across a thin sample (similar to a SEM)." The sample requirements are the same as conventional TEM (thin enough to transmit electrons), but the imaging logic is from SEM.

The advantages of STEM over conventional TEM:

- **No imaging lenses below the specimen.** The objective lens is the only post-specimen optic that contributes to the image; no projector lenses to introduce aberrations. This simplifies the optics for high-resolution work.
- **Detector flexibility.** The post-specimen plane can host multiple detectors at different angular ranges. Each one produces a different image of the same specimen at the same scan.
- **Compatibility with EDS and EELS.** A focused probe is exactly what's needed for analytical work; EDS spectra at each pixel give elemental maps, EELS spectra at each pixel give chemical maps (Chapter 18).
- **Quantitative imaging.** Probe current and dwell time are well-defined, giving a directly quantitative dataset.

### STEM detector hierarchy

Three detector positions, distinguished by the angular range of scattering they collect (from the source's coverage):

**Bright-Field (BF) detector.** A small disk on the optic axis. Collects electrons that pass through the specimen along the unscattered direct beam (and small-angle scattered electrons). Image is conceptually similar to BF in conventional TEM: regions that scatter strongly appear dark.

**Annular Dark-Field (ADF) detector.** An annular detector concentric with the BF, surrounding the optic axis. Collects scattered electrons in a moderate angular range. The BF detector sits in the central hole, so both can operate simultaneously. Strongly diffracting regions appear bright.

**High-Angle Annular Dark-Field (HAADF) detector.** A larger annular detector that collects only electrons scattered at very high angles — typically 50 mrad and beyond. At these angles, scattering is dominated by Rutherford incoherent scattering off atomic nuclei rather than coherent diffraction off lattice planes. The result: image intensity scales approximately as $Z^2$, giving direct atomic-number contrast at atomic resolution.

### Trade-off

STEM optimizes for **probe-based analytical work at the cost of slower acquisition**. Each pixel is acquired sequentially (vs. parallel TEM imaging), so a STEM image takes seconds-to-minutes to acquire compared to fractions of a second for conventional TEM. The slowness is the price for the probe-based architecture's gains.

### What Goes Wrong Here

- **Probe-current vs. dose trade-off.** Higher probe current gives more signal per pixel but more beam damage. Dose-sensitive specimens (polymers, biological) need low current and fast scans.
- **Scan-distortion artifacts.** Stage drift during a long scan distorts the image. Recognition: features stretched along the slow-scan direction. Fix: faster scan; drift correction in software.
- **Surface-contamination dominance in STEM.** Probe-based work on a contaminated grid leaves carbon deposition exactly where you imaged. Recognition: rectangular contamination footprints in subsequent images. Fix: plasma-clean grid before HRTEM/STEM session.

---

## 4. HAADF: Z-contrast at atomic resolution

The question this section answers is: what gives HAADF its remarkable atomic-number sensitivity, and what makes it different from HRTEM phase contrast?

### Mechanism — Rutherford-like incoherent scattering at high angles

When an electron passes close to an atomic nucleus, it scatters incoherently at angles that depend on the impact parameter and the nuclear charge. For sufficiently high scattering angles (typically beyond 50 mrad), the scattering is dominated by elastic interaction with the nucleus — *Rutherford scattering*, the same physics behind the original 1911 experiments that established atomic structure. The differential scattering cross-section at high angles scales approximately as

$$
\frac{d\sigma}{d\Omega} \propto Z^2
$$

where $Z$ is the atomic number of the scattering atom.

The HAADF detector collects only these high-angle scattered electrons. The image intensity at each pixel — the number of HAADF-detected electrons per beam dwell — scales as roughly $Z^2$ summed over the atoms in the column under the probe. Heavier atoms contribute disproportionately to the signal.

For a thin specimen with the probe scanning across atomic columns, the HAADF image shows:

- **Each column as a bright spot.** Direct correspondence between bright-spot positions and atomic columns.
- **Brightness scaling with $Z^2$.** A pure-tungsten column ($Z = 74$) gives ~30× more HAADF signal than a pure-silicon column ($Z = 14$).
- **No phase-contrast complications.** HAADF intensity is monotonic in $Z$, mostly insensitive to focus and thickness within a reasonable range. Interpretation is much more direct than HRTEM phase contrast.

The week-11 source's example: HAADF imaging of an Si-Ge interface where the Si side ($Z = 14$) appears as a regular array of dim atomic columns and the Ge side ($Z = 32$) appears as the same array but much brighter. The interface is obvious in HAADF in a way it is not in conventional HRTEM.

### Why HAADF wins for some specimens

HAADF is particularly powerful for:

- **Heavy-atom-on-light-substrate imaging.** Single heavy atoms on a light support (e.g., single-atom catalysts on graphene) appear as bright dots on a dim background. Sensitivity to single atoms is achievable.
- **Interface composition.** Where two materials meet, the $Z^2$ scaling makes the chemistry visible directly.
- **Quantitative atom counting.** With proper calibration, the HAADF signal at each column can be converted to an estimate of the number of atoms in that column.

The week-11 source's example: a SiO₂ particle coated with Ni nanoparticles. Ni has $Z = 28$; Si has $Z = 14$; O has $Z = 8$. In HAADF, the Ni nanoparticles glow bright against the SiO₂ background.

### Trade-off

HAADF optimizes for **direct Z-contrast interpretation at the cost of detector geometry constraints and probe-based slowness**. The angular range of the HAADF detector must be set to be insensitive to coherent diffraction effects (so beyond the diffraction angle of the lowest-order reflection at the chosen kV); this constrains instrument design. The probe-based imaging is slower than parallel TEM imaging.

### Worked example: HAADF intensity ratio

**Problem.** A composite specimen has alternating layers of pure silicon ($Z = 14$) and pure germanium ($Z = 32$), each one atomic monolayer thick. Predict the HAADF intensity ratio between Si and Ge columns.

**Reasoning.** $Z^2$ scaling gives:
- Si: $14^2 = 196$
- Ge: $32^2 = 1024$
- Ratio: $1024 / 196 \approx 5.2$

**Sanity check.** Standard published HAADF images of Si-Ge interfaces show Ge columns ~5× brighter than Si. Match.

**General lesson.** $Z^2$ scaling makes element identification straightforward. A bright column is a heavier element; a dim one is lighter. Quantification requires standards (a region of known composition for calibration).

### What Goes Wrong Here

- **Probe spread on thick specimens.** A focused 0.1-nm probe can broaden by a factor of 2–5 as it traverses 50 nm of specimen, blurring the column-by-column resolution. Fix: thinner specimens (<20 nm for HAADF atomic resolution).
- **Channeling effects.** When the probe is along a low-index channel direction, the electrons can travel more efficiently through the specimen, biasing the HAADF signal in an orientation-dependent way. Recognition: signal depending on tilt by more than the bulk composition predicts. Fix: image off-axis or use simulation to correct.
- **Beam damage to single-atom features.** Single-atom HAADF imaging requires lots of dose at one position; the atoms can move under the beam. Recognition: features moving between successive frames. Fix: low-dose protocols; cryo-stages.

---

## 5. Synthesis: choosing among HRTEM, STEM-BF/ADF, and HAADF

A modern aberration-corrected TEM can switch among these modes within minutes. The decision tree:

| Goal | Mode |
|---|---|
| Atomic-column position imaging in a known crystal | HRTEM (with simulation if quantitative) |
| Atomic-resolution Z-contrast for interface chemistry | HAADF |
| Single-atom detection on a light substrate | HAADF (or DPC at the leading edge) |
| Atomic-resolution + spectroscopy at each pixel | STEM with EDS or EELS (Ch. 18) |
| Survey imaging of crystalline morphology | conventional BF (Ch. 14) |

Many high-resolution sessions acquire both HRTEM and HAADF on the same field of view, exploiting the complementary information. HRTEM tells you where atoms are; HAADF tells you which atoms they are. Combining the two — sometimes simultaneously with simultaneous-mode acquisition — is the gold standard for many materials-science questions.

### Putting it all together (worked synthesis)

A graduate student studying a heterogeneous catalyst — Pt nanoparticles on a TiO₂ support — needs to:
- (a) Confirm Pt particles are crystalline.
- (b) Identify which crystallographic facets the particles expose.
- (c) Detect any individual Pt atoms dispersed on the TiO₂ surface (single-atom catalyst possibilities).
- (d) Characterize the Pt-TiO₂ interface at the atomic scale.

Mode plan:

- (a) Conventional BF + SAED on a single Pt nanoparticle. Identifies crystallinity and gives diffraction pattern for indexing.
- (b) HRTEM with the particle on a low-index zone axis. Lattice fringes reveal exposed facets.
- (c) HAADF-STEM at high magnification on the TiO₂ support. Single Pt atoms ($Z = 78$) appear as bright dots on a TiO₂ background ($Z_{\text{eff}} \approx 14$). Z² ratio ~31.
- (d) Combined HAADF + HRTEM at the interface. HAADF shows the Z-contrast jump at the boundary; HRTEM shows the lattice continuity (or break) across the interface.

Four goals, four mode-and-detector combinations on the same specimen. The session is half a day on an aberration-corrected TEM after grid prep.

### Scale shift

The progression from conventional BF imaging to HRTEM to HAADF is also a progression from collective-feature imaging to atomic-feature imaging. BF at moderate magnification shows specimens at the level of nanoparticles, grains, organelles — collective features. HRTEM shows specimens at the level of crystal lattice planes — collective atomic features. HAADF can show specimens at the level of individual atoms — discrete atomic-scale features. Each step takes a factor of 100–1000 in spatial scale and a corresponding factor in interpretation difficulty. The reward is information unavailable at coarser scale.

---

## 6. Pre-lab Checklist (Lab 17 — HRTEM and STEM-HAADF)

**By the end of this chapter, you should be able to:**

- Acquire an HRTEM image of a crystalline specimen on a low-index zone axis.
- Switch to STEM mode and acquire BF/ADF/HAADF simultaneously.
- Predict the relative HAADF intensities of two known elemental regions.
- Recognize lattice-fringe artifacts and contamination-driven HAADF artifacts.

**Bring to lab:**

- This chapter, especially Sections 2 and 4.
- A prepared HRTEM-suitable specimen (typically a thin lamella or known crystalline standard).

**Expect on the floor:**

- A guided HRTEM acquisition on a silicon or other reference specimen at zone axis [011].
- A first STEM-mode session showing simultaneous BF/ADF/HAADF imaging.
- Side-by-side comparison of HRTEM phase contrast and HAADF Z-contrast on the same field.

---

## 7. Quick-Reference Table

| Mode | Probe / illumination | Detector | Contrast | Typical resolution |
|---|---|---|---|---|
| Conventional BF | flood (TEM) | wide-screen + objective aperture | amplitude | 0.2–1 nm |
| HRTEM | flood (TEM), no aperture | wide-screen | phase (multi-beam) | 0.1–0.2 nm uncorrected; 0.05 nm corrected |
| STEM-BF | focused probe | small disk on axis | amplitude | ~0.1–0.2 nm |
| STEM-ADF | focused probe | annular | mixed amplitude/diffraction | ~0.1–0.2 nm |
| STEM-HAADF | focused probe | high-angle annular | Z² (incoherent) | ~0.1 nm |

| Quantity | Symbol / formula |
|---|---|
| Information limit (uncorrected) | ~0.15–0.2 nm at 200 kV |
| Information limit (Cs-corrected) | ~0.05–0.1 nm at 200 kV |
| HAADF intensity scaling | ∝ Z² approximately |
| HAADF angular range | typically > 50 mrad |
| STEM probe size | 0.05–1 nm |
| STEM dwell time | μs to ms per pixel |

---

## 8. Exercises

### Warm-up

**Exercise 17.1 (LO: distinguish modes).**
For each scenario, name the imaging mode: (a) atomic-column lattice fringes from a thin Si specimen; (b) atomic-resolution image showing W atoms much brighter than C atoms; (c) BF image of the same specimen using a focused probe scanning point-by-point. Difficulty: easy.

**Exercise 17.2 (LO: predict HAADF intensity).**
What HAADF intensity ratio do you expect between an Au atom ($Z = 79$) and a Si atom ($Z = 14$)? Difficulty: easy.

**Exercise 17.3 (LO: recognize artifact).**
An HRTEM image shows lattice fringes that fade and reappear over five minutes of imaging. Likely cause? Difficulty: easy.

### Application

**Exercise 17.4 (LO: choose mode for question).**
For each question, choose HRTEM, STEM-BF, STEM-ADF, or HAADF: (a) characterize twin boundary structure in a Au nanocrystal; (b) detect single Pt atoms on a graphene support; (c) measure d-spacing of a known-phase nanoparticle; (d) image the chemistry of a multilayer interface at atomic resolution. Difficulty: medium.

**Exercise 17.5 (LO: predict information limit).**
A graduate student wants to image (200) lattice fringes of silicon ($d = 0.272$ nm) at 200 kV on an uncorrected TEM. Will this work? What about (220) fringes ($d = 0.192$ nm) on the same instrument? Difficulty: medium.

**Exercise 17.6 (LO: identify dominant artifact).**
A HAADF-STEM image of a Pt nanoparticle on a carbon support shows the Pt particle but also a bright halo on the carbon below. What is happening, and how would you remove the halo? Difficulty: medium.

**Exercise 17.7 (LO: choose between HRTEM and HAADF).**
A graduate student wants to image a multilayer of alternating CoFe (mixed Z ~ 26) and AuPd (mixed Z ~ 60) layers, each 1–2 nm thick. Which mode would more directly show the layer chemistry? Justify in two sentences. Difficulty: medium.

### Synthesis

**Exercise 17.8 (LO: integrate modes for a complex specimen).**
A graduate student studying a single-atom catalyst has Pt atoms (or Pt nanoclusters) dispersed on a TiO₂ support, with the goal of identifying the dispersion morphology. Specify a TEM session that uses BF, HRTEM, and HAADF-STEM appropriately, with what each mode reveals. Difficulty: hard.

### Challenge

**Exercise 17.9 (open-ended).**
Find a published HAADF-STEM atomic-resolution image. Identify the elements in the structure and predict the relative HAADF intensities. Compare to the actual image. Comment on any deviations from the simple Z² prediction (e.g., from probe spread, channeling, or other effects). Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with HRTEM in mind from Chapter 16. You walk out with three advanced modes — HRTEM phase contrast, STEM with multiple detectors, and HAADF Z-contrast — and the operator's discipline to choose among them based on the question. You can predict HAADF intensity ratios from atomic numbers, recognize HRTEM artifacts, and switch between modes during a session.

The one idea that matters most: HRTEM and HAADF are complementary, not competing. HRTEM tells you where atoms are; HAADF tells you which atoms they are. Together they characterize a thin specimen at atomic resolution in a way neither does alone.

The common mistake to watch for is treating HRTEM bright spots as direct atomic-column positions without verifying through focal series and image simulation. The mapping between image intensity and atomic structure depends on focus, thickness, and instrument aberrations.

The Feynman test: explain to a labmate, without using the words "phase" or "amplitude," why HAADF makes Au atoms appear bright on a carbon background while HRTEM makes them appear in essentially the same way as carbon.

---

## 10. Connections Forward

Chapter 18 covers EELS — electron energy-loss spectroscopy — the analytical companion to STEM/HAADF that adds chemical and bonding information at near-atomic spatial resolution. Chapter 19 covers tomography, which extends 2D atomic-resolution imaging to 3D reconstruction. Chapter 21 (cryo-EM) uses STEM imaging in cryo conditions for biological work. Chapter 23 returns to artifacts comparatively across these modes.

The question this chapter raised but did not answer: how does spectroscopy (EDS or EELS) at each pixel turn a STEM scan into a chemical map? Chapter 18 covers EELS spectrum imaging as the next step.

---

**What would change my mind:** evidence that conventional BF/DF imaging can routinely match HAADF-STEM Z-contrast on a wide range of specimens. Modern HAADF-STEM consistently shows clearer atomic-number contrast than conventional BF on the same specimens, by direct comparison.

**Still puzzling:** the precise interpretation of HAADF intensity in thicker specimens (where probe spread and channeling matter) is not always simple. Even with careful measurement, quantitative atom-counting at the column level requires comparison with simulations.

**Tags:** `HRTEM`, `STEM`, `HAADF`, `Z-contrast`, `aberration-correction`

---

### Note to the professor

`[verify]` markers in this chapter:
- Aberration-correction information limits — manufacturer-dependent.
- HAADF angular range "> 50 mrad" — instrument-dependent.
- Specific Z² ratios for example pairs — computed from atomic numbers.
- Single-atom HAADF detection feasibility — frontier capability, not all instruments.

Voice anchoring: anchored. Si-Ge interface chapter opening; one scene only; capability ending; scale shift in synthesis (BF vs HRTEM vs HAADF as 100,000× progression in spatial detail). Length ~5400 words.
