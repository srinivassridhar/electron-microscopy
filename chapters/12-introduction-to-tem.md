# Chapter 12 — Introduction to Transmission Electron Microscopy

## Title options

1. **Looking Through, Not at: First Encounter with TEM**
2. **The Electron Microscope That Sees Inside**
3. **From Bulk to Thin Section: Why TEM Resolves Atoms**

## TL;DR

A transmission electron microscope shines a high-energy electron beam through a specimen thin enough for the beam to penetrate, and forms an image from what passes through. The cost is a thin-specimen requirement that no other technique imposes; the reward is atomic-resolution imaging of internal structure.

---

## 1. Chapter Opening

A graduate student stands at the JEOL JEM 1010 transmission electron microscope and slides a copper grid into the holder. On the grid, a small carbon film bears a single ultrathin section of mouse cardiac tissue, sectioned at 70 nm by ultramicrotome that morning. The student inserts the holder into the column airlock; pumps activate; thirty seconds later the column is at vacuum, the holder seats into the stage, the gun comes on, the screen glows. The student turns the magnification to 50,000× and sees, in real time, the densely-packed mitochondrial cristae inside a single cardiac muscle cell. Each crista — a fold of inner membrane where the electron transport chain is anchored — appears as a dark line on a lighter cytoplasmic background, sharp at the 10-nm level. The student is looking *inside* the cell. Not at its surface, the way SEM did. Through it.

That is what TEM does and what SEM cannot. SEM scans a focused probe across a bulk surface and reads what comes back; TEM passes a wide beam through a thin specimen and reads what gets through. The difference is more than a technical detail — it is a different mode of microscopy with different specimen requirements, different physics, different image content, and different artifacts. The same specimen can yield SEM images of the surface and TEM images of the interior, but only after distinct preparation pipelines and at distinct instruments. Most working scientists in materials, biology, and nanomedicine use both.

By the end of this chapter you can state what a TEM is at the level of components and physics, recognize TEM images as projections through a specimen rather than reflections from a surface, and identify the questions that TEM answers better than any other technique. You will not yet be aligning the column or interpreting diffraction patterns; that is Chapters 13–17.

### Learning objectives

By the end of this chapter you can:

- **Distinguish** TEM from SEM by image-formation mechanism, specimen requirement, and information content.
- **Explain** why electrons must pass through a thin specimen to form a TEM image.
- **Identify** the principal interactions of beam electrons with the thin specimen (direct beam, elastic scattering, inelastic scattering).
- **Recognize** the limitations of TEM as a 2D projection technique imaging from inside a sample.
- **Choose** TEM versus SEM versus optical microscopy for a given research question.
- **Read** key milestones in TEM historical development.

### Prerequisites

Chapter 1 (TEM/SEM orientation), Chapter 2 (electron wavelength, resolution, aberrations), Chapter 6 (beam-specimen interactions in SEM — much of which carries over). The TEM-specific material starts here.

### Why this chapter matters

The next eight chapters of the book are TEM, including diffraction, contrast, advanced modes, EELS, tomography, and biological/inorganic prep. Without the orientation in this chapter, those subsequent chapters lose their anchor.

---

## 2. The transmission imaging contract

The question this section answers is: what does it mean to image *through* a specimen, and what does that require of the specimen?

### Mechanism — wide beam, thin sample, magnified projection

A transmission electron microscope shines a wide, coherent electron beam onto a thin specimen and uses post-specimen lenses to magnify the resulting transmitted image. The four key elements:

1. **High-energy beam.** Typical TEM beam energies are 60 to 300 keV, with 80–200 kV common for biological work and 200–300 kV common for high-resolution and atomic work. Higher kV gives shorter wavelength (Chapter 2): at 200 kV, $\lambda \approx 2.5$ pm. The wavelength advantage is what enables atomic resolution.
2. **Thin specimen.** The specimen must transmit a useful fraction of the beam — typically <100 nm thick, often <50 nm for high-resolution imaging. Below the thinness threshold, electrons pass through with predictable scattering; above it, multiple scattering and absorption swamp the signal. Sample preparation for TEM is a major undertaking (Chapters 20–22).
3. **Wide-field illumination.** Unlike SEM's focused-probe scanning, TEM illuminates the whole imaging area at once. The condenser lens system spreads the beam to flood-illuminate a region the operator selects.
4. **Post-specimen magnification.** Below the specimen, a series of lenses — objective, intermediate, projector — magnifies the transmitted image and projects it onto a fluorescent viewing screen or, in modern instruments, directly onto a digital camera (Chapter 13).

Three things happen to a beam electron as it traverses a thin specimen:

- **Direct beam.** Electrons pass through without significant scattering, between the atoms or through low-density regions.
- **Elastic scattering.** Electrons interact with the atomic nuclei (and the screening electron clouds) and are deflected by some angle, conserving kinetic energy. *Elastic*, from the Greek *elastikos*, "able to spring back" — same energy, new direction.
- **Inelastic scattering.** Electrons interact with bound electrons in the atom, transferring some energy and producing X-rays, plasmons, or excited valence electrons. The beam electron loses energy in proportion to what it transferred.

The image you form depends on which of these you select for collection. In **bright-field mode** (the default, Chapter 14), the objective aperture passes only the direct beam and excludes the scattered electrons; the image is bright where electrons passed unscattered, dark where they scattered. In **dark-field mode**, the aperture excludes the direct beam and passes scattered electrons; bright where scattering occurred. In **high-resolution mode**, multiple beams interfere to form lattice fringes — phase contrast (Chapter 16).

### Why the specimen has to be thin

A 200 kV electron has enough energy to travel several micrometers in most materials before stopping. So why is the TEM specimen requirement <100 nm?

The answer is image quality, not penetration. Beyond the thin-specimen regime:

- **Multiple scattering.** Each beam electron may scatter many times. The image becomes a diffuse, low-contrast smear because the directions are randomized.
- **Mass-thickness contrast saturates.** At high thickness, absorption is total and contrast is set by the thickness rather than by structural features.
- **Image resolution degrades.** The depth of the specimen blurs the image's lateral resolution, since features at different depths superimpose.

The 100-nm limit is empirical. For simple imaging, 100–200 nm works. For high-resolution work, <50 nm. For atomic-resolution lattice fringes, <10 nm. The thinness requirement is the central engineering challenge of TEM specimen preparation (Chapters 20 and 22).

### Trade-off

TEM trades **specimen flexibility for resolution and information depth**. SEM accepts bulk samples; TEM does not. The reward: 0.1–0.2 nm resolution (HRTEM) versus 1–10 nm in routine SEM. Internal structure visible directly versus surface-only in SEM.

### Worked example: choosing between TEM and SEM

**Problem.** A biology lab has fixed liver tissue and three questions: (a) gross morphology of the tissue at the cellular scale, (b) location and size of mitochondria within hepatocytes, (c) crystallinity of stored ferritin iron oxide.

**Reasoning.**
- (a) Cellular-scale morphology is a few μm; SEM does this with much less prep effort. Section the tissue with a vibratome, fix, dehydrate, dry, sputter-coat. Image at 5 kV. Done in a day.
- (b) Mitochondria are ~1 μm with 10 nm cristae. SEM can image the surface of the tissue but not see inside cells. TEM, with ultrathin sections (~70 nm), shows mitochondrial cristae directly. Standard biological TEM prep (Chapter 20) takes 4–5 days.
- (c) Crystallinity of iron oxide cores requires diffraction or HRTEM lattice imaging. TEM only.

**Answer.** SEM for (a), TEM for (b) and (c). One specimen, three questions, two instruments, two prep pipelines.

**Sanity check.** Standard biology workflows use both SEM and TEM for tissue characterization, with SEM for tissue-scale morphology and TEM for sub-cellular ultrastructure.

**General lesson.** The same specimen often answers different questions in different microscopes. Plan the prep and the instrument for each question separately.

### What Goes Wrong Here

- **Trying to image a too-thick TEM specimen.** Image is dim and low-contrast; resolution is degraded. Diagnostic: at 200 kV, if you cannot see structure clearly at moderate magnification, the specimen is probably >300 nm thick. Re-thin or pick a different region.
- **Imaging a wrinkled or folded section.** Wrinkles double the local thickness and produce dark bands. Recognition: dark stripes in otherwise uniform regions. Mitigation: pick a flat region of the section.
- **Confusing TEM 2D projection with 3D structure.** A particle that looks spherical in TEM might be a disk seen edge-on. The 2D shadow does not encode the third dimension. Mitigation: tilt the specimen and re-image (Chapter 19 tomography).

---

## 3. What TEM tells you that SEM cannot

The question this section answers is: what specifically does the TEM see that the SEM cannot?

### Three kinds of information

Per the week-10 source, TEM provides three categories of information:

1. **Morphology.** The shape and arrangement of features inside the specimen at high resolution. Examples: mitochondrial cristae, nanoparticle internal structure, polymer phase separation, semiconductor multilayer cross-sections.
2. **Structure.** Crystallinity, defects, grain boundaries, dislocations, twins, stacking faults — visible in diffraction-contrast imaging (Chapter 16) or high-resolution lattice imaging (Chapter 17). Diffraction patterns themselves are direct images of the reciprocal lattice (Chapter 15).
3. **Chemistry.** Elemental composition via EDS (same as SEM) and via EELS (electron energy-loss spectroscopy, Chapter 18 — a TEM-specific technique with light-element sensitivity beyond EDS).

The combination — atomic-resolution morphology, direct structural identification by diffraction, elemental analysis at near-atomic spatial resolution — is what makes TEM the workhorse of materials characterization at the nanoscale.

### What TEM is good at

- **Resolution at high magnification.** Modern TEMs resolve below 0.1 nm and can magnify by more than $10^6$. Atomic columns in a crystalline sample appear as discrete dots when imaging at lattice resolution.
- **Internal structure.** TEM looks *through* the specimen; SEM looks *at* the surface. Mitochondria, nanoparticle interiors, layered semiconductor stacks, polymer micelles — only TEM sees the inside directly.
- **Diffraction.** Selected-area electron diffraction (Chapter 15) gives single-crystal patterns from regions as small as 100 nm, revealing crystallographic structure and orientation.
- **Analytical measurements.** EDS for elemental composition; EELS for elemental + chemical-bond information; STEM for high-resolution mapping (Chapter 17).

### What TEM is not good at

- **Sampling.** The price of high resolution is small field of view. A 50,000× TEM image shows ~5 μm × 5 μm; a 5,000× SEM image shows ~50 μm × 50 μm; an optical micrograph shows millimeters. The TEM is not the right tool for surveying a specimen — start with eyes, optical microscopy, or SEM. Then zoom in with TEM where the question demands it.
- **Reading 2D projections of 3D specimens.** Every TEM image is a projection through the specimen's full thickness. Particles can appear superimposed; depth information is averaged. Tomography (Chapter 19) addresses this with a tilt series, but a single image cannot.
- **Beam damage.** Ionizing radiation breaks bonds in soft materials and can drive atomic displacement in many inorganic materials at high kV. Polymers and biological samples especially suffer. Low-dose TEM (Chapter 19) and cryo-EM (Chapter 21) are responses to this constraint.
- **Specimen preparation.** A major limitation. Thinning a bulk specimen to <100 nm is laborious; the prep pipeline (Chapters 20 and 22) often exceeds the imaging time.

### Trade-off

TEM optimizes for **information depth and resolution at the cost of sampling, prep effort, and 2D projection ambiguity**. The cost-benefit is favorable when the question requires resolution or internal structure. It is unfavorable when the question is about a large area or a near-native unprepared specimen.

### Worked example: nanoparticle question for TEM

**Problem.** A graduate student has lipid-coated polymer nanoparticles, ~80 nm diameter, intended for drug delivery. SEM showed they are spherical and monodisperse. Open questions: (a) is the lipid coating uniform across the surface, (b) what is the thickness of the lipid layer, (c) is the polymer core hollow or solid?

**Reasoning.**
- (a) Surface uniformity at 80 nm scale: SEM can do this, but the lipid coating is too thin (a few nm) to resolve cleanly with SEM. TEM at 200 kV gives better surface-feature resolution and can directly image the lipid layer in cross-section.
- (b) Lipid layer thickness ~3–5 nm: requires sub-nanometer resolution. TEM only.
- (c) Hollow vs. solid: requires looking *through* the nanoparticle. TEM by definition. Mass-thickness contrast (Chapter 16) shows hollow vs. solid as a doughnut-vs-uniform-disk pattern.

**Answer.** All three answered by TEM; none by SEM alone.

**General lesson.** When the question is internal-structure or sub-nanometer, TEM is the technique. When it is surface-or-external, SEM is faster and gentler.

### What Goes Wrong Here

- **Insufficient sampling.** The student looks at one TEM image of one nanoparticle and concludes the population is hollow. One field of view is not statistical evidence; an SEM survey of 200 particles plus TEM confirmation of representative subset is the credible approach.
- **Beam damage during long imaging.** Polymer nanoparticles burn under prolonged high-kV exposure. Recognition: features change shape between successive images. Mitigation: low-dose protocols, fast imaging, fresh fields.

---

## 4. A brief TEM history

The same physics that gave SEM gave TEM, and the timelines are tightly coupled. Per the week-10 source:

- **1897** J. J. Thompson — discovers the electron.
- **1924** Louis de Broglie — wavelength of moving particles ($\lambda = h/mv$). At 60 kV, $\lambda = 0.005$ nm. The theoretical prediction that electrons could resolve far below visible light.
- **1926** Hans Busch — magnetic and electric fields act as lenses for electrons. The optics that would make TEM possible.
- **1929** Ernst Ruska — Ph.D. thesis on magnetic lenses.
- **1931** Knoll & Ruska — first electron microscope built.
- **1931** Davisson & Calbrick — properties of electrostatic lenses.
- **1934** Driest & Müller — surpass resolution of the light microscope.
- **1938** von Borries & Ruska — first practical TEM (Siemens), 10-nm resolution.

Two milestones bear emphasis. **1924** is the wavelength insight that made the whole project possible. **1938** is the first practical instrument with 10-nm resolution. Fourteen years from theory to working microscope. Ruska shared the 1986 Nobel Prize in Physics for the work, more than fifty years after the first instrument [verify: Nobel year and citation].

The wonder. From de Broglie's 1924 theoretical insight that an electron at 60 kV has a wavelength of 5 pm — a hundred times shorter than the spacing between adjacent atoms in a crystal — to the 1938 demonstration of 10-nm resolution to today's atomic-resolution imaging, the path goes from a theoretical curiosity about quantum particles to a routine tool that resolves the columns of atoms in a silicon crystal. The wavelength was always there; the engineering caught up.

---

## 5. Synthesis: where TEM lives in the technique landscape

A research question is *well-posed for TEM* when the answer requires:

- **Sub-nanometer resolution**, especially atomic-resolution lattice imaging.
- **Internal structure** of a specimen — through-the-thickness information rather than surface-only.
- **Crystallographic structure** by electron diffraction.
- **Defect characterization** — dislocations, stacking faults, grain boundaries — visible in diffraction contrast.
- **Light-element analytical chemistry** by EELS (Chapter 18).
- **3D reconstruction** by tomography (Chapter 19).

A research question is *poorly posed for TEM* when it requires:

- **Surface morphology of a bulk specimen** — SEM does this faster and easier.
- **Macroscale or millimeter-scale views** — TEM's field of view is too small.
- **Imaging of unprepared, hydrated, or living specimens** — TEM specimen prep is destructive; cryo-EM (Chapter 21) is a partial workaround.
- **Real-time process imaging** — TEM allows some in-situ work but is generally a static-imaging instrument.

The decision is: *what does this question require?* If sub-nanometer-internal, TEM. If surface or scale, SEM. If both, both.

**Putting it all together (worked scenario).** A nanomedicine PI brings cellulose nanocrystals decorated with gold nanoparticles for bioimaging. The SEM session of Chapter 11 gave: shape, size distribution, gold particle attachment confirmation, and elemental verification. Open questions for TEM:

- (a) Are the gold particles attached to the surface only, or are some embedded in the cellulose?
- (b) What is the gold particle size distribution at sub-nanometer resolution?
- (c) Are the gold particles crystalline (FCC gold) and what is their orientation distribution?
- (d) What is the cellulose-gold interface like at the atomic scale?

Each question pushes deeper than SEM can go. TEM at 200 kV, with conventional bright-field for (a) and (b), HRTEM for (b) refinement and (d), and selected-area diffraction for (c). One specimen, four questions, full session: half a day on the TEM after another half a day prepping the grid.

---

## 6. Pre-lab Checklist (Lab 12 — TEM tour and orientation)

**By the end of this chapter, you should be able to:**

- State what a TEM is and what it requires of a specimen.
- Distinguish bright-field from dark-field imaging conceptually.
- Choose between TEM, SEM, and optical microscopy for a given research question.

**Bring to lab:**

- This chapter, especially Sections 2 and 3.
- A research question, however rough — a sample type and what you want to know about it.
- Closed-toe shoes; nitrile gloves available at the door.

**Expect on the floor:**

- A working TEM (the source notes the JEOL JEM 1010 at the BEMC), already at vacuum and beam-on.
- Specimen-grid loading demonstration with the airlock and holder.
- A first look at a real TEM image — likely a biological section showing cells with mitochondria — at 5,000× and 50,000× magnification.

---

## 7. Quick-Reference Table

| Feature | SEM | TEM |
|---|---|---|
| Image-formation | scanned focused probe, point-by-point | wide beam through thin specimen, projected |
| Specimen | bulk, conductive or coated | thin (<100 nm), often thinner |
| Beam energy | 0.1–30 keV | 60–300 keV |
| Resolution | 1–10 nm (best ~0.4 nm FE-SEM) | 0.1–0.2 nm (HRTEM 0.05 nm) |
| Magnification | 10×–1,000,000× | 1,000×–1,500,000× |
| Information | surface, composition | internal structure, crystallography, chemistry |
| Sampling | small (~10² to 10⁻² mm² fields) | very small (~10⁻⁴ mm² fields) |
| Prep | mount, coat (insulators) | thin section, fix, embed (biological) or polish/ion-mill (inorganic) |

| Beam–specimen interaction | Result | Used for |
|---|---|---|
| Direct beam (unscattered) | passes through | bright-field imaging |
| Elastic scattering | direction change | dark-field imaging, diffraction |
| Inelastic scattering | energy loss | EDS, EELS, beam damage |

---

## 8. Exercises

### Warm-up

**Exercise 12.1 (LO: distinguish TEM from SEM).**
List three differences between SEM and TEM in image-formation mechanism. Difficulty: easy.

**Exercise 12.2 (LO: explain thin-specimen requirement).**
Why must a TEM specimen be thinner than 100 nm typically, but not necessarily thinner than what an electron beam at 200 kV can penetrate? Difficulty: easy.

**Exercise 12.3 (LO: identify beam–specimen interactions).**
Match each interaction to the imaging mode: (a) direct beam, (b) elastic scattering at small angles, (c) inelastic scattering at angles characteristic of element. Modes: bright-field, dark-field, EELS. Difficulty: easy.

### Application

**Exercise 12.4 (LO: choose between SEM, TEM, optical).**
For each question, name the technique you would choose first: (a) measure 50 nm gold nanoparticles for size distribution; (b) examine internal structure of a single cardiac myocyte; (c) measure the d-spacing of a single-crystal silicon film; (d) image a fly's compound eye for population study. Difficulty: medium.

**Exercise 12.5 (LO: read TEM image as projection).**
A TEM image at 50,000× shows a ring-like structure with bright center and dark rim, on a uniform substrate. Without using BF/DF terminology, explain in two sentences how the TEM made this image and what the ring might represent. Difficulty: medium.

**Exercise 12.6 (LO: predict prep difficulty).**
A student wants TEM images of: (a) a polished aluminum alloy, (b) fresh liver tissue, (c) a 10 nm gold nanoparticle, (d) a polymer film. Rank the prep difficulty from easiest to hardest. Justify in one sentence each. Difficulty: medium.

**Exercise 12.7 (LO: identify limitation).**
A graduate student claims that one TEM image of a polymer particle proves the particle is monodisperse and spherical. What two limitations of TEM imaging make this claim insufficient? Difficulty: medium.

### Synthesis

**Exercise 12.8 (LO: design SEM+TEM session).**
A nanomedicine lab has cellulose-acetate nanofibers (~50 nm diameter, lengths up to 1 μm) functionalized with antibodies. They want to: (a) confirm the fiber morphology and size, (b) measure the surface antibody coverage, (c) determine whether the fiber polymer is crystalline. Specify an SEM imaging plan and a TEM imaging plan, and explain what each instrument adds that the other cannot. Difficulty: hard.

### Challenge

**Exercise 12.9 (open-ended).**
Find a published paper that uses both SEM and TEM on the same specimen. Read both methods sections. Identify the specific question each instrument answered. List one question that neither answered, and propose which technique (or extension thereof) could answer it. Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter knowing that "there is another electron microscope called TEM." You walk out understanding that TEM passes a wide high-energy electron beam through a thin specimen and reads what comes through, that this requires <100-nm specimens but rewards sub-nanometer resolution and direct internal-structure imaging, and that TEM and SEM answer fundamentally different classes of question on the same specimen.

The one idea that matters most: TEM is *transmission* — through the specimen, not from its surface. The specimen must be thin enough; the image is a projection through the thickness; the resolution can reach atomic dimensions because of high kV and short wavelength.

The common mistake to watch for is assuming a single TEM image proves three-dimensional structure. The 2D projection ambiguity is real and only addressed by tilting (tomography) or complementary imaging (SEM, AFM).

The Feynman test: explain to a labmate, without using the word "transmission," why a TEM specimen has to be much thinner than an SEM specimen.

---

## 10. Connections Forward

Chapter 13 walks the TEM column from gun to camera at the engineering level — gun, condenser, objective, intermediate, projector lenses; the specimen holder and airlock; cameras (CCD, CMOS, direct-detection). Chapter 14 covers image formation — bright-field, dark-field, and the objective aperture's role. Chapter 15 unpacks electron diffraction, the structural-analysis tool unique to TEM. Chapter 16 covers contrast mechanisms; Chapter 17 advanced modes (HRTEM, STEM, HAADF); Chapter 18 EELS; Chapter 19 tomography and low-dose imaging.

The question this chapter raised but did not answer: how does the TEM column actually accomplish wide-beam illumination and post-specimen magnification? Chapter 13 names the components and their interactions.

---

**What would change my mind:** evidence that thin-specimen requirement could be relaxed substantially without sacrificing resolution. High-voltage TEMs at 1–3 MV (rare; mostly historical) extend the limit somewhat but the basic physics holds.

**Still puzzling:** the gap between specimen-prep effort and imaging time in TEM remains substantial. A typical biological TEM session is 10:1 prep-to-imaging at minimum. The empirical evidence that no shortcut exists for high-quality biological TEM continues to drive innovation in cryo-EM and HMDS-style fast prep.

**Tags:** `TEM`, `transmission`, `thin-specimen`, `internal-structure`, `electron-microscopy-orientation`

---

### Note to the professor

`[verify]` markers in this chapter:
- Nobel year for Ruska (1986) and citation.
- Specific historical milestone dates from the source table.

Voice anchoring: anchored. Cardiac-tissue chapter opening (one scene only). Etymology used at "elastic" / "elastikos" referenced by inheritance from Ch. 6. Capability ending. Wonder grounded in numbers (5 pm wavelength at 60 kV; 14 years from theory to instrument; 50 years to Nobel). Length ~5300 words.
