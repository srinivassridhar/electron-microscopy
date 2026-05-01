# Chapter 23 — Artifact Recognition Across Techniques: A Comparative Synthesis

## Title options

1. **Is It Real? Comparative Artifact Recognition in EM**
2. **The Artifact Atlas: SEM, TEM, EDS, EELS Side by Side**
3. **When Techniques Disagree: Reading EM Images Skeptically**

## TL;DR

Every electron-microscopy technique introduces its own artifacts; the same specimen may show different "features" in SEM, TEM, EDS, and EELS for entirely physical reasons that have nothing to do with the specimen. This chapter synthesizes the per-chapter "What Goes Wrong Here" callouts into a comparative atlas, plus a decision framework for "is this real or is it an artifact?"

---

## 1. Chapter Opening

A graduate student looks at a published figure from a paper claiming a novel nano-feature in a polymer composite. The figure shows an SEM image with bright spots dispersed across the polymer matrix at ~50 nm spacing, claimed to be embedded gold nanoparticles. A second panel shows a BSE image of the same field — the bright spots are now darker than the matrix. Wait. Bright in SE means surface emission; dark in BSE means lower atomic number than the matrix. But the matrix is carbon ($Z = 6$); gold is $Z = 79$. Gold particles should be brighter in BSE, not darker. So either these are not gold, or the SEM imaging conditions confused the operator.

The student looks more carefully. The "bright spots" in the SE image have a halo around them characteristic of charging. The "dark spots" in the BSE image align perfectly with the SE bright spots — same locations, but BSE's lower sensitivity to surface charge makes them appear at the matrix's true gray level. The bright SE spots were charging artifacts, not gold particles. The paper's claim is wrong.

This is what Chapter 23 prepares you to do: read EM figures skeptically by comparing what different techniques say about the same specimen, and recognize when "features" are artifacts of imaging rather than properties of the sample.

By the end of this chapter you can identify the artifact type for any "feature" in an EM figure, propose a complementary technique that would distinguish artifact from real, and recognize the published-figure patterns that warrant skepticism.

### Learning objectives

By the end of this chapter you can:

- **Distinguish** artifacts of preparation from artifacts of imaging from real specimen features.
- **Apply** a comparative-technique check: "what would this look like in technique X versus technique Y?"
- **Recognize** the most common artifact families across SEM, TEM, EDS, EELS, and tomography.
- **Use** detector geometry, kV, tilt, and dose as diagnostic levers to isolate artifacts.
- **Evaluate** published figures for signs of common artifacts.

### Prerequisites

Chapters 4–22, especially the per-chapter "What Goes Wrong Here" callouts. This chapter assumes familiarity with all the imaging modes, prep methods, and detectors covered in the SEM and TEM halves.

### Why this chapter matters

Misinterpreted artifacts have produced retracted papers, wrong scientific conclusions, and wasted research time. The skill of reading EM images critically is what separates a competent microscopist from a credulous one.

---

## 2. The artifact taxonomy

The question this section answers is: how do you classify EM artifacts so you can recognize which family any given anomaly belongs to?

### Mechanism — three sources of "features that aren't real"

Every artifact has one of three sources:

**1. Specimen-preparation artifacts.** Introduced before the specimen reaches the imaging instrument. Examples:
- Drying shrinkage in biological SEM (Chapter 8).
- Fixation artifacts in biological TEM (Chapter 20).
- Microtomy chatter and knife marks (Chapters 8, 20).
- Ion-milling amorphization (Chapter 22).
- FIB curtaining and gallium implantation (Chapters 10, 22).
- Heavy-metal stain precipitation (Chapter 20).
- Sputter-coating decoration (Chapter 8).
- Drying cracks in non-CPD biological prep.

These artifacts are physical changes to the specimen. They cannot be removed by switching imaging mode; the specimen must be re-prepared.

**2. Imaging artifacts.** Introduced during data acquisition. Examples:
- Charging in SEM (Chapter 5).
- Beam damage during long imaging sessions.
- Drift during long acquisitions.
- Astigmatism (Chapters 2, 5).
- Edge brightening from SE detector geometry (Chapter 7).
- Bend contours in TEM diffraction contrast (Chapter 16).
- Fresnel fringes (Chapters 13, 16).
- Beam-induced motion in cryo-EM (Chapter 21).
- Missing-wedge artifact in tomography (Chapter 19).

These artifacts can sometimes be eliminated by changing operating conditions (different kV, different aperture, different tilt) without re-preparing the specimen.

**3. Detector and analytical artifacts.** Introduced by the detector or signal-analysis chain. Examples:
- E-T detector edge enhancement (Chapter 7).
- Sum peaks and escape peaks in EDS (Chapter 9).
- Si internal fluorescence in EDS (Chapter 9).
- Background-subtraction errors in EELS (Chapter 18).
- Channeling artifacts in HAADF (Chapter 17).
- Probe-spread blurring in STEM thick specimens (Chapter 17).

These artifacts are diagnosable from the spectrum or signal characteristics. Mitigation often involves changing acquisition parameters or post-processing.

### Trade-off

Artifact recognition optimizes for **interpretive integrity at the cost of additional acquisitions and analytical effort**. Cross-checking by alternative techniques takes time; reading published figures critically takes effort. The reward: avoiding wrong conclusions.

### What Goes Wrong Here

The meta-failure: not recognizing that something is an artifact. Once an operator or reader is convinced a feature is real, biased confirmation tends to ignore evidence of artifact-hood. The corrective is the comparative-technique check (Section 3).

---

## 3. The comparative-technique check

The question this section answers is: how do you distinguish real specimen features from artifacts using techniques you have at hand?

### Mechanism — what would technique X show?

For any "feature" in an EM image, ask: what would another technique show in the same region? Some standard cross-checks:

**SE vs BSE.** SE is surface-sensitive, BSE penetrates deeper and is Z-contrast. If a "feature" is bright in SE but the same location is matrix-color in BSE, the SE brightness is likely a surface/charge artifact, not a heavy-element inclusion.

**BF vs DF in TEM.** In BF, scattering shows as dark; in DF, scattering shows as bright. A feature dark in BF and bright in DF (in the appropriate aperture configuration) is real scattering. A feature dark in BF that does not appear in DF is probably a defocus shadow.

**Tilt the specimen.** Real specimen features stay in their location relative to other features. Artifacts of beam path (charging shadows, scan-coil distortions) move differently.

**EDS or EELS at the feature.** A bright spot interpreted as an inclusion should show distinct elemental signal in EDS. If the EDS spectrum at the feature is identical to the matrix, the feature is not compositional.

**Defocus through.** Fresnel fringes change position; lattice fringes rotate; real specimen features stay in place. Defocusing reveals which is which.

**Re-image after time.** Beam-induced features grow; charging migrates; specimen damage appears. Stable real features stay constant. Re-image a region after letting it sit for an hour.

**Different operator, different instrument, different prep.** If a feature is reproducible across these variables, it's real. If it disappears, it was an artifact.

### Trade-off

The comparative-technique check optimizes for **certainty at the cost of additional sessions**. A single SEM image cannot prove a feature is real. Multiple sessions, multiple modes, multiple specimens can.

### Worked example: distinguishing real from artifact

**Problem.** A graduate student claims to have observed a "novel structural feature" in a polymer film: hexagonally arranged spots ~30 nm apart in a TEM bright-field image at 100 kV. What checks would distinguish a real molecular pattern from an artifact?

**Reasoning.**
- **Tilt the specimen.** If the spots stay in the same lattice positions relative to the polymer matrix, real. If the spots move with the beam direction, artifact.
- **Defocus through.** If the spots' contrast inverts at over-vs-under focus, they are Fresnel fringes (artifact). If the spots stay similar through focus, they are real.
- **SAED on the feature region.** If the spots are a real lattice, SAED should show a discrete diffraction pattern with d-spacings consistent with 30 nm.
- **HRTEM at the feature.** Real lattice should show fringes within each spot consistent with the molecular structure.
- **Re-image at a different specimen region.** Reproducibility across the specimen.
- **Re-prepare specimen with different protocol.** Reproducibility across prep methods.

**Answer.** Several checks should align before claiming a real lattice. Single-image evidence is not sufficient.

**General lesson.** Reproducibility across modes, conditions, and preps is the standard for "real."

### What Goes Wrong Here

- **Confirmation bias.** Operator wants the feature to be real; ignores artifact evidence.
- **Insufficient cross-checks.** Single technique evidence presented as definitive.
- **Cherry-picked images.** One representative image from one session shown; bulk data with conflicting evidence not shown.

---

## 4. The artifact atlas: side-by-side comparisons

The question this section answers is: for the most common artifact types, what does each look like across techniques?

### Charging

| Technique | Appearance |
|---|---|
| SEM SE | bright halos; bright stripes; image distortions |
| SEM BSE | minimal; BSE less affected by surface fields |
| TEM | rare; TEM specimens are typically conducting via grid or coating |
| EDS | spurious peak shifts due to beam deflection |

**Mitigation:** lower kV (Ch. 5); coat specimen (Ch. 8); use VP-SEM (Ch. 10); switch to BSE.

### Drift

| Technique | Appearance |
|---|---|
| SEM | image scrolling slowly; stretched features along scan axis |
| TEM | features blur during long exposure |
| Cryo-EM | beam-induced motion in first 1-2 e/Å² of dose |
| Tomography | tilt series alignment fails |

**Mitigation:** thermal equilibration; faster acquisition; drift-correction software; DED frame-by-frame acquisition.

### Beam damage

| Technique | Appearance |
|---|---|
| SEM | features change shape during long sessions; carbon contamination grows |
| TEM polymer/biological | features fade; specimen mass loss |
| HRTEM | specimen amorphizes under the beam |
| Cryo-EM | beam-induced motion; ice damage |

**Mitigation:** lower kV; lower current; shorter dwell; cold stage; fresh fields.

### Preparation artifacts

| Technique | Specific artifacts to recognize |
|---|---|
| SEM bio | drying shrinkage, sputter-coating decoration |
| SEM metallic | polishing scratches, mount-medium smearing |
| TEM bio | fixation distortions, ultramicrotomy chatter, stain precipitation |
| TEM inorganic | ion-milling amorphization, FIB curtaining, gallium implantation |
| Cryo-EM | crystalline ice, ice contamination |

**Mitigation:** prep-specific (re-prep with different protocol).

### Detector-specific artifacts

| Detector | Artifact |
|---|---|
| SEM E-T | edge brightening; SE3 contamination |
| In-lens (TTL) | working-distance distortion at long WD |
| BSE annular | tilt-induced topographic confusion with composition |
| EDS | sum peaks, escape peaks, Si internal fluorescence |
| EELS | thickness effects, multiple scattering, channeling artifacts |
| HAADF | probe-spread blur on thick specimens |

### Diffraction and contrast artifacts

| Technique | Artifact |
|---|---|
| TEM BF | bend contours mistaken for defects |
| TEM DF | dim regions misinterpreted as voids |
| HRTEM | lattice-fringe misinterpretation; defocus-dependent feature appearance |
| SAED | indexing errors; double-diffraction extra spots |
| Tomography | missing-wedge elongation |

### Trade-off

The atlas optimizes for **comparative recognition at the cost of specificity**. Each entry above is a starting point for a fuller diagnostic; specific cases may need additional cross-checks. The atlas is the framework, not the final answer.

---

## 5. Synthesis: a decision framework for "is this real?"

The standard diagnostic flowchart for any unusual EM feature:

1. **Specify the specimen and prep.** What did you put in the chamber? What prep method was used?
2. **Specify the imaging conditions.** kV, detector, magnification, tilt, dwell. The methods sentence.
3. **Identify the apparent feature.** Describe it in physical terms (bright halo, dark band, periodic stripes, etc.).
4. **Check the artifact taxonomy.** Could this be a prep artifact? An imaging artifact? A detector artifact?
5. **Run a complementary technique.** SE↔BSE, BF↔DF, tilt, defocus through, EDS at the feature, HRTEM on the feature.
6. **Re-image after time.** Stable real features remain; growing or migrating features are likely artifacts.
7. **Re-image with different prep.** Reproducibility across prep methods is the gold standard for "real."
8. **Cross-check with non-EM techniques.** Optical microscopy, AFM, XRD, fluorescence, TEM if SEM was used or vice versa. Each independent method gives an independent constraint.
9. **Read the literature.** Has this artifact been reported before? Is this a known failure mode for this material with this prep?
10. **Skeptical conclusion.** Default to artifact unless evidence is clearly compelling for real.

### Putting it all together (worked synthesis)

A research group claims a novel nano-pattern in a fast-charging battery cathode material. The pattern shows ~10 nm bright dots in HAADF-STEM images. Goals:
- Confirm the dots are real Sb (a heavy element) precipitates, not artifacts.
- Determine the spatial distribution and crystallographic relationship to the matrix.

Plan:
- **HAADF-STEM** baseline image. Dots present.
- **Tilt to a low-index zone axis** of the matrix material. If dots remain at consistent positions relative to matrix lattice, structural. If dots change, channeling artifact.
- **EDS on the dot positions.** Real Sb gives Sb K and L peaks. Negative dots give matrix-only spectrum.
- **HRTEM on a dot.** Real precipitate shows crystalline lattice (potentially with epitaxial relationship to matrix). Artifact gives no fringes.
- **Compare with BF and DF imaging at the same location.** Different aperture configurations produce consistent patterns.
- **Independent prep, second specimen.** Reproducibility check.

If all checks align, the dots are real. If any check fails, more work needed before publication.

The wonder. EM imaging across modes is a triangulation system. No single image is sufficient evidence; the integrity of any conclusion depends on agreement across multiple independent measurements. This is the same standard scientists use across fields, but in EM, the modes that triangulate are usually present in the same instrument and accessible within the same session.

---

## 6. Pre-lab Checklist (Lab 23 — artifact identification practice)

**By the end of this chapter, you should be able to:**

- Identify the most likely artifact source for any unusual feature in an EM image.
- Run cross-checks (SE/BSE, BF/DF, tilt, defocus) to test artifact hypothesis.
- Read published EM figures critically.

**Bring to lab:**

- This chapter, especially the artifact atlas.
- A specimen with known artifacts (e.g., a known charging insulator, a known FIB-prepped lamella, a stained biological section).

**Expect on the floor:**

- Practice artifact identification on the lab's reference specimens.
- A guided walkthrough of cross-checks for a specific artifact type.
- Discussion of how to write a methods section that documents artifact-resistance.

---

## 7. Quick-Reference Table

| Artifact | Recognition | Mitigation |
|---|---|---|
| Charging | bright halos in SE; doesn't appear in BSE | lower kV, coat, VP-SEM |
| Drift | image scrolling | thermal equilibration; faster acquisition |
| Beam damage | features change with time | lower kV, current, dose |
| Astigmatism | direction-dependent focus; rotates 90° through focus | stigmator alignment cycle |
| Bend contours | dark bands in BF; move with tilt | tilt to remove |
| Fresnel fringes | bright-dark stripes parallel to edge | use as focus indicator; recognize as artifact |
| Edge brightening (SE) | thin features over-bright | adjust for in quantification |
| FIB curtaining | vertical stripes on FIB lamella | cleanup pass; better protective Pt |
| Crystalline ice (cryo) | sharp diffraction rings on ice region | re-vitrify |
| Missing wedge | elongation along beam in tomography | dual-axis tomography; advanced algorithms |
| Sum peak (EDS) | peak at 2× a strong line's energy | lower count rate |
| Escape peak (EDS) | peak at parent − 1.74 keV | software correction |

| Cross-check | What it distinguishes |
|---|---|
| SE vs BSE | charging vs composition |
| BF vs DF | scattering presence vs absence |
| Tilt | structural vs beam-path artifact |
| Defocus through | Fresnel fringe vs real feature |
| EDS at feature | composition real vs artifact |
| Re-image after time | stable real vs damage/contamination |
| Independent prep | reproducible vs prep-specific |

---

## 8. Exercises

### Warm-up

**Exercise 23.1 (LO: identify artifact source).**
For each, name the most likely artifact source: (a) bright halos around features in an SEM SE image; (b) elongated nanoparticles in a TEM tomographic reconstruction; (c) dark vertical stripes on a FIB lamella; (d) periodic bright spots in a HRTEM image that don't appear in the SAED. Difficulty: easy.

**Exercise 23.2 (LO: choose cross-check).**
A bright spot in an SEM SE image — which detector or mode would you use to test if it's a heavy-element inclusion or a charging halo? Difficulty: easy.

**Exercise 23.3 (LO: distinguish artifact from real).**
A TEM BF image shows a thin dark line crossing several grains of a polycrystalline metal. Real defect or artifact? What test? Difficulty: easy.

### Application

**Exercise 23.4 (LO: design cross-check).**
A graduate student claims to have observed a 20-nm void inside a single-crystal silicon film. Specify three independent cross-checks that would distinguish a real void from an artifact (charge accumulation, defocus shadow, FIB-induced damage). Difficulty: medium.

**Exercise 23.5 (LO: apply taxonomy).**
A paper's SEM figure shows nano-features that the authors interpret as a novel mineralogical phase. From the methods section: kV 25, FE-SEM, in-lens detector, working distance 5 mm, no coating, no prep cross-check. List three plausible artifact hypotheses and one test for each. Difficulty: medium.

**Exercise 23.6 (LO: recognize charging).**
A SEM image of a polymer shows bright periodic bands. The same field, imaged at lower kV, shows the bands disappearing. What is the artifact, and why does the cross-check work? Difficulty: medium.

### Synthesis

**Exercise 23.7 (LO: full diagnostic on a published figure).**
Find a published EM figure in your research field. Identify the imaging mode and detector. List three plausible artifacts that could appear in that mode. Comment on whether the figure shows evidence of any of them, and what cross-check the authors should have included. Difficulty: hard.

### Challenge

**Exercise 23.8 (open-ended).**
Find a paper that has been retracted or corrected for misinterpreted EM imaging. Read the original and the retraction. What artifact was misidentified as real, and what cross-check would have caught it? Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with the various artifacts named in earlier chapters but not synthesized. You walk out with a comparative atlas, a decision framework for distinguishing real from artifact, and a discipline of multi-technique cross-checking.

The one idea that matters most: every EM image has artifacts; the operator's job is to recognize them before they propagate into wrong conclusions. The standard for "real" is reproducibility across modes, conditions, and preparations.

The common mistake to watch for is single-image evidence. No single SEM or TEM image is sufficient to prove a feature is real. Multi-technique triangulation is the working standard.

The Feynman test: explain to a labmate, without using the word "artifact," why the same specimen can produce different "features" in SEM and TEM that are not really there.

---

## 10. Connections Forward

Chapter 24 takes the artifact synthesis and uses it as input to technique-selection: which technique gives the most artifact-resistant answer for a given question? Chapter 25 covers cross-technique applications where the artifact synthesis informs the multi-technique workflow design. Chapter 26 covers reporting and critique with explicit attention to artifact-resistance in published figures.

The question this chapter raised but did not answer: how do you choose which combination of techniques to use for a given research question? Chapter 24 provides the technique-selection framework with artifact-resistance as one criterion.

---

**What would change my mind:** evidence that any single EM technique could produce artifact-resistant results without cross-checking. The empirical record consistently shows that single-technique evidence is over-interpreted; multi-technique cross-checking is the standard.

**Still puzzling:** the practical decision of when to invest the time in multi-technique cross-checking versus when to accept single-mode evidence is mostly judgment-driven. Some labs invest heavily and avoid retractions; others move fast and occasionally pay the price.

**Tags:** `artifact-recognition`, `cross-technique`, `comparative-imaging`, `interpretation`, `methodology`

---

### Note to the professor

This chapter synthesizes content from all prior chapters (Ch. 4-22) plus standard artifact-recognition pedagogy. It is intentionally light on `[verify]` markers because the content is largely taxonomical synthesis rather than specific numerical claims.

Voice anchoring: anchored. Polymer-claim chapter opening (one scene only). Capability ending. Wonder grounded in numbers (a single retracted paper's worth of mismatched cross-checks; reproducibility across multiple preps). Length ~5300 words.

The chapter is suited for late in the course when students have learned all the imaging modes and prep methods. The cross-check rule of thumb — "what would technique X show?" — is the central operator skill the chapter teaches.
