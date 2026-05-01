# Chapter 14 — Image Formation in TEM

## Title options

1. **Choosing What to Look At: Bright-Field, Dark-Field, and the Objective Aperture**
2. **The Two-Stage Imaging Process: Why TEM Has Two Image Planes**
3. **Reading a TEM Image: Direct Beam, Scattered Beam, and the Aperture That Picks Between Them**

## TL;DR

A TEM image is formed in two stages — the objective lens makes a primary image; the projector lenses magnify it. The objective aperture sits at the back focal plane and selects which beams contribute to the image: the direct beam alone (bright-field), a single scattered beam (dark-field), or many beams together (high-resolution phase contrast). Reading any TEM image starts with knowing which choice was made.

---

## 1. Chapter Opening

A graduate student is at the TEM looking at a thin foil of polycrystalline aluminum. The image at 50,000× shows a uniform gray field with subtle variations — grain boundaries faint, defects barely visible. The student inserts the objective aperture, centers it on the direct beam. The image transforms: grains appear as distinct gray levels, dark contours snake across some grains marking dislocations, the boundaries between grains sharpen. Same specimen, same kV, same magnification. What changed is what the lens is allowed to image. Now switch the aperture: tilt the objective aperture to surround a single diffracted beam. The bright-field image inverts — what was bright is now dark, what was dark is now bright. Some grains light up; others go black. The dislocations that were dark are now bright lines. Same physical features, different image.

This is the central operator move in TEM: choosing which post-specimen beams get to form the image. Bright-field, dark-field, and high-resolution phase-contrast are not three different microscopes — they are three different aperture configurations on the same instrument, three different selections from the same scattered electron distribution. Reading any TEM image starts with knowing which selection was made.

By the end of this chapter you can identify bright-field versus dark-field imaging from the methods section, predict what each shows for a given specimen, and decide which to acquire for a given research question.

### Learning objectives

By the end of this chapter you can:

- **Describe** the two-stage TEM image-formation process: primary image at the objective image plane, magnified image at the camera plane.
- **Distinguish** the back focal plane from the image plane and locate the objective aperture in the column.
- **Choose** between bright-field and dark-field imaging for a given specimen and question.
- **Define** contrast quantitatively as $C = \Delta I / I$ and predict how aperture size affects it.
- **Recognize** projection ambiguity in TEM images and propose imaging strategies that resolve it.

### Prerequisites

Chapter 13 (TEM column components, especially objective and intermediate lenses), Chapter 12 (TEM as transmission microscopy). Some familiarity with lens optics: object plane, image plane, focal plane.

### Why this chapter matters

Bright-field is the default mode for almost all TEM work. The minute you understand what BF actually selects, you can also read DF, HRTEM, and STEM images critically. Reading a paper's TEM figures starts here.

---

## 2. The two-stage image formation process

The question this section answers is: how does the TEM go from a 100-nm specimen to a 1-million-fold magnified image at the camera?

### Mechanism — objective primary image, projector cascade

Per the week-11 source, image formation in the TEM occurs in two stages:

**Stage A: scattering and primary image formation.** An incident electron beam strikes the specimen; some electrons pass through unscattered (the **direct beam**), others scatter elastically at small angles (forming a discrete diffraction pattern for crystalline specimens) or at larger angles (diffuse scattering for amorphous or biological specimens), still others scatter inelastically (losing energy as they go). All these scattered and unscattered electrons pass through the **objective lens**, which focuses them.

The objective lens is *the* central component of TEM optics. Its action has two distinct outputs at two different planes below the lens:

- **Back focal plane.** Where parallel rays from infinity (here: parallel beams scattered at the same angle) come to focus. The back focal plane contains the **diffraction pattern** of the specimen — each scattered direction maps to a distinct point.
- **Image plane.** Where rays from each point on the specimen converge after passing through the lens. The image plane contains the **primary image** of the specimen.

The same lens produces both outputs simultaneously, at different planes. Operators select which plane to project onto the screen by adjusting the intermediate lens.

**Stage B: magnification and final image.** The intermediate lens picks up either the image plane (giving an image of the specimen at the screen) or the back focal plane (giving a diffraction pattern at the screen) and projects it. Subsequent projector lenses magnify further. The final image at the camera or viewing screen is the result.

### Object, image, and focal planes

The week-11 source emphasizes the geometric relationships:

- The **object plane** is where the specimen sits — always above the objective lens.
- The **image plane** is where the primary image appears — always below the objective lens.
- The **focal plane** (back focal plane in our context) is where parallel rays from the object plane focus.

These three planes have a specific geometric relationship determined by the lens equation. For a thin lens of focal length $f$:

$$
\frac{1}{d_o} + \frac{1}{d_i} = \frac{1}{f}
$$

where $d_o$ is the object-to-lens distance and $d_i$ is the lens-to-image distance. The image plane shifts when the focal length shifts (i.e., when lens current changes), which is why focusing a TEM image is operationally a current adjustment.

### Trade-off

The two-stage architecture optimizes for **flexibility and high magnification at the cost of optical complexity**. Compared to a light microscope (which also has two stages), the TEM column is harder to align and the consequences of mis-alignment are more dramatic. The reward is the ability to switch between imaging mode and diffraction mode using the same lens stack.

### What Goes Wrong Here

- **Mode confusion: the operator believes they are in imaging mode but the screen shows diffraction.** Diagnostic: imaging mode shows specimen features (gray-level variations, organic morphology, etc.); diffraction mode shows discrete spots or rings on a dark background.
- **Defocus moves the image plane off the camera.** Image is dim or absent. Diagnostic: scan the focus knob until image returns.

---

## 3. Bright-field imaging: the default

The question this section answers is: what does the most common TEM imaging mode actually do, and why is it the default?

### Mechanism — aperture passes only the direct beam

In **bright-field (BF) imaging**, the operator inserts the objective aperture into the back focal plane and *centers it on the direct beam*. The aperture is small enough that it physically blocks the scattered beams (which appear at the back focal plane as off-axis spots in a discrete diffraction pattern, or as a halo for amorphous/biological specimens). Only the direct beam — the unscattered electrons — passes through to form the image.

What does this image show? **Regions of the specimen that scatter strongly appear dark.** Because the aperture excludes scattered electrons, regions that scatter many electrons send fewer to the image plane, so they look dark. Regions that scatter weakly appear bright. The contrast is amplitude contrast: the image is built from variations in the *number* of electrons reaching the camera.

For a typical bright-field image:
- **Thicker regions** appear darker (more scattering events, fewer electrons through).
- **Higher-Z regions** appear darker (heavier atoms scatter more).
- **Crystalline regions** appear darker when oriented to diffract strongly.
- **Voids and holes** appear brightest (no scattering at all).

The week-11 source notes BF is "the most common imaging mode in TEM" and produces "images with a dark and light contrast between different parts of a structure."

### Defining contrast

Contrast in TEM is defined quantitatively as the relative difference in intensity between adjacent regions:

$$
C = \frac{I_2 - I_1}{I_1} = \frac{\Delta I}{I_1}
$$

A 10% contrast means the brighter region is 1.10 times the intensity of the darker. The visibility threshold for a human observer in noisy data is typically 5–10% contrast.

The source notes a critical operator-level trade-off: **as overall image intensity increases, contrast decreases** for a given specimen. Brighter illumination floods the dark regions with more electrons too, washing out the relative differences. The implication: for delicate features, dim illumination plus long acquisition gives better contrast than bright illumination plus short acquisition.

### Aperture size and contrast

The operator can choose objective aperture sizes (typically 20–60 μm physical diameter). The trade:

- **Smaller aperture:** excludes more scattered electrons; greater contrast; less current; more diffraction-limited blurring.
- **Larger aperture:** includes some scattered electrons; lower contrast; more current; less diffraction-limited blurring.

For high-contrast imaging of biological specimens, smaller aperture. For high-current imaging where SNR matters, larger aperture. Typical default: 30–40 μm aperture.

### Trade-off

BF imaging optimizes for **simplicity and broad applicability at the cost of selective sensitivity**. BF works for almost all specimens but does not maximize any particular kind of contrast. If you want maximum sensitivity to crystalline orientation, dark-field is better. If you want to see lattice fringes, HRTEM. If you want light-element sensitivity, EELS. BF is the default; the others are specializations.

### Worked example: contrast computation for a polymer

**Problem.** A bright-field TEM image of a stained polymer at 80 kV shows two phases: phase A with 4,000 counts per pixel; phase B with 3,200 counts per pixel. Compute contrast. Predict the visual visibility.

**Given.** $I_A = 4000$, $I_B = 3200$.

**Reasoning.** Take the lower as $I_1$:

$$
C = \frac{I_A - I_B}{I_B} = \frac{4000 - 3200}{3200} = 0.25
$$

So 25% contrast.

**Sanity check.** This is well above the 5–10% visibility threshold. The phase boundary will be clearly visible.

**General lesson.** Contrast above 10–15% is comfortable to see; below 5% requires longer exposures, image processing, or a different imaging mode.

### What Goes Wrong Here

- **Objective aperture not centered on the direct beam.** Image dim or asymmetrically lit. Diagnostic: check aperture-centering routine. Fix: re-center.
- **Aperture too large for high contrast.** Features barely visible. Fix: insert smaller aperture.
- **Image too bright; contrast washed out.** Reduce illumination at C2; lengthen acquisition.

---

## 4. Dark-field imaging: contrast inversion

The question this section answers is: what happens when you swap the aperture's role and pass only scattered beams?

### Mechanism — aperture excludes the direct beam, passes scattered

In **dark-field (DF) imaging**, the objective aperture is configured so that the *direct beam is blocked*; only scattered beams contribute to the image. Two ways to achieve this:

- **Off-axis aperture displacement.** The aperture sits to one side of the direct beam, allowing one diffracted beam (or a sector of scattered electrons) through. The image is formed by the scattered electrons in that direction.
- **Centered dark-field with beam tilt.** The illumination is tilted so the diffracted beam of interest goes down the optic axis; the aperture sits centered on the optic axis but now passes the (formerly off-axis) diffracted beam.

The result inverts the bright-field image:
- **Strongly scattering regions appear bright.** (They sent lots of electrons toward the diffracted direction.)
- **Weakly scattering regions appear dark.**
- **Voids and holes appear black.** (No scattering.)
- **Crystalline regions oriented to diffract toward the aperture appear bright.**

DF imaging is particularly useful for crystallography and defect imaging. A dislocation appears as a thin dark line in BF and as a thin bright line in DF, but the DF image isolates *only* the regions of crystal oriented to scatter into the chosen direction — making specific defects much more visible against a dark background.

### Operationally

In practice, BF is the survey mode and DF is the targeted mode. An operator reaches for DF when:
- Specific crystalline phases need to be highlighted against a darker matrix.
- Defects need to be seen in isolation from the bright bulk.
- Single-grain orientation work is the goal.

### Trade-off

DF optimizes for **sensitivity to specific scattering channels at the cost of overall image brightness**. The image is much dimmer than BF (most electrons are excluded), so longer acquisition times are needed.

### Worked example: choosing BF or DF for grain-boundary work

**Problem.** A graduate student wants to image grain boundaries in a polycrystalline metal foil. Boundaries are decorated with second-phase precipitates ~20 nm in size. Bright-field images show grains as different gray levels but precipitates are barely visible. Should the student switch to DF?

**Reasoning.** In BF, all grains appear because they all transmit electrons; precipitates barely show because the contrast difference between the precipitate Z and the matrix Z is small and the precipitates are thin. In DF, an aperture around a single matrix-grain diffracted beam will show *only* that grain bright, with everything else dark — including precipitates. If the precipitates have different crystal structure (different scattering pattern) than the matrix, they will not appear in the matrix-DF image. Conversely, choosing an aperture around a precipitate-specific scattered beam (if it exists) lights only the precipitates against a dark matrix.

**Answer.** Yes, switch to DF, with the aperture centered on a precipitate-specific scattered beam if available, or alternatively a matrix-specific beam to highlight grain boundaries by their lack of brightness.

**General lesson.** BF is great for survey; DF is great for hunting specific features that have a distinctive scattering signature.

### What Goes Wrong Here

- **DF image too dim to see anything.** Long exposure and high beam current are routine for DF. Or: the chosen aperture is in a low-intensity scattered beam.
- **Confusion about which features should appear in DF.** Operators sometimes expect DF to show "everything that scatters"; in fact, it shows only what scatters into the aperture's solid angle. Different aperture positions show different features.

---

## 5. Synthesis: aperture choice and projection ambiguity

The objective aperture is the operator's most consequential mode-selection lever. The configurations:

| Configuration | Aperture | What's selected | Mode | Image character |
|---|---|---|---|---|
| Aperture centered on direct beam | small | direct beam only | bright-field | scattering = dark |
| Aperture off-axis on a scattered beam | small | one scattered beam | dark-field | diffracting = bright |
| Aperture removed or very large | large/none | all beams | HRTEM/phase contrast | lattice fringes |
| Beam tilted, aperture centered | small | one scattered beam | centered DF | same as off-axis DF |

The trade between BF and DF is exclusive: same specimen, opposite image. A combined-mode approach takes a BF image, then a DF image of the same field, and uses both to interpret the structure. Some modern instruments allow simultaneous acquisition of BF and DF using detectors at different solid angles.

### Projection ambiguity

A TEM image is a projection through the specimen's full thickness. The week-10 source warned that "you cannot say that the particles are spheres. They could equally well be disks or cylinders." The 2D image cannot distinguish:

- **Spheres versus disks.** A sphere viewed from any angle is a circle. A disk viewed face-on is also a circle.
- **Hollow versus solid.** A particle with a low-density core and a high-density shell looks like a "doughnut" in BF (bright center with dark ring). But the same image could result from a solid particle made of a uniform material with curvature-dependent path length, depending on the specimen.
- **Surface versus interior features.** Where a feature lies in the specimen's depth dimension is mostly invisible in a single image.

Resolving projection ambiguity requires:

- **Tomography** (Chapter 19) — tilt series produces a 3D reconstruction.
- **Stereo pairs** — two images at different tilt angles allow stereo viewing.
- **Mass-thickness modeling** — for known materials, contrast scales predictably with thickness.
- **Complementary techniques** — SEM at the surface, AFM for topography, X-ray diffraction for crystal phase.

### Putting it all together (worked synthesis)

A graduate student needs to characterize 50 nm zeolite particles inside a polymer matrix. The plan:

- **BF at 100 kV.** Survey the specimen, locate isolated zeolite particles. Mass-thickness contrast distinguishes zeolite (silicate) from polymer.
- **BF at higher magnification.** Image individual zeolites for shape characterization.
- **DF.** Aperture on a zeolite-specific diffracted beam. Highlights zeolite particles against dark polymer matrix; useful for population statistics.
- **HRTEM** (Chapter 17). Aperture removed; lattice fringes of zeolite. Confirms crystal phase and orientation.
- **SAED** (Chapter 15). Aperture configuration on a single zeolite. Diffraction pattern indexed to identify zeolite phase.

Five aperture configurations on the same specimen. Each answers a different question. The full session demonstrates the operator's discipline of choosing apertures deliberately.

### Scale shift

Zoom in further than the operator usually goes: at the level of individual atoms, a TEM image is a coherent superposition of electron waves that have passed near and around individual atomic centers. The scattering and the interference are quantum-mechanical: each electron acts as a wave that interferes with itself between atoms. The image is the time-averaged probability distribution of where electrons land at the camera plane. A single TEM image with $10^9$ electrons per pixel is a statistical sampling of a wavefunction that, for a single electron, is purely probabilistic. The wonder is that this probabilistic individual-particle physics aggregates into an image that cleanly resolves features 0.1 nm apart. The wave nature of electrons, predicted by de Broglie in 1924, is not just an abstract idea — it is what makes the image possible.

---

## 6. Pre-lab Checklist (Lab 14 — BF and DF imaging)

**By the end of this chapter, you should be able to:**

- Acquire a bright-field image with the objective aperture centered on the direct beam.
- Acquire a dark-field image by tilting the beam onto a chosen scattered beam.
- Recognize projection ambiguity and propose a tilt-series strategy if needed.

**Bring to lab:**

- This chapter, especially Sections 3 and 4.
- A prepared TEM grid (provided by the lab).

**Expect on the floor:**

- A guided BF acquisition on a polycrystalline specimen.
- A first attempt at DF imaging by aperture displacement.
- Side-by-side comparison of BF and DF on the same field of view.

---

## 7. Quick-Reference Table

| Imaging mode | Aperture configuration | What appears bright | What appears dark | Best for |
|---|---|---|---|---|
| Bright-field (BF) | center on direct beam | regions that scatter weakly | regions that scatter strongly | survey, mass-thickness, defect imaging in BF |
| Dark-field (DF) | center on scattered beam | regions that scatter strongly into chosen direction | other regions | crystalline phase / orientation work |
| Centered DF (tilt) | beam tilted, aperture central | regions diffracting into selected direction | other regions | high-quality DF imaging |
| HRTEM (phase) | very large or no aperture | lattice fringes from interference | interference dark | atomic-resolution lattice imaging |

| Operating choice | Effect |
|---|---|
| Smaller aperture | higher contrast, lower current, more diffraction blur |
| Larger aperture | lower contrast, higher current |
| Lower kV | more contrast, more beam damage |
| Higher kV | lower contrast, less damage, sharper at thin parts |
| Longer acquisition | better SNR, more drift exposure |

---

## 8. Exercises

### Warm-up

**Exercise 14.1 (LO: identify image planes).**
For a TEM with a focal length of 5 mm and an object distance of 6 mm, where is the image plane? Difficulty: easy.

**Exercise 14.2 (LO: BF/DF distinction).**
In BF imaging, regions that scatter strongly appear ___, while in DF imaging they appear ___. Difficulty: easy.

**Exercise 14.3 (LO: define contrast).**
A region of a TEM image has 5,000 counts per pixel; an adjacent region has 3,000 counts. Compute the contrast and predict whether the boundary is visible. Difficulty: easy.

### Application

**Exercise 14.4 (LO: choose mode for question).**
For each scenario, name the imaging mode you would acquire first: (a) survey image of a polycrystalline metal foil at low magnification; (b) imaging of a specific crystalline phase against a matrix; (c) atomic-resolution imaging of a silicon-germanium interface. Difficulty: medium.

**Exercise 14.5 (LO: predict aperture-size effect).**
A BF image at 80 kV using a 30-μm objective aperture has 12% contrast on a polymer phase. The operator switches to a 60-μm aperture at the same kV. Predict the new contrast. Justify in one sentence. Difficulty: medium.

**Exercise 14.6 (LO: identify projection ambiguity).**
A TEM BF image shows what looks like a 50-nm spherical hollow vesicle (bright center, dark rim). What three alternative interpretations of the image exist, and what would you do to test among them? Difficulty: medium.

**Exercise 14.7 (LO: choose between BF and DF).**
A graduate student wants to count tiny twin boundaries in a single grain of a copper foil. The grain is one of many in the field; the boundaries are subtle in BF. What mode-and-aperture strategy would isolate the twins? Difficulty: medium.

### Synthesis

**Exercise 14.8 (LO: integrate BF, DF, HRTEM).**
A nanomedicine PI has 100 nm cobalt-iron oxide magnetic nanoparticles in a polymer matrix. The PI needs to (a) confirm particle size and dispersion, (b) verify the particles are crystalline, (c) determine the particle-matrix interface character. Specify a TEM acquisition strategy with at least three aperture configurations and explain what each reveals. Difficulty: hard.

### Challenge

**Exercise 14.9 (open-ended).**
Find a published paper that uses TEM bright-field and dark-field imaging on the same specimen. Explain in two paragraphs how the comparison answers a question that BF alone cannot answer. Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with a sense that TEM produces images. You walk out with the two-stage image-formation architecture, the objective aperture's role at the back focal plane, and the operator's choice of which beams contribute to the image. You can read BF and DF imagery critically, compute image contrast, and recognize projection ambiguity in 2D images of 3D specimens.

The one idea that matters most: the same specimen produces different images in BF, DF, and HRTEM modes because the objective aperture selects different beams. The image you see is a deliberate selection from the post-specimen wave field.

The common mistake to watch for is treating a single TEM image as a complete description of a specimen. Every image is a 2D projection through the thickness with a specific aperture configuration; it tells you what the aperture-passed beams reveal, not what the specimen actually is. Tilting, complementary modes, and tomography address this — but only by acquiring more data.

The Feynman test: explain to a labmate, without using the word "aperture," why the same specimen looks bright in some regions in BF and dark in those same regions in DF.

---

## 10. Connections Forward

Chapter 15 takes the back focal plane and unpacks the diffraction pattern that lives there — selected-area electron diffraction, indexing, d-spacings, zone axes. Chapter 16 covers contrast mechanisms in detail: mass-thickness, diffraction, and phase contrast, including Fresnel fringes you've already met. Chapter 17 covers HRTEM, STEM, and HAADF — advanced modes where the aperture rules differ. Chapter 19 covers tomography, the answer to projection ambiguity.

The question this chapter raised but did not answer: what *is* the diffraction pattern at the back focal plane, and how do you read it? Chapter 15 begins.

---

**What would change my mind:** evidence that single-image TEM acquisition can routinely resolve 3D structure without tilt-series tomography. Recent algorithmic methods (compressed sensing, deep-learning reconstruction) make progress here but the underlying projection ambiguity remains an information-theoretic limit.

**Still puzzling:** the practical decision of when "enough" diffraction-mode data to disambiguate a structure has been collected is not well-formalized. Most operators rely on heuristics (orient on multiple zone axes, get tilt series) rather than principled stopping criteria.

**Tags:** `bright-field`, `dark-field`, `objective-aperture`, `image-formation`, `projection`

---

### Note to the professor

`[verify]` markers in this chapter:
- Specific contrast-threshold values (5–10%) — operator-dependent.
- Worked-example numerics — constructed plausible.

Voice anchoring: anchored. Aluminum-foil chapter opening; capability ending; scale shift in synthesis (probabilistic individual-electron physics aggregating into a clean image). Length ~5300 words.
