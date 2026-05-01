# Chapter 26 — Designing, Reporting, and Critiquing Electron Microscopy Experiments

## Title options

1. **Closing the Loop: Methods, Figures, Critique**
2. **Writing the Methods Section: How to Make Your EM Defensible**
3. **From Image to Argument: Reporting and Reading EM**

## TL;DR

A defensible EM result requires a defensible methods section, defensible figures, and a habit of critiquing both your own and others' published work. This chapter is the final discipline: how to design experiments to produce reportable data, how to write methods sections that name every consequential parameter, and how to read others' figures with the skepticism the techniques demand.

---

## 1. Chapter Opening

A reviewer reads a paper claiming a novel imaging technique that resolves single iron atoms on a graphene support. The paper has three figures. Figure 1 is the headline: a HAADF-STEM image showing bright dots labeled as Fe atoms. Figure 2 is an EDS spectrum from one of the dots. Figure 3 is a histogram of dot diameters.

The reviewer reads the methods section. *"Imaging at 80 kV in STEM mode."* That's the entire methods sentence on imaging. No working distance, no aperture, no detector specifications, no convergence angle. The figure caption: *"Bright dots represent Fe atoms."* No scale bar referenced explicitly. The histogram methods: *"Diameters were measured manually using ImageJ."* No N stated.

The reviewer flags every missing piece. The authors revise: methods section now four paragraphs, one per technique, with every parameter named. Caption now states scale, magnification, dose. Histogram methods: 152 atoms measured across 47 micrographs, mean ± SD reported.

The reviewer accepts the paper. The reader who picks it up six months later can reproduce the imaging conditions, reconstruct the analysis, and verify (or contest) the conclusions. The methods section is what made the paper defensible.

This is what Chapter 26 does. By the end you can write a methods section that holds up to skeptical reading, prepare figures that document your work without overselling, and critique published EM critically.

### Learning objectives

By the end of this chapter you can:

- **Design** an EM experiment to produce reproducible, reportable data.
- **Write** a complete methods section naming every consequential parameter.
- **Prepare** figures with scale bars, captions, and quantitative measurements.
- **Critique** a published EM figure for completeness and reproducibility.
- **Avoid** common pitfalls: over-claimed resolution, cherry-picked images, missing controls.

### Prerequisites

Chapters 4-25. This is the final chapter; the reader is assumed to know all the techniques and have practiced multi-technique workflows.

### Why this chapter matters

EM data is published in figures and methods sections. Reviewers and readers judge the work primarily through these. A weak methods section can sink a strong result; a strong methods section can vindicate a defensible result against tough critique.

---

## 2. Designing the experiment for reportable data

The question this section answers is: what should you plan into an EM experiment to make sure the data is reportable later?

### Mechanism — five planning principles

**1. State the research question with a verb.** Without a clear question, the design drifts. Write the question as a sentence with a verb before the first session.

**2. Specify what the figure will show.** Before acquiring data, sketch the figure you want to publish. What needs to be in the image? At what magnification? What scale bar? What caption?

**3. Plan for replicates.** Single images are anecdotes. Quantitative measurements require population statistics: typically N≥30 for histograms, N≥100 for distributions, N≥1000 for SPA-style work.

**4. Plan controls.** What's the negative control (what should NOT be present)? What's the positive control (what's a known good result)? What's a complementary technique that would cross-check? Plan these into the session.

**5. Document everything.** Take notes during the session, not after. Time-stamp each acquisition. Note the parameters that changed between images. Save raw data with metadata embedded.

### Trade-off

Planning optimizes for **defensible reporting at the cost of session efficiency**. A 30-minute "exploratory" session producing one image is faster than a 4-hour systematic session producing replicate measurements. The reportable data justifies the longer session.

### Worked example: planning for a nanoparticle paper

**Problem.** A graduate student wants to publish characterization of new gold nanoparticles. Goals: confirm shape (assumed spherical), measure size distribution, show one HRTEM lattice image.

**Plan.**
- **Sample preparation:** drop-cast suspension on TEM grid. Three independent grid preps. Dry. No staining or coating.
- **Imaging session:**
  - Survey at 5,000× — confirm dispersion across multiple grid squares.
  - Acquire at 50,000× — at least 200 particles for size measurement (manual or software).
  - Acquire at 500,000× — HRTEM lattice fringes on representative particle.
  - Save methods log: kV, current, detector, working distance, aperture, dwell, N particles, dates.
- **Cross-checks:** SEM at 5 kV for surface morphology; SAED on a single particle for crystallinity confirmation.
- **Population statistics:** 200+ particles across 47 random fields; histograms of equatorial diameter.
- **Figures:** 3 figures planned — survey TEM, size distribution histogram, HRTEM lattice.

This level of planning takes a few hours of preparation. The session is more efficient because the operator knows what to acquire. The published paper is defensible.

### What Goes Wrong Here

- **Reactive imaging.** Acquiring whatever looks interesting without a plan. Result: 50 images that don't combine into a publishable figure.
- **Single-image evidence.** N=1 measurements presented as definitive. Result: reviewer rejection.
- **Missing controls.** Result: claims unfalsifiable in print.

---

## 3. Writing the methods section

The question this section answers is: what must a methods section name for the paper to be defensible?

### Mechanism — the 12-element checklist

A complete EM methods section names:

1. **Sample preparation.** Every step from acquisition to TEM grid: fixation, dehydration, embedding, staining, coating, polishing, FIB lift-out — whatever applies. Concentrations, times, temperatures.

2. **Instrument identification.** Make and model (e.g., "JEOL JEM 1010" or "FEI Tecnai G2"). Software for acquisition.

3. **Operating voltage.** kV.

4. **Detector(s) used.** SE, BSE-scintillator, in-lens TTL, BSE-semiconductor (sum or difference mode), HAADF, EDS, EELS — name explicitly which one produced which image.

5. **Working distance** (SEM) or **camera length** (TEM diffraction).

6. **Aperture size.** Both condenser and objective; physical diameter or selected setting.

7. **Beam current** or spot size. For analytical work especially.

8. **Magnification range.** "Images acquired at magnifications from 5,000× to 500,000×" or per-figure specifications.

9. **Acquisition parameters.** Frame integration, scan rate, dwell time, total exposure time. For DED: frames per second, total frames, motion correction algorithm.

10. **Counting / statistics.** N particles measured, frame averages, classification scheme, software for analysis.

11. **Software.** Acquisition software, image analysis software (ImageJ, Fiji, Gatan DigitalMicrograph, RELION, etc.), reconstruction software (IMOD, etc.).

12. **Specific parameters for specific techniques.**
    - **EDS:** dead time, counting time, detector solid angle, sample tilt.
    - **EELS:** energy dispersion, exposure time, monochromator state.
    - **Tomography:** tilt range, step size, alignment fiducials.
    - **SPA:** particle count, classification scheme, FSC criterion, software pipeline.

A typical published EM methods section runs 1-3 paragraphs per primary technique. Multi-technique workflows have 3-6 paragraph methods sections.

### Trade-off

Detailed methods sections optimize for **reproducibility at the cost of word count**. Some journals impose word limits that compress the methods. The supplementary materials section is now standard for the full version; main-text methods can summarize.

### Worked example: a complete methods sentence for HAADF imaging

**Bad:** "*Images acquired in HAADF mode at 200 kV.*"

**Good:** "*HAADF-STEM images were acquired on an FEI Titan G2 (200 kV) using a 50 mrad inner-collection-angle annular detector. Probe current was 30 pA; convergence angle 22 mrad; pixel dwell 16 μs; scan rate 1024 × 1024 pixels per frame at 2 fps. Images shown represent single frames; no frame averaging applied. Drift correction was performed using the FEI software's built-in cross-correlation algorithm.*" [verify all numerics]

The "Good" version has 8 specific parameters. Each one is consequential. Each one must be matched if a different lab wants to reproduce.

### What Goes Wrong Here

- **Voiced as if "obviously the standard."** Sentences like "imaged at standard conditions" tell the reader nothing. Standards vary by lab.
- **Hidden in supplementary.** Critical parameters buried in supplements; reviewers don't always find them.
- **Software versions unstated.** Same algorithm can produce different results with different software versions; the version matters.

---

## 4. Preparing figures

The question this section answers is: how should EM figures look in a publication?

### Mechanism — five figure-quality requirements

**1. Scale bars.** Every figure with quantitative spatial information has a scale bar. The scale bar is in the image, white-on-dark or black-on-light, sized appropriately.

**2. Captions.** Each figure caption states what is shown, the technique used, the operating conditions, and the takeaway. Avoid "interesting" or "remarkable" — let the data speak.

**3. Annotations.** Arrows, scale bars, region labels, but with restraint. The image should be readable without annotations; annotations should add information rather than clutter.

**4. Multiple panels for cross-technique evidence.** A figure that shows the same specimen in BF, DF, and EDS makes the multi-technique discipline visible.

**5. Image processing transparency.** Brightness, contrast, gamma, and any digital manipulation should be stated in the caption or supplementary materials. Especially: false color (yes or no?); cropping (specify); enhancement (specify and document).

### Image processing ethics

Some standards [verify all]:

- **Linear adjustments** (brightness, contrast, gamma) applied uniformly to a whole image are conventionally allowed without disclosure.
- **Cropping** is allowed but should be disclosed if it changes the represented field.
- **Pseudo-coloring** or **false coloring** applied to a single channel is allowed if disclosed.
- **Cherry-picking** (showing the best image without statistical context) is not.
- **Deletion of features** (cleaning up "artifacts" without disclosure) is misconduct.
- **Image splicing** (combining multiple images into one without disclosure) is misconduct.

The line is: any change that could mislead a reader about what was actually present in the specimen requires disclosure. When in doubt, disclose.

### Trade-off

Figure preparation optimizes for **clarity and honesty at the cost of "polished" appearance**. A figure that looks slightly less impressive but is fully documented is more publishable than a polished figure missing critical context.

### What Goes Wrong Here

- **Missing scale bars.** Common in early-career work. Default fail at peer review.
- **Cherry-picked images.** "Representative" images that don't represent.
- **Over-processed images.** Uniformly enhanced contrast that artificially clarifies real data; gamma manipulation hiding noise; false colors distinguishing channels but obscuring real features.

---

## 5. Critiquing published EM

The question this section answers is: how do you read published EM figures critically?

### Mechanism — six diagnostic questions

For any published EM figure, ask:

1. **What technique is named?** SEM, TEM, STEM, EELS, etc. Is the technique-question match plausible?

2. **What detector is named?** This often determines what the image actually shows.

3. **What operating conditions are stated?** kV, working distance, aperture, magnification.

4. **What sample prep is described?** Many artifacts originate in prep; the prep description is half the credibility.

5. **What controls and replicates are reported?** Single-image evidence vs. statistical evidence.

6. **What artifact-resistance is documented?** Cross-checks, alternative techniques, reproducibility.

### Worked example: reading a published cryo-EM paper

**Excerpt of paper:** *"Cryo-EM single-particle reconstruction of [protein X] at 2.8 Å resolution from 250,000 particles using Relion 4.0. Vitrified using Vitrobot at 4°C. Images acquired on a Titan Krios at 300 kV equipped with a Falcon 4 detector. Total dose 50 e/Å² distributed across 40 frames at 0.05 s per frame. Motion correction: MotionCor2. CTF estimation: CTFFIND4. FSC criterion: 0.143."*

**Diagnostic questions answered:** Technique, instrument, voltage, detector, dose, frame structure, motion correction, CTF estimation, FSC criterion all stated. The methods section is reproducible at the level of process. Resolution claim is FSC-0.143-based, the field's standard.

**What's not stated:** Particle distribution (homogeneous? heterogeneous classes?); 3D classification scheme; preferred-orientation analysis. These would be in supplementary materials of a typical cryo-EM paper. Reading the supplements is essential.

### Trade-off

Critical reading optimizes for **interpretive integrity at the cost of time per paper**. Reading every paper at this level slows down literature review. A working researcher reads carefully when the paper's claims affect their own work, more skimming for context.

### What Goes Wrong Here

- **Accepting claims at face value.** The paper says "atomic resolution"; the FSC may say 4.5 Å, which is not atomic. Always check.
- **Missing the supplements.** Many papers' real methods are in supplements. Read them.
- **Lacking baseline knowledge.** A reader without grounding in the techniques may not know what's missing.

---

## 6. Synthesis: a defensible EM publication

A defensible EM publication has all the following:

1. **Clear research question.** Stated in the introduction.
2. **Multi-technique workflow.** Where appropriate, multiple techniques providing convergent evidence.
3. **Reproducible methods section.** Every parameter named; every step documented; software and versions stated.
4. **Honest figures.** Scale bars, captions naming techniques, no over-processing.
5. **Statistical evidence.** Population data for measurements; replicates for claims.
6. **Cross-checks.** Alternative techniques or controls that test artifact hypotheses.
7. **Acknowledgment of limitations.** What the data cannot show; what alternative interpretations exist.
8. **Available data.** Raw data and code where applicable; supplementary materials for full disclosure.

The discipline applies equally to laboratory notebooks, theses, conference posters, and journal papers. The audience changes; the standards do not.

The wonder. The same EM techniques that 50 years ago produced descriptive electron-microscopy papers now produce papers with quantitative cross-technique evidence at near-atomic resolution. The standards have risen because the techniques have risen. A 1970s paper claiming a novel ultrastructural feature might be accepted on the basis of one carefully captioned image; a 2020s paper requires multi-technique cross-checks, statistical replicates, FSC criteria, and DED-based motion correction. The discipline has tightened because the technology has matured. The microscopist who completes this textbook has been trained to the modern standard.

---

## 7. Pre-lab Checklist (Lab 26 — methods-section practice)

**By the end of this chapter, you should be able to:**

- Write a complete methods section for an EM session.
- Prepare publication-quality figures with scale bars and captions.
- Critique a published EM paper for completeness and rigor.

**Bring to lab:**

- This chapter, especially Sections 3 and 4.
- A draft methods section from your own work or from a peer's draft.

**Expect on the floor:**

- Peer review of methods sections — what's missing, what's underspecified.
- Discussion of figure preparation and ethical reporting.
- Critique of a published EM figure as a class exercise.

---

## 8. Quick-Reference Table

| Methods element | What to include |
|---|---|
| Sample prep | Every step; concentrations; times; temperatures |
| Instrument | Make, model, software |
| kV | Numerical |
| Detector | SE / BSE / in-lens / HAADF / EDS / EELS |
| Working distance | mm |
| Aperture | Physical diameter (μm) |
| Beam current | pA or nA |
| Magnification | Range or per-figure |
| Acquisition | Frame rate, integration, dose |
| Statistics | N particles, software for analysis |
| Software | Acquisition + analysis, with versions |
| Specific to technique | EDS dead time; EELS dispersion; tomography tilt range; SPA particle count |

| Figure element | Standard |
|---|---|
| Scale bar | Required, in image |
| Caption | Technique, conditions, takeaway |
| Annotations | Restrained; add information |
| Multi-panel | For multi-technique evidence |
| Image processing | Disclosed if more than uniform linear |

| Critique question | Look for in paper |
|---|---|
| Technique-question match | Methods section first |
| Detector identification | Caption or methods |
| Operating conditions | Methods or supplement |
| Sample prep | Methods + supplement |
| Statistical replicates | Results figures + methods |
| Artifact-resistance | Cross-checks or alternative techniques |

---

## 9. Exercises

### Warm-up

**Exercise 26.1 (LO: identify methods gap).**
A methods section reads: "Cryo-EM at 300 kV." List five additional pieces of information needed for reproducibility. Difficulty: easy.

**Exercise 26.2 (LO: plan replicates).**
For a particle-size measurement, what is the minimum N to claim a meaningful distribution? Justify in one sentence. Difficulty: easy.

**Exercise 26.3 (LO: identify figure problem).**
A TEM figure shows a single highlighted feature with no scale bar. What's missing? Difficulty: easy.

### Application

**Exercise 26.4 (LO: write methods).**
Write a complete methods section for the following imaginary session: SEM at 15 kV, FEI Quanta 650, BSE detector, working distance 10 mm, aperture 60 μm, 5,000× to 50,000× magnification, dwell 5 μs, 200 particles measured for size distribution, ImageJ for analysis. Difficulty: medium.

**Exercise 26.5 (LO: critique a published methods section).**
A paper's methods section reads: "*All EM imaging was performed using a high-resolution TEM. Images acquired at standard conditions and processed in ImageJ.*" List six specific deficiencies. Difficulty: medium.

**Exercise 26.6 (LO: design statistics).**
A research group claims that the mean nanoparticle diameter is 53.2 ± 4.1 nm. What information should accompany this claim for credibility? Difficulty: medium.

**Exercise 26.7 (LO: prepare figure).**
You have an SEM image at 50,000× magnification, 256 mm wide, intended for publication. Specify: scale bar dimensions; caption format; magnification scale; whether to include annotations. Difficulty: medium.

### Synthesis

**Exercise 26.8 (LO: critique end-to-end).**
Find a published EM paper in your research field. Critique it on: (a) clarity of research question; (b) appropriateness of techniques; (c) completeness of methods; (d) figure quality; (e) acknowledgment of limitations. Identify one area where the paper could be improved. Difficulty: hard.

### Challenge

**Exercise 26.9 (open-ended).**
Take a draft methods section you have written for a lab report or thesis. Apply the 12-element checklist. Identify which elements are missing or underspecified. Revise to a fully complete methods section. Difficulty: open-ended.

---

## 10. Summary

You walked into this chapter with the techniques individually mastered, multi-technique workflows planned, and artifacts recognized. You walk out with the discipline to make all of that publishable: methods sections that reproduce, figures that document, claims that cross-check, statistics that support.

The one idea that matters most: a defensible EM result requires defensible reporting. The methods section is the bridge between the operator's careful work and the reviewer's careful reading.

The common mistake to watch for is undocumented work. Beautiful images without complete methods sections fail at peer review. Complete methods sections without beautiful images may still pass.

The Feynman test: explain to a labmate, without using the word "reproducibility," why a methods section is the hardest part of an EM paper to write.

---

## 11. Connections — Closing the Book

You have now completed all 26 chapters. The textbook covered:

- Foundations of electron microscopy (Chapters 1-3).
- Scanning electron microscopy in depth (Chapters 4-11).
- Transmission electron microscopy in depth (Chapters 12-19).
- Sample preparation for both biological (Ch. 20-21) and inorganic (Ch. 22) specimens, plus cryo-EM (Ch. 21).
- Synthesis: artifact recognition (Ch. 23), technique selection (Ch. 24), applications (Ch. 25), and reporting/critique (Ch. 26).

Two appendices cover lab safety (A) and TEM supplies (B).

You are now prepared to:
- Operate SEM and TEM independently.
- Choose appropriate techniques for research questions.
- Plan and execute multi-technique workflows.
- Recognize and mitigate artifacts.
- Read and critique published EM literature.
- Write defensible methods sections.

The textbook closes here. The lab work continues. May your future microscopy be as careful as the methods sections you now write.

---

**What would change my mind:** evidence that EM publication standards have universally fallen relative to the field's technical capability. The opposite seems true — standards have risen with technology — but the empirical record is mixed across journals and disciplines.

**Still puzzling:** the practical question of how much information to put in a methods section vs. supplementary materials varies by journal and field. Some journals demand more in main text; others push everything to supplements. The convention is unstable.

**Tags:** `methods-section`, `figure-preparation`, `critique`, `publication-standards`, `EM-reporting`

---

### Note to the professor

This chapter closes the book. The voice anchoring is consistent. The synthesis nature means few `[verify]` markers; specific examples (Falcon 4 detector, RELION versions, etc.) are publication conventions and should be checked against current practice.

Voice anchoring: anchored. Reviewer chapter opening (one scene only). Capability ending. Wonder paragraph closing the synthesis section: the standards have risen with the technology. Length ~4500 words.

The course chapter completes the book; the appendices follow.
