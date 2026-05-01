# Chapter 15 — Diffraction and Crystallographic Information in TEM

## Title options

1. **Reading the Lattice: Selected-Area Electron Diffraction**
2. **From Spots to Spacings: TEM Diffraction Patterns**
3. **The Diffraction Pattern at the Back Focal Plane**

## TL;DR

When the TEM beam passes through a crystalline specimen, the periodic atomic lattice scatters electrons coherently into discrete directions, producing a diffraction pattern at the back focal plane that the operator can image directly. Spot positions encode interplanar spacings; spot patterns identify crystal phase; spot brightness and shape carry information about defects and orientation.

---

## 1. Chapter Opening

A graduate student is at the TEM with a thin film of titanium dioxide. The bright-field image at 50,000× shows a uniform gray field — the film is thin and amorphous-looking. The student inserts the selected-area aperture, encircling about 200 nm of the film. Then switches the intermediate-lens excitation from imaging to diffraction mode. The screen transforms: the gray field disappears, replaced by a series of concentric bright rings on a dark background, sharp at the inner radii, broader and dimmer toward the outside. Each ring corresponds to a specific lattice plane in the TiO₂ — the (110), (220), (002), (212) planes of rutile. The d-spacings, measured from the ring radii, match published values for rutile within a few picometers. The film is rutile-phase TiO₂, polycrystalline, with no hint of amorphous component. The student's image and the diffraction pattern together identify the material with a precision no other technique on this specimen could achieve.

This is what selected-area electron diffraction (SAED) does, and it is one of the genuinely unique capabilities of TEM. Light microscopes do not have this. SEMs have it only in the form of EBSD on bulk surfaces. TEM lets you point at any 100-nm region of a thin specimen and read off its crystal phase from the diffraction pattern.

By the end of this chapter you can recognize SAED patterns, distinguish single-crystal from polycrystalline from amorphous, measure d-spacings from ring radii, and use the result to identify the crystal phase of an unknown specimen.

### Learning objectives

By the end of this chapter you can:

- **Explain** how electrons diffract from a crystal lattice via Bragg's law.
- **Distinguish** single-crystal, polycrystalline, and amorphous diffraction patterns.
- **Measure** d-spacings from the ring radii or spot positions of a SAED pattern.
- **Use** selected-area aperture and camera-length calibration to acquire SAED patterns.
- **Identify** zone axes and orient a single-crystal specimen.
- **Recognize** indexing errors and double-diffraction artifacts.

### Prerequisites

Chapter 14 (TEM image formation, back focal plane). Some crystallography: lattice planes, Miller indices, d-spacings, reciprocal lattice. A vector picture of how the lattice produces a Fourier-like diffraction signal.

### Why this chapter matters

Crystal-phase identification is one of the questions that TEM answers better than any other technique on small specimens. Reading SAED patterns is a foundational TEM skill — for materials science, for nanomedicine of crystalline drug particles, for biomineralization studies, for mineral identification.

---

## 2. Bragg's law and the geometry of electron diffraction

The question this section answers is: when do electrons scatter coherently from a crystal, and what determines the angles at which they emerge?

### Mechanism — coherent elastic scattering from periodic planes

A crystal is a periodic arrangement of atoms — rows and rows of identical scatterers separated by repeating distances. When a coherent wave (electron, X-ray, neutron) encounters such an array, the scattered waves from different scatterers can interfere. Constructive interference happens at specific angles; destructive interference everywhere else. The result is a diffraction pattern — discrete directions where scattered intensity concentrates.

The condition for constructive interference is **Bragg's law**:

$$
n \lambda = 2 d \sin\theta
$$

where $\lambda$ is the wavelength, $d$ is the spacing between adjacent lattice planes, $\theta$ is the angle between the incident wave and the lattice planes, and $n$ is an integer (the diffraction order). For first-order diffraction ($n=1$), the law simplifies to $\lambda = 2d\sin\theta$.

In TEM at 200 kV, $\lambda \approx 2.5$ pm. For typical lattice spacings of 0.1–1 nm:

$$
\sin\theta = \frac{\lambda}{2d} \approx \frac{0.0025 \text{ nm}}{2 \times 0.3 \text{ nm}} \approx 4 \times 10^{-3}
$$

So $\theta \approx 0.25°$. Diffraction angles in TEM are tiny — far smaller than the angles in optical or X-ray diffraction. The diffraction pattern in the back focal plane appears compact compared to the camera area.

The wavelength and lattice spacing are linked by the diffraction equation: small $\lambda$, small $\theta$. To resolve diffraction features at high angle (i.e., from small $d$-spacings), TEM needs to project the back focal plane onto the screen with significant magnification. The intermediate and projector lenses do this; the result is a pattern of spots or rings at the screen.

### What the lattice produces — three pattern types

The pattern depends on what kind of crystallinity the specimen has within the selected area:

**Single crystal.** A single crystallite within the selected area gives a pattern of discrete bright **spots** on a dark background. Each spot corresponds to a specific reciprocal-lattice vector — that is, to a specific set of lattice planes scattering coherently. The pattern is the projection of the reciprocal lattice onto the camera plane, oriented according to which crystal direction is parallel to the beam.

**Polycrystalline.** Many randomly-oriented crystallites within the selected area. Each crystallite produces its own spot pattern, oriented differently. When you superimpose all of them, the spots blur into **rings** at radii corresponding to the d-spacings. Rutile, in our chapter opener, gave a polycrystalline ring pattern.

**Amorphous.** No long-range periodic order. Atoms still have characteristic spacings (nearest-neighbor distance), but with random orientation in space. The diffraction signal is **diffuse halos** — broad concentric bands rather than sharp rings or spots. The center is dark (the direct beam goes through the unscattered direction); halos indicate the most-probable nearest-neighbor distance.

### Camera length and the d-spacing relation

The TEM operator measures spot positions or ring radii on the camera and converts them to d-spacings using the **camera length** $L$:

$$
R \cdot d = L \cdot \lambda
$$

where $R$ is the radius of a spot or ring on the camera, $d$ is the corresponding lattice spacing, and $\lambda$ is the wavelength. Camera length depends on lens settings — typically 50–500 mm for routine SAED — and is calibrated against a known specimen (commonly a polycrystalline gold or aluminum film whose d-spacings are tabulated).

For a 200 kV TEM with $L = 200$ mm and $\lambda = 2.5$ pm:

- A ring at $R = 1.7$ mm has $d = L\lambda/R = 200 \times 0.0025 / 1.7 = 0.29$ nm.
- A spot at $R = 5.5$ mm has $d = 200 \times 0.0025 / 5.5 = 0.091$ nm.

So small radii correspond to large d-spacings, and large radii correspond to small d-spacings. The pattern is a *reciprocal* representation of the lattice.

### Trade-off

SAED optimizes for **crystal-phase identification at the cost of imaging the same region**. While in diffraction mode, you do not see the bright-field or dark-field image of the specimen. Switching back and forth requires re-establishing focus, eucentric height, and aperture position. Modern instruments have streamlined this with software-driven mode switches.

### Worked example: identifying rutile from a ring pattern

**Problem.** A polycrystalline TiO₂ film gives a SAED pattern with rings at $R_1 = 1.55$ mm, $R_2 = 3.10$ mm, $R_3 = 3.33$ mm, $R_4 = 4.16$ mm. Camera length 200 mm, accelerating voltage 200 kV ($\lambda = 2.51$ pm). Identify the phase.

**Given.** $L = 200$ mm, $\lambda = 2.51$ pm.

**Reasoning.** Compute d-spacings from $d = L\lambda/R$:

- $d_1 = 200 \times 0.00251 / 1.55 = 0.324$ nm
- $d_2 = 200 \times 0.00251 / 3.10 = 0.162$ nm
- $d_3 = 200 \times 0.00251 / 3.33 = 0.151$ nm
- $d_4 = 200 \times 0.00251 / 4.16 = 0.121$ nm

Compare to published rutile d-spacings (per the source-given table): (110) at 0.325 nm, (220) at 0.162 nm, (002) at 0.148 nm, (212) at 0.120 nm. Matches within a few picometers.

**Answer.** Rutile-phase TiO₂.

**Sanity check.** The spacing values are all in the right ballpark for an oxide; the (110) at ~0.32 nm is the largest spacing, consistent with the diagonal of a tetragonal unit cell of rutile dimensions.

**General lesson.** SAED ring measurement plus published d-spacing tables identifies most common crystal phases. Modern software automates the identification; the operator's job is to acquire a clean pattern and trust (with cross-check) the database match.

### What Goes Wrong Here

- **Camera-length miscalibration.** Off by 10% gives d-spacings off by 10% — enough to confuse rutile with anatase or other related phases. Fix: routine calibration against a known standard.
- **Selected area too small for the camera-length convention.** SAED at 100-nm selected area can include single-crystal grains, partial grains, and grain boundaries. The pattern may show spots from a few orientations rather than full rings, and indexing becomes harder.
- **Indexing errors.** Picking the wrong combination of spots can lead to a phase identification that is internally consistent but wrong. Cross-check by computing predicted d-spacings for the proposed phase and comparing to all measured spots.

---

## 3. Single-crystal patterns and zone axes

The question this section answers is: what do you do when the SAED pattern is a sparse array of spots rather than rings?

### Mechanism — projection of the reciprocal lattice

A single crystallite, oriented at random with respect to the beam, gives a pattern of discrete spots. Each spot is a reciprocal-lattice vector $\mathbf{g}_{hkl}$ where $hkl$ are the Miller indices of the lattice plane that scattered into that spot.

When the beam is parallel to a low-index crystallographic direction (a **zone axis**), the resulting pattern is highly symmetric — for cubic crystals along [001], the pattern is a square array of spots; along [011], a rectangular pattern; along [111], a hexagonal pattern. These zone-axis patterns are recognizable at a glance and the most useful for orientation determination.

The **zone axis** is the crystal direction along which the beam travels. All lattice planes that contain the zone axis appear in the pattern.

To orient a single-crystal specimen for diffraction work:

```
PROCEDURE — Tilting to a low-index zone axis

1. Insert SAED aperture; switch to diffraction mode.
2. Find the direct beam in the center of the screen.
3. Look at the diffraction pattern. If asymmetric or broken, tilt
   the stage in small increments (1-2°) along one axis at a time.
4. Watch the spots: they move in symmetric trajectories as you tilt.
5. When spots form a recognizable symmetric pattern (square, hex, rect),
   you are on or near a zone axis.
6. Fine-tune by tilting both axes to maximize symmetry.
7. Record: the zone axis indices [uvw] (e.g., [001], [011], [111]).
```

Modern double-tilt holders (Chapter 13) give the operator the freedom to tilt in two perpendicular axes; finding a zone axis typically takes a few minutes once you know the crystal symmetry.

### Indexing a pattern

For a known crystal structure, indexing the pattern means assigning specific $hkl$ Miller indices to each spot. The standard approach:

1. Measure d-spacings for the closest spots (smallest $R$ on camera).
2. Compare to published d-spacings for candidate phases.
3. Identify the family of $hkl$ values consistent with each spot.
4. Verify internal consistency: the angles between spots should match the angles between lattice planes computed from the crystal structure.

Modern software automates this. The operator's contribution is judgment about which candidate phases are plausible (driven by the specimen chemistry).

### Trade-off

Single-crystal SAED optimizes for **structural information density at the cost of selected-area constraint**. A 100-nm aperture isolates a region small enough to typically see one or a few crystallites in metals, ceramics, and minerals. For nanocrystalline specimens (grain size ≪ 100 nm), the pattern blends many orientations into rings; for coarser specimens (grain size ≫ 100 nm), the pattern shows only one orientation. The aperture size and camera-length combination needs to match the specimen's grain size.

### Worked example: zone-axis orientation for a silicon film

**Problem.** A graduate student has a thin silicon film and wants to image lattice fringes (Chapter 17). What zone axis should they orient the silicon to, and why?

**Reasoning.** Silicon is cubic (diamond structure). The standard low-index zone axes are [001], [011], and [111]. For HRTEM lattice imaging:
- [001]: shows the (200) and (220) planes, fringe spacings 0.272 nm and 0.192 nm.
- [011]: shows (111), (200), (311) planes; fringe spacings 0.314 nm, 0.272 nm, 0.164 nm.
- [111]: shows (220) only easily resolvable; 0.192 nm.

For first attempts at lattice imaging, [011] is often a good choice because it gives multiple visible spots with comfortable spacings. [001] is also common.

**Answer.** [011] or [001] zone axis. Tilt to align one of these.

**General lesson.** Zone-axis choice is a strategic decision before imaging. The zone determines which lattice planes you can see; pick the zone whose planes match your imaging goal.

### What Goes Wrong Here

- **Drift away from the zone axis during imaging.** Stage drift slowly tilts the specimen out of alignment. Recognition: pattern asymmetry growing over time. Fix: re-tilt periodically; settle stage longer.
- **Tilt-induced double diffraction.** When the specimen is tilted such that the beam encounters two lattice families, double diffraction can produce extra spots not present in the simple single-orientation pattern. Recognition: spots that don't index to the candidate phase. Fix: re-tilt to a cleaner zone axis.

---

## 4. Synthesis: SAED in the imaging workflow

A typical TEM session that uses diffraction has both imaging and diffraction-mode acquisitions on the same field of view:

1. **Bright-field overview** (Chapter 14). Survey the specimen; locate features of interest.
2. **High-magnification BF detail.** Image a single feature at high resolution.
3. **Insert SAED aperture.** Encircle the feature.
4. **Switch to diffraction mode.** Read d-spacings or zone axis.
5. **Switch back to imaging mode.** Verify the same region.
6. **DF imaging.** If needed, use a specific scattered beam to highlight one phase or orientation.

The combination is more powerful than any single mode. A BF image plus an SAED pattern together identifies the phase, the orientation, the morphology, and (with DF) the spatial distribution of crystallites.

### Multi-phase identification

A specimen with two or more crystalline phases gives a SAED pattern with rings or spots from each phase. The operator's job is to identify which features belong to which phase. Strategies:

- **Acquire DF images** with the aperture on each set of rings/spots in turn. Each DF image shows the spatial distribution of one phase.
- **Tilt to separate phases.** Different phases tilt to different zone axes; tilting the stage may resolve overlapping patterns.
- **Combine with EDS or EELS.** Elemental composition (Chapters 9 and 18) confirms which phase contains which elements.

### Putting it all together (worked synthesis)

A graduate student characterizes a 50 nm zeolite catalyst particle in a polymer matrix. The full TEM session:

- **BF survey.** Locate isolated zeolites, image at 50,000×.
- **SAED on a single zeolite.** Spot pattern indexes to a specific zeolite framework type (e.g., MFI for ZSM-5).
- **Tilt to zone axis.** Find [001] or other low-index orientation.
- **HRTEM** (Chapter 17). Lattice fringes at 1 nm spacing visible, consistent with the indexed structure.
- **DF imaging on a zeolite-specific spot.** Confirms zeolite particles isolate from the polymer matrix.

The combination of techniques fully characterizes the catalyst — phase, orientation, morphology, distribution. SAED is the structural-analysis backbone of this workflow.

---

## 5. Pre-lab Checklist (Lab 15 — SAED on a thin film)

**By the end of this chapter, you should be able to:**

- Acquire a SAED pattern from a chosen region of a thin specimen.
- Measure d-spacings from ring or spot radii.
- Tilt to a low-index zone axis on a single-crystal specimen.
- Distinguish single-crystal from polycrystalline from amorphous patterns.

**Bring to lab:**

- This chapter, especially Sections 2 and 3.
- A polycrystalline gold or aluminum film for camera-length calibration.
- Your specimen of choice, ideally with known crystal phase for verification.

**Expect on the floor:**

- Camera-length calibration on a standard.
- A first SAED acquisition on a polycrystalline specimen.
- A first attempt at zone-axis tilting on a single-crystal grain.
- A first measurement of d-spacings and comparison to a published table.

---

## 6. Quick-Reference Table

| Pattern type | What it indicates | Identification |
|---|---|---|
| Discrete spots | single crystal | zone axis indexing |
| Concentric rings | polycrystalline | d-spacings from ring radii |
| Diffuse halos | amorphous | nearest-neighbor distance |
| Mixed | multiple phases or grain mixing | phase by phase indexing |

| Quantity | Symbol / formula | Notes |
|---|---|---|
| Bragg's law | $\lambda = 2d \sin\theta$ | first-order diffraction |
| Camera-length relation | $R \cdot d = L \cdot \lambda$ | $R$ on camera, $d$ in specimen |
| Wavelength at 200 kV | 2.51 pm | relativistic |
| Typical TEM diffraction angle | 0.1°–1° | small angle |
| Typical camera length | 50–500 mm | for SAED |
| SAED aperture diameter | 50–500 nm equivalent | physical size in selected-area plane |

| Worked-example zone-axis spacings (Si) | (hkl) | $d$ (nm) |
|---|---|---|
| [001] | (200) | 0.272 |
| [001] | (220) | 0.192 |
| [011] | (111) | 0.314 |
| [011] | (200) | 0.272 |
| [011] | (311) | 0.164 |

---

## 7. Exercises

### Warm-up

**Exercise 15.1 (LO: predict pattern type).**
For each specimen, predict whether the SAED pattern will be spots, rings, or halos: (a) single crystal of silicon, (b) thin film of nanocrystalline gold, (c) amorphous carbon support film. Difficulty: easy.

**Exercise 15.2 (LO: measure d-spacing).**
A SAED pattern at $L = 250$ mm, $\lambda = 2.5$ pm shows a ring at radius 4.0 mm. Compute the d-spacing. Difficulty: easy.

**Exercise 15.3 (LO: name pattern source).**
Why does a ring pattern correspond to a polycrystalline specimen rather than a single crystal? Difficulty: easy.

### Application

**Exercise 15.4 (LO: identify a phase from a pattern).**
A polycrystalline metal gives rings with d-spacings 0.236, 0.205, 0.144 nm at 200 kV. Compare to: copper (0.209, 0.181, 0.128 nm), aluminum (0.234, 0.203, 0.143 nm), nickel (0.203, 0.176, 0.124 nm). Which is the specimen? Difficulty: medium.

**Exercise 15.5 (LO: design a zone-axis tilt).**
You have a single-crystal silicon thin film and want to image (220) lattice fringes. Which zone axis would you tilt to, and how many spots will you expect to see in the diffraction pattern? Difficulty: medium.

**Exercise 15.6 (LO: choose camera length).**
You want to resolve d-spacings as small as 0.05 nm. At 200 kV, $\lambda = 2.5$ pm. The camera is 50 mm wide and pixel size 10 μm. What camera length do you need to spread the smallest spacing to a resolvable position on the camera? Difficulty: medium.

**Exercise 15.7 (LO: calibrate from a standard).**
A polycrystalline gold standard at 200 kV gives the (111) ring at radius 5.20 mm. The gold (111) d-spacing is 0.235 nm. Compute the camera length. Difficulty: medium.

### Synthesis

**Exercise 15.8 (LO: integrate BF, DF, SAED).**
A graduate student has 100 nm cobalt-iron oxide nanoparticles in a polymer matrix. The student wants to (a) confirm the particles are crystalline, (b) determine which iron oxide phase (Fe₃O₄, Fe₂O₃, etc.) the particles are, (c) measure orientation distribution among particles. Specify a TEM session including BF, DF, and SAED acquisitions, and explain what each contributes to answering the three questions. Difficulty: hard.

### Challenge

**Exercise 15.9 (open-ended).**
Find a published SAED pattern in a paper from your research field. Identify which kind of pattern it is (single crystal, polycrystalline, amorphous). Estimate d-spacings from any visible rings or spots. Compare to the indexed values the authors report. Comment on any discrepancies and possible reasons (camera-length miscalibration, indexing ambiguity, etc.). Difficulty: open-ended.

---

## 8. Summary

You walked into this chapter knowing the TEM has a diffraction mode. You walk out knowing how to use it: insert the SAED aperture, switch the intermediate lens, read d-spacings from ring radii or spot positions, identify crystal phases by comparison to published tables, and use zone-axis tilting to align a single crystal for imaging. SAED is one of TEM's distinctive capabilities — direct structural identification of the crystal phase in a 100-nm region.

The one idea that matters most: the diffraction pattern at the back focal plane is a *reciprocal* representation of the lattice. Spot or ring radii correspond to inverse d-spacings; small radii encode large spacings. Reading the pattern means inverting from the camera plane to the lattice.

The common mistake to watch for is treating a single ring or spot as a phase fingerprint. Multiple phases share specific d-spacings; you need several spots or rings, all consistent with one phase, before the identification is reliable.

The Feynman test: explain to a labmate, without using the word "Bragg," why a polycrystalline specimen gives rings while a single crystal gives spots.

---

## 9. Connections Forward

Chapter 16 covers contrast mechanisms in detail — mass-thickness, diffraction, and phase contrast — and how each manifests in different imaging modes. Diffraction contrast (Chapter 16) is the basis of how grain orientation appears in BF and DF. Chapter 17 covers HRTEM and STEM — modes that exploit the same diffraction physics to produce atomic-resolution images. Chapter 18 covers EELS, the chemical analog of SAED for elemental and bonding information.

The question this chapter raised but did not answer: how does diffraction contribute to the contrast in a real-space image (rather than just the diffraction pattern)? Chapter 16 unpacks diffraction contrast as a contrast mechanism in BF and DF imaging.

---

**What would change my mind:** evidence that selected-area diffraction can routinely identify trace phases (<5 vol%) in a thin specimen. Current practice with SAED needs ≥10 vol% of the secondary phase typically; below that, the secondary spots are too weak to distinguish from background.

**Still puzzling:** the practical interpretation of partial or noisy SAED patterns from thin or beam-damaged specimens often relies more on operator pattern-matching skill than on principled deconvolution. Software-based pattern matching helps but does not solve the operator's judgment problem.

**Tags:** `SAED`, `diffraction`, `Bragg`, `d-spacing`, `zone-axis`

---

### Note to the professor

`[verify]` markers in this chapter:
- Specific Si zone-axis fringe spacings (standard textbook values).
- Camera-length values (instrument-dependent; 50–500 mm range is conventional).
- Published d-spacings for rutile, copper, aluminum, nickel — standard tabulated values.

Voice anchoring: anchored. TiO₂-film chapter opening (one scene only). Capability ending. Wonder grounded in numbers (2.5 pm wavelength, 0.25° diffraction angles, picometers of d-spacing precision). Length ~5300 words.
