# Chapter 7 — SEM Detectors and Image Formation

## Title options

1. **What the Detector Sees: How an SEM Image Gets Built**
2. **Reading Light from Electrons: The Detector Stack**
3. **Same Specimen, Different Detector, Different Image**

## TL;DR

The same specimen looks different through different SEM detectors because each detector samples a different combination of secondary electrons, backscattered electrons, and BSE-modulated populations from a different angular range. This chapter is the operator's guide to which detector tells you what — and to the artifacts each one introduces along the way.

---

## 1. Chapter Opening

A graduate student is at the SEM with a polished Ni–Al alloy specimen, the same one used in Goldstein's textbook. The slide on the screen says the alloy has four phases. Through the Everhart–Thornley detector at 20 kV, the student sees a uniform gray surface with faint hints of phase boundaries in the corner where polishing got rough. Switch to the semiconductor BSE detector mounted under the objective lens. The same field of view is now a four-tone mosaic: jet black where aluminum dominates, mid-gray where the Al–Ni–Fe phase sits, light gray for the Ni-rich phase, near-white for the highest-Ni region. Phase boundaries that were invisible thirty seconds ago are now the dominant feature in the image.

Nothing about the specimen changed. The beam is the same, the kV is the same, the working distance is the same. What changed is which population of electrons is being counted. The E-T detector counts mostly secondary electrons, which carry surface morphology and almost no atomic-number information. The BSE detector counts only backscattered electrons, which carry strong atomic-number contrast and very little surface topography. Two detectors, two pictures, one specimen.

This chapter teaches you to read which picture you are looking at. By the end, you can name every standard SEM detector, predict what kind of image each one produces, and identify the artifacts each one introduces. You will also be able to combine detectors — the simultaneous SE plus BSE pair, the sum-and-difference annular geometry — to extract more information than either alone provides.

### Learning objectives

By the end of this chapter you can:

- **Distinguish** Everhart–Thornley, in-lens / through-the-lens, scintillator BSE, and semiconductor BSE detectors by their physical principle and signal sensitivity.
- **Predict** what kind of image each detector produces for a given specimen.
- **Apply** the four detector questions — take-off angle, solid angle, energy response, bandwidth — to analyze a detector's behavior.
- **Recognize** detector-specific artifacts (E-T edge brightening, in-lens distortion, BSE topographic misreads, shadowing).
- **Choose** sum-mode versus difference-mode acquisition on a segmented BSE detector.

### Prerequisites

Chapter 6: which signals exist (SE1/SE2/SE3, BSE, characteristic X-rays), what they cost in energy, and where they sample from. Some elementary electronics: photomultiplier tubes, semiconductor diodes, gain.

### Why this chapter matters

An SEM image is uninterpretable without knowing which detector produced it. Every methods section in a published SEM paper names the detector for a reason. This chapter is the operator's foundation for both producing publishable images and reading them.

---

## 2. Four questions to ask of any detector

The question this section answers is: what makes one detector behave differently from another, and how do you reason about a detector you have never used before?

### Mechanism — geometry, sensitivity, response, speed

The week-4 source frames every detector with the same four questions. Every detector sits somewhere in the chamber; every detector has a face that catches electrons; every detector converts electrons into a signal at some efficiency that varies with electron energy; and every detector has electronics that pass through some range of frequencies. Together those four parameters tell you what the detector will do.

**Take-off angle ψ** is the angle from the specimen surface to the line connecting the beam impact point to the center of the detector face. A take-off angle near 90° (detector directly above the specimen) reads roughly the same signal regardless of specimen tilt. A take-off angle of 30° (typical Everhart–Thornley geometry) makes the detector much more sensitive to features facing toward it than to features facing away. Take-off angle is what the source identifies as the detector's *position*, and it sets the directional bias of the image.

**Solid angle Ω** is the size of the detector relative to its distance from the specimen:

$$
\Omega = \frac{A}{r^2}
$$

where $A$ is the detector face area and $r$ is the radial distance to the beam impact point. Solid angle is *what fraction of the emission cone the detector sees*. A small detector far away has a small solid angle and collects little. A large detector close to the specimen has a large solid angle and collects much. Higher solid angle gives better signal-to-noise, but at the cost of chamber clearance and other trade-offs (a big detector can block other detectors, occlude the eucentric tilt, and clutter the chamber geometry).

**Energy response** is the detector's efficiency for converting an incoming electron of a given energy into a useful signal. A scintillator-based BSE detector responds well to electrons above a few keV but gives nothing at all from a 5 eV SE — the SE just bounces off the scintillator. A solid-state silicon diode responds linearly to electron energy above its threshold (about 3.6 eV per electron-hole pair in Si, so a 15 keV BSE generates about 4000 free electrons before any amplification). The energy-response function is the key to *which signal* a detector measures, before anyone tells you what its name is.

**Bandwidth** is the range of signal frequencies the detector and its amplifier can pass. As the beam scans across fine-scale features, the signal changes rapidly — high spatial frequency translates to high temporal frequency. Coarse features change slowly, low temporal frequency. A detector with a bandwidth too narrow at the high end *blurs* fine features. A detector with a bandwidth too narrow at the low end *loses* the gradual shading of large features. Most modern systems span several decades of frequency, but specialty modes (very fast scanning, very slow integration) can hit bandwidth limits.

### Trade-off

The four questions hand you the joint constraint surface. A detector designer can optimize any one — bigger solid angle, wider energy range, faster bandwidth, more flexible take-off geometry — but rarely all four. Modern multi-detector chambers solve the problem by mounting half a dozen specialized detectors and letting the operator switch.

### Worked example: take-off angle and tilted-specimen geometry

**Problem.** An E-T detector is mounted at 30° take-off angle for a flat specimen at 0° tilt. The operator tilts the specimen 45° toward the detector. Estimate the new effective take-off angle.

**Given.** Initial $\psi_0 = 30°$ relative to specimen surface. Specimen tilt 45°.

**Reasoning.** Take-off angle is measured from the *specimen surface* to the line to the detector. When the specimen tilts toward the detector by 45°, the angle between the surface (now tilted up toward the detector) and the line to the detector decreases by 45°.

If the unrotated geometry placed the detector at 30° above the original surface, tilting the surface up toward the detector by 45° rotates the surface so that the line to the detector now sits at $30° - 45° = -15°$ relative to the new surface — meaning the detector is now *below* the new surface plane. Practically: the detector loses direct line of sight to the surface, the take-off angle has gone negative, and SE collection efficiency drops sharply. The image goes dark.

**Sanity check.** This matches operational experience: tilting too aggressively toward an asymmetric detector causes the image to dim. Operators learn to either tilt away from or rotate around the detector axis.

**General lesson.** Take-off angle changes with specimen tilt. The detector geometry that the manufacturer optimized for flat-specimen 0° tilt may not be the right geometry for 45°-tilted samples. For aggressively tilted work — fracture surfaces, cross-sections, geological thin sections — the operator picks detectors whose take-off angle survives the tilt.

### What Goes Wrong Here

Detector geometry confusion is common when readers try to interpret SEM images without knowing the detector position:

- **Side-lit images read as top-lit.** An E-T at 30° take-off lights the image from the side; the eye reads the shadow pattern as direction-of-light, sometimes mislocating which way is "up."
- **Mistaking a tilt-induced dimming for a charging artifact.** When the specimen tilt drops below the detector take-off angle, the image goes dark because of geometry, not because of beam-specimen problems. Diagnostic: rotate the stage; the dimming should follow.
- **Ignoring solid angle when comparing detectors.** A detector with large $\Omega$ at short working distance can't be matched by the same detector with the same kV at long working distance, because $\Omega$ shrinks as $r^2$.

---

## 3. Secondary-electron detectors: Everhart–Thornley and the through-the-lens family

The question this section answers is: how do we collect 5 eV electrons that cannot make it to a scintillator on their own?

### Mechanism — accelerate, scintillate, multiply

The defining problem of an SE detector is energy. Secondary electrons leave the specimen with at most 50 eV — typically less than 10. That is not enough to excite the phosphor on a scintillator. Not enough to drive a photodiode. Not enough, by itself, to be measured.

The **Everhart–Thornley detector**, developed by Everhart and Thornley in 1960, solves this with a two-stage acceleration. A **Faraday cage** sits in front of a scintillator; the cage is biased at +300 V relative to ground. The biased cage attracts SEs from a wide solid angle around the specimen — roughly hemispherical, even with the detector mounted asymmetrically off the optic axis. SEs that enter the cage are then accelerated by an additional +10 kV applied to the aluminum-coated front face of the **scintillator**, a phosphor (yttrium aluminum garnet doped with cerium, or similar) that emits light when struck by energetic electrons. The light passes through a **light guide** to a **photomultiplier tube (PMT)**, where it strikes a photocathode, releases photoelectrons, and triggers an avalanche amplification of $10^5$ or more. The output is a voltage proportional to the number of electrons that hit the cage.

That is the whole detector: collector, scintillator, light guide, PMT, amplifier. Five components, one job — turn a 5 eV SE into a measurable signal.

The +10 kV scintillator bias is high enough to disturb the primary beam if uncontrolled. The fix is the **Faraday cage**, which encloses the scintillator and shields the column from the high voltage; the much lower +300 V cage potential perturbs the beam negligibly. The architecture is a delicate compromise: enough field to attract and accelerate SEs, not enough to deflect the primary beam.

**Position.** The rigid light guide forces the E-T detector to a fixed position in the chamber, typically at 30° take-off angle relative to a 0°-tilt flat specimen. Take-off angle and collection efficiency depend on tilt, as Section 2's worked example showed.

**What it actually collects.** The week-4 source enumerates four populations the E-T detector picks up:

1. **SE1** — generated within the beam entrance footprint. The high-resolution surface signal.
2. **SE2** — generated where BSEs exit the specimen. BSE-modulated, lower lateral resolution.
3. **SE3** — generated where BSEs strike the chamber walls or polepiece. Spatially uninformative; uniform pedestal.
4. **Direct BSE** that happen to enter the scintillator solid angle. Carry Z-contrast.

The total E-T signal is roughly an SE-dominated mix with significant BSE-modulated contributions. SE1 alone might be a third or less of the total. This is why the E-T detector is described as "an SE detector" while honest treatments add "with BSE contamination."

### Through-the-lens (TTL) and in-lens detectors

Modern field-emission SEMs with strong objective fields — snorkel and immersion lenses (Chapter 3) — exploit the lens field itself. SE1 and SE2, generated near the specimen, are captured by the strong axial $B$ field and spiral up *through the lens* along magnetic field lines. The SE3 signal, generated far from the specimen, mostly cannot make it back into the lens. After emerging from the top of the objective, the SE1+SE2 stream is attracted to an E-T-style detector mounted above. The same scintillator-PMT physics, but a different collection geometry.

**The advantage.** Near-pure SE1+SE2, with most direct BSE and most SE3 excluded. Image quality, especially at low kV, is dramatically better than conventional E-T. This is why FE-SEMs with TTL/in-lens detectors are the high-resolution surface-imaging instruments of choice.

**The catch.** TTL works only when the lens is producing strong field at the specimen — that is, at short working distance. At long working distances the SE collection drops sharply. Also, the SE2 component is still BSE-modulated; the TTL is closer to a pure-SE detector than the E-T but is not perfectly pure.

### Trade-off

E-T detectors give you a detector that works at any working distance, on any column, with a robust signal. They mix populations.
TTL/in-lens detectors give you a near-pure SE1+SE2 image at the cost of working-distance constraint and instrument-specific availability.

For most labs: use the in-lens for low-kV high-resolution work, the E-T for everything else.

### Worked example: counting E-T signal contributions

**Problem.** A polished sample at 20 kV, with $\eta = 0.3$, $\delta = 0.15$ for SE1+SE2. The E-T detector geometry collects all BSEs entering its solid angle (estimate 5% of the half-sphere) plus essentially all SEs from any direction. A reasonable estimate of SE3 yield is $\delta_{\text{SE3}} \approx 0.1$ on an alloy specimen. What fraction of the E-T signal is from SE1+SE2 versus SE3 versus direct BSE?

**Given.** $\eta = 0.3$, $\delta_{\text{SE1+2}} = 0.15$, $\delta_{\text{SE3}} = 0.1$, BSE collection fraction = 0.05.

**Reasoning.** Per beam electron, the E-T collects approximately:

- SE1+SE2: 0.15 (assuming high collection efficiency)
- SE3: 0.10 (ditto)
- Direct BSE: 0.30 × 0.05 = 0.015

Total: 0.265. Of that, SE1+SE2 is about 57%, SE3 is about 38%, direct BSE is about 6%.

**Sanity check.** Standard textbook accounts attribute roughly half the E-T signal to true SE1+SE2 and the other half to BSE-modulated contributions (SE3 + direct BSE). Our estimate gives 57%/44% — close to that breakdown.

**General lesson.** Even on a "pure SE" detector, more than a third of the signal can come from BSE-driven processes. The high-resolution component (SE1) is a fraction of the SE1+SE2 number; on a well-collimated detector this might be 20% of the total signal. Hence the appeal of TTL.

### What Goes Wrong Here

- **Edge brightening on E-T images.** Thin edges, fibers, and small particles look brighter than they should because SE escape from edges is enhanced — escape paths are shorter for SEs generated near a steep surface gradient. This is a *real signal*, not a detector artifact, but it can mislead a quantitative size measurement. Recognition: thin features look "over-exposed" relative to the bulk material.
- **In-lens distortion at long WD.** TTL detectors lose efficiency rapidly when the working distance exceeds the design point. Image suddenly dims and grows noisy.
- **Charging amplified by E-T sensitivity.** The +300 V Faraday-cage bias attracts not just SEs but also any low-energy electrons emitted by a charging surface. A charged region can generate a parasitic signal completely decoupled from the primary beam impact point. Recognition: bright spots that move when the charge redistributes.

---

## 4. Backscatter detectors: scintillator and semiconductor

The question this section answers is: how do we measure the high-energy BSE signal that an E-T mostly throws away, and what does the resulting image actually show?

### Mechanism — scintillator and semiconductor, two physics, one signal

BSEs leave the specimen with most of the beam energy. They do not need acceleration. They can directly excite a scintillator or a semiconductor.

**YAG scintillator BSE detector.** A crystal of yttrium aluminum garnet, $\text{Y}_3\text{Al}_5\text{O}_{12}$ (etymology: garnet = the gem; "yttrium aluminum" tells you the structure type), doped with a small concentration of cerium that does the actual light emission. The crystal sits below the objective, often as an annulus around the optic axis. BSEs strike the crystal directly; the cerium ions emit visible photons; a light guide carries the photons to a PMT, which amplifies them into a signal. Because BSEs are energetic (5–25 keV typical), no post-specimen acceleration is needed — and that means no high voltage near the specimen, no Faraday cage, no beam disturbance. The detector can sit very close to the specimen.

**Semiconductor BSE detector (silicon diode).** A thin annular silicon diode, mounted under the objective. When a BSE strikes the silicon, it creates electron-hole pairs at a rate of one pair per 3.6 eV of deposited energy. A 15 keV BSE creates about 4000 free electrons in the silicon — a measurable signal even before amplification. Silicon diodes are thin, mechanically simple, easy to segment into multiple sectors (typically four quadrants A, B, C, D, or just A and B for sum-difference work), and can sit very close to the specimen for large solid angle.

Both detectors sense BSEs only. SEs lack the energy to excite the scintillator or generate enough e-h pairs to register above noise — the SEs effectively pass through invisible to the BSE detector. This automatic energy filtering is exactly what we want for clean Z-contrast imaging.

### Annular geometry, sum and difference modes

A segmented annular BSE detector mounts above the specimen, surrounding the beam axis, with the segments oriented so that each catches BSEs leaving in roughly opposite directions. With two segments (A and B), the operator can read out:

- **Sum mode (A + B).** Total BSE signal. Composition-dominated; topographic effects mostly cancel because A and B catch roughly symmetric tilt-driven asymmetries from opposite directions.
- **Difference mode (A − B).** The asymmetry between A and B. Topography-dominated; composition cancels because both segments see the same Z-driven yield. Tilted features show up brightly in difference; flat composition variations disappear.

The two modes from one detector give you, in one acquisition, both a Z-contrast image and a topographic image — without changing the column setup.

### Trade-off

**Scintillator vs. semiconductor.** Scintillators are robust, fast (high bandwidth), energy-linear, and can be made large. Semiconductors are thin, easily segmented, allow sum-difference work, and have higher energy resolution but slower bandwidth (the detector capacitance limits frequency response). Most modern SEMs offer both; the choice between them is mostly operator preference and historical instrument design.

**BSE vs. SE.** BSE optimizes for compositional sensitivity and depth penetration; SE optimizes for surface specificity and lateral resolution. The same specimen always looks different through the two. Smart imaging acquires both simultaneously.

### Worked example: BSE signal from a semiconductor diode

**Problem.** A 20 kV beam strikes a copper sample; the BSE coefficient is $\eta = 0.30$. The semiconductor BSE detector has a solid angle of 1.0 sr (a large, low-mounted annulus). The beam current is 1 nA. Estimate the average BSE signal current at the diode.

**Given.** $E_0 = 20$ keV, $\eta = 0.3$, $\Omega_{\text{det}} = 1.0$ sr, $i_b = 1$ nA. BSE angular distribution roughly cosine over 2π sr (hemispheric).

**Reasoning.** BSE current leaving the specimen: $i_{\text{BSE}} = \eta i_b = 0.30 \times 1 \text{ nA} = 0.30 \text{ nA}$. The fraction collected by the detector solid angle is $\Omega_{\text{det}} / (2\pi) \approx 0.16$, so collected BSE current ≈ 0.30 × 0.16 = 0.048 nA. Average BSE energy is roughly 0.7–0.9 of $E_0$; call it 14 keV. Each BSE produces 14,000 / 3.6 ≈ 3,900 e-h pairs in the diode. The diode current is then roughly $i_{\text{BSE}} \times (3900) = 0.048 \text{ nA} \times 3900 = 187 \text{ nA}$ — substantially amplified by the e-h pair gain in silicon, before any external amplification.

**Sanity check.** Real semiconductor BSE detector signals are tens to hundreds of nA at typical operating points, well above the noise floor of routine amplifiers. Match.

**General lesson.** The semiconductor diode has internal "gain" — about 4000× per BSE in silicon, given by the ratio of beam-electron energy to e-h pair creation energy. Even modest collection efficiency gives a robust signal because of this multiplication.

### What Goes Wrong Here

- **Topographic features misread as compositional in BSE.** A facet tilted toward the BSE detector is brighter in BSE *because of geometry*, not composition. Difference-mode imaging or stage rotation can disambiguate.
- **Annular detector blocking other detectors.** A large under-the-objective BSE detector occludes the EDS detector or limits short-working-distance SE work. Modern instruments mount BSE on a retractable mechanism for this reason.
- **BSE detector saturation at high beam current.** Scintillators can saturate and become non-linear; semiconductor diodes can hit thermal limits. Recognition: bright regions of the image cap at maximum gray rather than getting brighter.
- **The "buried bright spot" problem from Chapter 6.** A subsurface inclusion shows as a bright spot in BSE that is *not* on the surface. Diagnostic: drop kV; if the spot fades, it was buried. If it stays, it's at the surface.

---

## 5. Synthesis: detector choice as a deliberate operator move

Every SEM image you produce is a choice of which detector to read. The choice is consequential. Same specimen, four detectors, four different images.

**A polished alloy with phase variation and surface scratches**, imaged at 20 kV:
- E-T (SE-dominated): scratches and surface oxide visible; phases nearly invisible.
- TTL (pure SE1+SE2): scratches sharper; phases still mostly invisible.
- BSE scintillator (sum mode if segmented): phase mosaic dominant; scratches faint.
- BSE semiconductor (difference mode): scratches and steep slopes visible; phases largely cancelled.

**A 50 nm gold nanoparticle on carbon**, imaged at 5 kV on FE-SEM:
- E-T at 5 kV: charging artifacts on the carbon, particles visible but noisy.
- In-lens at 5 kV: high-resolution surface morphology of particle. Best image.
- BSE at 5 kV: low signal (small interaction volume, low BSE yield), particles barely above noise.

**A buried tungsten interconnect under 200 nm SiO₂** at 25 kV:
- E-T: no signal. SE escape depth is too short to reach back through the oxide.
- BSE semiconductor: clear bright tungsten lines visible through the oxide. The right tool.

**A thin biological section with metal-shadowed contrast**, prepared per Chapter 20, imaged at 8 kV:
- E-T: shadow-cast topography clear; the metal shadow does the contrast work.
- BSE: would resolve metal versus tissue but loses much of the shadow's directional information.

**Reading any SEM image** means asking: which detector? At what kV? Tilt? Working distance? The methods sentence "*all images acquired in SE mode at 5 kV with WD = 6 mm using the in-lens detector*" tells you, in advance, what to expect to see.

The wonder is that the detector, not the physics of the beam, is what lets you see one thing or another. A specimen that is "a flat metal" to one detector is "a four-phase mosaic" to another. An SEM is not just a microscope; it is a chamber full of specialized eyes, each tuned to a different part of the spectrum of beam-specimen interaction. The operator who chooses well is reading from many books at once.

---

## 6. Pre-lab Checklist (Lab 7 — detector comparison)

**By the end of this chapter, you should be able to:**

- Predict the qualitative difference between SE and BSE images of the same specimen.
- Recognize edge-brightening, side-lighting, and topographic-vs-compositional contrast from a given detector.
- Switch between sum-mode and difference-mode on a segmented BSE detector and predict what each will reveal.

**Bring to lab:**

- This chapter, especially Section 5.
- A specimen with at least one feature that should appear differently in SE vs BSE (a polished multi-phase alloy, a coated heterogeneous polymer, a heavy-metal-stained biological section).

**Expect on the floor:**

- A demonstration of the same specimen imaged in SE, BSE-sum, and BSE-difference modes.
- A working-distance scan on a TTL-equipped FE-SEM, watching image quality degrade as WD exceeds the design point.
- A first attempt at sum-difference acquisition on a real specimen, where you identify which features come from composition and which from topography.

### Hazards and Safe Practice

The hazards specific to detector hardware:

- **High voltage (+10 kV) at the E-T scintillator.** Inside the chamber, behind the Faraday cage. Modern instruments have interlocks; do not defeat them. Service work on the detector wiring is for trained personnel only.
- **Mechanical handling of detectors.** BSE detectors mount on retractable arms; insert and retract slowly. A poorly secured BSE detector can drop into the chamber and damage the polepiece. Two-handed handling, slow motion.
- **Liquid-nitrogen-cooled detectors** (some EDS detectors, certain CCD/CMOS direct-detection cameras in TEM). Cryogenic burn risk and asphyxiation risk in confined spaces. Cross-reference Chapter 9 for EDS detector cooling specifics.

Cross-reference: **Appendix A** for the comprehensive treatment.

---

## 7. Quick-Reference Table

| Detector | Signal | Energy range collected | Geometry | Information |
|---|---|---|---|---|
| Everhart–Thornley (E-T) | mostly SE; some BSE | wide (300 V to 10 kV acc.) | side-mounted, 30° take-off typical | surface morphology + side-lighting |
| Through-the-lens / in-lens | SE1+SE2 | low-energy SE | through objective | high-res surface; FE-SEM only; short WD |
| YAG scintillator BSE | BSE | > a few keV | under objective, often annular | Z-contrast, near-specimen mount |
| Semiconductor (Si) BSE | BSE | > a few keV | annular under objective | Z-contrast; segmented sum/diff |
| EDS (preview, full Ch. 9) | characteristic X-rays | 0.05–30 keV | side-mounted; 35° take-off typical | elemental composition |
| Other | cathodoluminescence, EBIC, EBSD | various | various | specialized — see Chapter 25 |

| Operating regime | Best detector |
|---|---|
| Low-kV high-resolution surface | TTL / in-lens |
| Conventional surface, any WD | E-T |
| Composition mapping | BSE annular |
| Topography of rough surface at low magnification | E-T or BSE difference mode |
| Buried subsurface feature | BSE at high kV |

---

## 8. Exercises

### Warm-up

**Exercise 7.1 (LO: distinguish detectors).**
For each of the following, name the detector you would choose: (a) surface morphology of a fungal spore, (b) buried tungsten lines under silicon dioxide, (c) phase distribution on a polished steel section, (d) high-resolution image of a 5 nm gold particle on carbon. Difficulty: easy.

**Exercise 7.2 (LO: ask the four questions).**
For an E-T detector mounted at 30° take-off angle with an aperture diameter of 5 mm at a working distance of 10 mm, estimate the solid angle. Difficulty: easy.

**Exercise 7.3 (LO: name the artifact).**
You see an annular BSE image where slopes facing the detector are bright and slopes facing away are dark, on a uniform-composition surface. What is happening? Which mode would suppress the effect? Difficulty: easy.

### Application

**Exercise 7.4 (LO: predict E-T signal mix).**
On a polished aluminum surface at 20 kV with $\eta = 0.16$, $\delta_{\text{SE1+2}} = 0.20$, $\delta_{\text{SE3}} = 0.07$, BSE collection 5%, estimate the fraction of the E-T signal from each population. Difficulty: medium.

**Exercise 7.5 (LO: choose detector under constraints).**
You need high-resolution surface imaging at 1.5 kV on an insulating polymer. The available detectors are E-T (working at all WDs) and TTL (working only at WD < 5 mm). The chamber requires WD = 8 mm to fit your sample stage. Which detector and why? What change to the experiment would let you use the other detector? Difficulty: medium.

**Exercise 7.6 (LO: interpret BSE topography).**
A BSE image at 25 kV shows a uniform alloy with bright "stripes" that change direction when the stage is rotated. Compositional variation, topographic effect, or both? Justify. Difficulty: medium.

**Exercise 7.7 (LO: choose mode on segmented detector).**
You have a segmented BSE detector with quadrants A, B, C, D, and you want to image a polished surface where you suspect both compositional phases and surface scratches. Describe an acquisition strategy that lets you produce both types of image from one scan. Difficulty: medium.

### Synthesis

**Exercise 7.8 (LO: integrate detector choice with operating physics).**
A graduate student is imaging cryo-fixed bacterial cells coated with 8 nm Pt. Goals: (a) high-resolution surface morphology of cell membrane; (b) confirm even Pt distribution across the surface; (c) detect any platinum-rich aggregates (>20 nm) that might be unevenly deposited Pt. For each, name the detector and the operating point (kV, WD, mode), and explain in one sentence each how the chapter's physics guided the choice. Difficulty: hard.

### Challenge

**Exercise 7.9 (open-ended).**
Find a published SEM micrograph in your field that shows surface morphology and where the detector is identified. Read what kind of detector was used. Predict what the image would look like through the *other* detector type (SE → BSE or BSE → SE) and write a paragraph about what new information the swap would reveal. Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with one detector in mind. You walk out with a chamber-full and the operator's discipline to pick from them. You can name the four questions for any detector — take-off angle, solid angle, energy response, bandwidth — and read what the detector will do before pressing acquire. You can recognize the artifacts each one introduces, and you can use sum-difference acquisition on segmented detectors to extract both Z-contrast and topographic information from one scan.

The one idea that matters most: the same specimen looks different through different detectors because each detector samples a different combination of populations from the interaction volume. Reading an SEM image without knowing the detector is reading an unsigned painting.

The common mistake to watch for: assuming "SEM image" means SE image. Many published images are BSE, in-lens, or detector-sum composites; the visual style of each is recognizable with practice. Always check the detector caption.

The Feynman test: explain to a labmate, without using the words "secondary" or "backscattered," why the same specimen at the same kV produces a different image through two different detectors.

---

## 10. Connections Forward

Chapter 8 covers the sample-preparation choices that decide which detector will produce a clean image; coating and mount choices interact with detector physics. Chapter 9 unpacks the EDS detector — a third major detector family, sensitive to characteristic X-rays for elemental analysis. Chapter 10 covers FIB-SEM dual-beam systems where the detector inventory expands further to include secondary-ion imaging detectors. The "What Goes Wrong" content of this chapter feeds directly into Chapter 23, where artifacts are synthesized comparatively across techniques.

The question this chapter raised but did not answer: how does an EDS detector, which is sensitive to X-rays rather than electrons, integrate into the same chamber? Chapter 9 explains.

---

**What would change my mind:** evidence that a single detector geometry could simultaneously deliver SE-quality surface resolution and BSE-quality Z-contrast on routine samples. Modern direct-detection cameras and energy-discriminating annular detectors are pushing in this direction; the trade-offs of Section 2 still hold for now.

**Still puzzling:** the specific contributions of SE3 to the E-T signal vary substantially across instruments and chamber geometries, yet are rarely characterized for a specific SEM. The instrument-by-instrument variation makes precise SE1 measurements harder than they should be.

**Tags:** `SEM-detectors`, `Everhart-Thornley`, `BSE`, `in-lens`, `image-formation`

---

### Note to the professor

`[verify]` markers in this chapter:
- E-T accelerating potentials (+300 V cage, +10 kV scintillator) — source-stated.
- 3.6 eV per e-h pair in Si — source-stated, standard.
- Take-off-angle 30° as E-T default — instrument-dependent.
- Solid-angle estimate of 1.0 sr in worked example.
- "About 50%" SE-vs-BSE-modulated split for E-T as standard textbook account.

Voice anchoring: anchored. Chapter-opening hook (the Ni-Al alloy mosaic appearing on the BSE switch). Capability-ending closer.
