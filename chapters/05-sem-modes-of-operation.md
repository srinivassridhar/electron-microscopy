> **Voice anchoring:** `voice-unanchored` — both `style/` folders are empty.

# Chapter 5 — SEM Modes of Operation

## Title options

1. **Driving the SEM: How Operating Conditions Shape the Image**
2. **The Operator's Trade-offs: kV, Working Distance, Spot Size, and Aperture**
3. **From Knobs to Image: Choosing SEM Conditions for Your Specimen**

## TL;DR

The SEM has perhaps a dozen settings the operator chooses for every image, and each setting interacts with the others through the physics of Chapters 2 and 3. This chapter turns the knobs into rules: when to push kV up, when to back working distance off, when to open the aperture, and how to recognize which setting is wrong when the image is wrong.

---

## 1. Chapter Opening

A second-year graduate student is at the SEM trying to image gold nanoparticles dispersed on a thin carbon film. The image is grainy. The student raises the accelerating voltage from 5 kV to 25 kV, hoping for better resolution. The graininess gets worse, and now there is a strange bright halo around each particle. The student lowers the magnification, raises the spot size for "more signal," and the image goes soft. Frustration sets in. The lab manager walks by, looks at the screen, and says: *the spot is too big, the kV is too high for these particles, and the dwell time is too long. Drop kV to 5 keV, drop spot size, increase scan rate, average frames. Try again.* The student does. The next image shows individual 5 nm particles cleanly.

What happened? The student treated the SEM as if every "more" knob would improve the image. The lab manager knew the physics: at 25 kV the beam penetrates well past 5 nm particles into the carbon below, the signal-to-noise from a too-big probe is dominated by noise, and a long dwell time on a thin carbon film just means more time for charging and contamination to grow. Lower kV, smaller probe, faster scan with averaging — that is the operating point for surface-sensitive nanoparticle imaging.

This chapter is the operator's discipline. By the end, you can pick reasonable starting values for kV, working distance, probe current, spot size, aperture, and scan rate for a given specimen, then iterate from there. You can also recognize five common image artifacts as functions of operating conditions and know which knob to turn.

### Learning objectives

By the end of this chapter you can:

- **Choose** accelerating voltage, working distance, and spot size for a specimen given its features and conductivity.
- **Recognize** charging, drift, astigmatism, and focus errors as artifacts of operating conditions.
- **Predict** how changes in kV, aperture, and probe current will shift the image's resolution, signal-to-noise, and depth of focus.
- **Apply** the standard charging mitigations: lower kV, faster scan with averaging, conductive coating, lower temperature.

### Prerequisites

Chapter 2 (aberrations and the optimum aperture), Chapter 3 (gun, lens, and aperture roles), Chapter 4 (the SEM as an integrated instrument). Some familiarity with the working-distance concept will help.

### Why this chapter matters

Almost every operator decision in real SEM work happens in this chapter's parameter space. Most "the image looks bad" sessions end with a parameter change, not a hardware change. Knowing which parameter to change is the difference between a 30-minute session and a 3-hour one.

---

## 2. The big three: accelerating voltage, working distance, spot size

The question this section answers is: how do the three most-used SEM controls interact, and how do you set them?

### Mechanism — what each parameter physically does

**Accelerating voltage (kV).** Sets the electron wavelength (Chapter 2) and the kinetic energy of the beam at the specimen. Three consequences cascade:

- **Wavelength → resolution floor.** Higher kV means shorter λ; in principle, finer resolution. From Chapter 2, $d_{\min} \propto (C_s \lambda^3)^{1/4}$, so doubling kV improves the floor by only $\sim 2^{3/8} \approx 1.3\times$. The wavelength advantage of high kV is real but modest.
- **Penetration depth → interaction volume.** Higher kV electrons go deeper into the specimen before stopping. The interaction volume — the pear- or teardrop-shaped region inside the specimen where the beam loses its energy — grows roughly as $V^{1.7}$ (the Kanaya-Okayama relation; Chapter 6 develops it). At 30 kV the interaction volume can be several micrometers deep; at 1 kV, a few tens of nanometers.
- **Surface sensitivity.** SE escape depth is roughly the same at all kV (a few nanometers), but at low kV the entire interaction volume sits within the SE-escape region, so SE yield per beam electron is highest at low kV. At high kV, most of the beam energy is deposited deeper than SEs can escape from. Low kV is where surface morphology lives.

**Working distance (WD).** Distance from the bottom of the objective lens to the specimen surface.

- **Short WD → smaller aperture angle and lower aberrations.** The objective focuses tightest just below the lens. Short WD gives the highest resolution.
- **Long WD → larger depth of focus.** Aperture angle decreases as the specimen moves away, increasing the axial range over which the image stays in focus. Useful for rough specimens.
- **WD constraints from detector geometry.** Some detectors (in-lens, BSE annulus) only work at specific WDs. Some specimens can only fit at long WD due to physical clearance.

Modern SEMs typically operate at WD = 4–10 mm for high-resolution work, 10–20 mm for detector flexibility, and 20–50 mm for large or rough specimens.

**Spot size (probe current via C1 condenser).** Strongest condenser lens excitation gives smallest probe and lowest current; weakest excitation gives biggest probe and highest current. Source physics: brightness is conserved through the column, so

$$
i_b \propto d^2 \alpha^2 \beta
$$

where $\beta$ is gun brightness and $d$ is probe diameter. At fixed aperture, current scales as $d^2$. Halve the probe size, quarter the current.

The trade-off is direct:

- **Small spot, low current:** high resolution, noisy image, long dwell to compensate, more drift and contamination.
- **Big spot, high current:** lower resolution, clean signal, short dwell, less drift sensitivity. Standard for EDS mapping.

### Trade-off (the joint surface)

The three parameters live on a coupled trade surface. Some illustrative pairings:

- **Surface morphology of a beam-sensitive specimen at high resolution:** low kV (1–5 kV), short WD (4–6 mm), small spot. Use FE-SEM if available — chromatic aberration at low kV is the killer, and Schottky/CFE energy spreads suppress it.
- **EDS mapping of a polished alloy:** moderate kV (15–20 kV, well above the heaviest characteristic line of interest), moderate WD (10–15 mm — the EDS detector likes a specific takeoff), larger spot for current.
- **Topographic imaging of a rough fracture surface:** moderate kV (10–15 kV), long WD (20–30 mm) for depth of focus, small aperture for the same.
- **Imaging a 50 nm particle on a heavy substrate:** low kV (1–3 kV) so the interaction volume does not overwhelm the particle, short WD, smallest spot.

This table is the operator's first-pass heuristic. The detailed adjustment comes from looking at the image and turning the right knob.

### Worked example: choosing kV for a biological cell on a glass coverslip

**Problem.** A graduate student wants to image fibroblasts that have been chemically fixed, dehydrated, critical-point-dried, and sputter-coated with 5 nm of platinum on a glass coverslip. The features of interest are the cell membrane projections (filopodia), ~100 nm diameter, on the 20 μm cell body. Choose kV.

**Reasoning.** The features of interest are surface-morphological. The substrate (glass) is insulating but covered by ~5 nm Pt. The Pt layer is conductive but thin: too high a kV and the beam will penetrate through it into the underlying glass and charge.

- 25 kV: penetrates ~3–5 μm in glass, well below Pt layer. Charging risk high.
- 15 kV: penetrates ~1–2 μm, still well below Pt. Charging risk moderate.
- 5 kV: penetrates ~50–100 nm in glass. The Pt absorbs much of the beam. Charging much reduced.
- 1 kV: penetrates ~10–20 nm. Almost entirely within the Pt. Surface sensitivity highest. Resolution lower because of chromatic aberration unless on FE-SEM.

**Answer.** Start at 5 kV. If charging is still visible, drop to 2–3 kV. If the FE-SEM is available, 1 kV may give the cleanest filopodia images. Increase Pt coating from 5 nm to 8 nm if charging persists.

**Sanity check.** Standard biological-SEM practice on coated specimens is 5–10 kV. We landed in that range.

**General lesson.** kV is chosen primarily by interaction depth relative to feature depth and substrate conductivity. Once you can answer "what depth of specimen does the beam see," you can answer "what kV."

### What Goes Wrong Here

- **kV too high for thin specimens or coatings:** beam penetrates through, samples substrate or interior, contrast falls and charging rises.
- **kV too low for FE-SEM-incapable instruments:** chromatic aberration dominates; image looks soft regardless of focus.
- **WD set short by habit, on a rough specimen:** image goes in and out of focus across the field of view because depth of focus is too small.
- **Spot size cranked up for "better signal" on a small feature:** probe diameter exceeds the feature, resolution lost.

---

## 3. Aperture, magnification, and depth of focus

The question this section answers is: what does the aperture knob actually buy you, and how do you choose magnification beyond just the visible feature size?

### Mechanism — three effects of one aperture

The week-2 source listed three effects of the final beam-limiting aperture:

1. **Aberration optimization** (Chapter 2): there is an optimum aperture angle for resolution.
2. **Depth of focus**: smaller aperture → larger axial range of focus.
3. **Beam current limiting**: smaller aperture → less current, because only a fraction of the cone passes.

The physical aperture is a fixed-diameter hole — typically 30, 60, or 100 μm — mounted in the objective. Smaller physical aperture means smaller half-angle $\alpha$ at the specimen for a given working distance. The half-angle is approximately $\alpha \approx (r_{\text{ap}}) / (\text{WD effective})$, where $r_{\text{ap}}$ is the aperture radius. (More precisely, the lens action modifies this, but the geometric estimate is in the right neighborhood.)

**Depth of focus** $D$ is the axial range over which the image stays acceptably sharp. For an aperture half-angle $\alpha$ and an acceptable disk diameter $d_0$ on the specimen,

$$
D \approx \frac{d_0}{\alpha}.
$$

A small aperture (say $\alpha = 5$ mrad) and a 100 nm acceptable circle gives $D = 20$ μm — enough to image a fracture surface with substantial topography. A large aperture (15 mrad) gives only 7 μm, which is fine for a polished flat surface but inadequate for a fracture.

**Magnification** is electronic, but bounded by physics. Chapter 2 named the empty-magnification cliff. The rule of thumb in many texts: maximum useful magnification = display dimension (in mm) × 1000 / resolution (in nm) [verify: standard convention but exact factor varies]. A 256 mm wide monitor with an instrument resolving 1 nm gives a maximum useful magnification around $10^6$.

### Trade-off

Aperture choice on every image:

- **Large aperture (60–100 μm):** more current, smaller depth of focus, more aberrations, dimmer corners on misaligned columns. For EDS mapping or low-magnification imaging of flat specimens.
- **Medium aperture (30–60 μm):** the everyday default. Balance of resolution and current.
- **Small aperture (10–30 μm):** maximum depth of focus, lowest aberration, least current. For high-resolution at low magnification of rough surfaces, and for the highest-resolution work where every aberration matters.

Magnification is what you set; *useful* magnification is what physics allows.

### Worked example: depth of focus for a fracture surface

**Problem.** You are imaging a rough fracture surface with peak-to-valley topography of 12 μm. You want the whole surface in focus. The aperture half-angle is 5 mrad, and the resolution criterion is 200 nm (50 μm beam width on a 25,000× displayed image).

**Given.** Topography $\Delta z = 12$ μm. Required $d_0 = 200$ nm. $\alpha = 5$ mrad.

**Reasoning.** Available depth of focus:
$$
D = d_0 / \alpha = 200 \text{ nm} / 5 \times 10^{-3} = 40 \text{ μm}.
$$
Required depth of focus: 12 μm.

**Answer.** $D > \Delta z$, so the chosen aperture works. To verify, what if the aperture were 15 mrad?
$$
D = 200 \text{ nm} / 15 \times 10^{-3} = 13 \text{ μm}.
$$
Borderline; the deepest valley would be marginally out of focus.

**General lesson.** Depth of focus is calculated, not eyeballed. For rough specimens, smaller aperture wins almost every time. The cost is current, but for topographic imaging that is rarely the binding constraint.

### What Goes Wrong Here

- **Aperture mounted but mis-positioned:** the beam is partially clipped, image is dim and asymmetric. Diagnostic: aperture-alignment check.
- **Aperture chosen by habit:** "I always use the medium one." Sometimes wrong. The aperture should match the imaging goal.
- **Magnification past the empty-magnification cliff:** monitor pixels get larger than instrument resolution times display size. Image just gets blurrier. Diagnostic: zoom out, see if features remain identifiable; if yes, the previous zoom was empty.

---

## 4. Charging, drift, astigmatism, and focus errors as functions of conditions

The question this section answers is: which image artifacts come from operating-condition choices, and how do you fix each one at the console?

### Charging

**Mechanism.** When the beam deposits more electrons into the specimen than the specimen can drain to ground, the surface accumulates negative charge. The resulting field deflects subsequent beam electrons, distorts SEs at emission, and produces image regions that go bright, dark, or both, with extreme distortions in non-conductors.

The week-4 source gives the operating-condition dependencies directly:

1. **Beam energy effect.** A specimen that is charge-free at 1 keV may charge at 2 keV and above. The mechanism: at low kV the SE yield often exceeds 1 (more electrons leave than arrive), so the specimen actually charges *positively* — and a small positive charge is harmless. At higher kV, SE yield drops below 1; the specimen charges negatively; bad things happen.
2. **Dwell-time effect.** An image at 1.6 μs pixel dwell appeared free of charging artifacts; longer dwells let bright regions grow as charge accumulates. Solution: faster scans and frame averaging instead of single slow scans.
3. **Detector sensitivity.** The E-T SE detector is especially sensitive to charging because its operation relies on attracting low-energy SEs whose trajectories are easy to deflect. The same specimen often shows much milder charging in a BSE image, because high-energy BSEs are not significantly perturbed by surface fields.

**Solutions.**
- **Conductive coating.** Sputter-coat the specimen with 2–10 nm of Au, Au-Pd, Pt, Cr, or carbon (Chapter 8). The coating drains charge to the stub and then to ground.
- **Lower kV.** Drop to or below the **crossover energy** (usually 1–3 kV) where SE yield ≈ 1 and net charge stays near zero.
- **Faster scanning with averaging.** Avoid slow scans; sum many fast frames.
- **Variable-pressure SEM (Chapter 10).** Introduce a small partial pressure of gas in the chamber; gas ions drift to the specimen and neutralize charge.

### Drift

**Mechanism.** The specimen, the stage, and the column move slowly relative to the imaging position over seconds-to-minutes timescales. Sources include thermal expansion (after kV change or specimen insertion), stage mechanical creep, and stage piezo creep. At 100,000× magnification, 1 nm/s drift moves features by a noticeable fraction of the display per second.

**Solutions.**
- **Thermal equilibration.** Wait 5–15 minutes after specimen insertion or major kV change before high-magnification work.
- **Drift compensation.** Some software auto-corrects between frames.
- **Faster acquisition.** A 1-second frame at 1 nm/s drift moves features 1 nm; at 100,000× this is invisible.

### Astigmatism

**Mechanism.** Lens not perfectly cylindrical (Chapter 2); a point on the specimen images to two perpendicular line foci at slightly different planes. Recognition cue: as you defocus through, a horizontal streak rotates to a vertical streak.

**Solution.** The stigmator alignment cycle: x-stigmator → focus → y-stigmator → focus, repeated until the image is sharp. Re-run after every kV, aperture, or working-distance change.

### Focus errors

**Mechanism.** Operator focused on a wrong feature (e.g., the carbon support film instead of the particle). Or the focus search exceeded the depth of focus and missed.

**Solutions.**
- **Focus on a high-contrast feature.** Edges, particles, sharp corners. Defocus shows up as edge softness; zoom in to see it clearly.
- **Use auto-focus carefully.** Auto-focus algorithms can be fooled by repetitive textures or charging artifacts.

### Trade-off

Most artifact-fix strategies cost something. Lower kV reduces charging but increases chromatic aberration and may lose deep-feature visibility. Conductive coating prevents charging but obscures fine surface features below the coating thickness. Faster scans reduce drift sensitivity but require more frames to reach the same SNR. Each fix is a trade.

### What Goes Wrong Here (recognition cues)

| Image symptom | Likely cause | First fix |
|---|---|---|
| Bright regions that grow during scan | Charging (build-up) | Drop kV; coat; or faster scan |
| Whole image scrolls slowly | Drift | Wait for equilibrium; or speed up scan |
| Streak rotates 90° through focus | Astigmatism | Stigmator cycle |
| Features blurred uniformly across field | Defocus | Refocus on high-contrast edge |
| Edges sharp but interior soft | Defocus across rough specimen | Smaller aperture for depth of focus |
| Image dim, no signal in some directions | Detector geometry / aperture mis-position | Check detector and aperture |
| Bright haloes around small features | Charging at edges | Coat; lower kV; switch to BSE |

---

## 5. Synthesis: a parameter-choice protocol

When you sit at a new specimen, run the protocol once before reaching for any clever maneuver:

1. **Specify the question.** What feature, what scale, what information depth? (Section 4 of Chapter 4.)
2. **Specify the specimen.** Conductive or insulating? Bulk or thin? Beam-sensitive or robust? What is the substrate?
3. **Pick kV.** Surface morphology of a beam-sensitive insulator: 1–5 kV. Bulk metallic surface: 10–20 kV. EDS work: ≥ 1.5–2× the highest characteristic-line energy of interest. Adjust upward if the specimen is robust and depth of penetration is acceptable.
4. **Pick spot size and aperture.** High-resolution surface morphology: small spot, medium-to-small aperture. EDS mapping: large spot, large aperture. Rough topography: medium spot, small aperture for depth of focus.
5. **Pick working distance.** Highest resolution: shortest practical (4–6 mm). Detector-flexible: 8–12 mm. Rough or large specimens: 15+ mm.
6. **Set magnification.** Pick to fit your feature, with at least 100 pixels across the smallest feature of interest.
7. **Acquire fast.** Get a quick image. Adjust focus and stigmator on a high-contrast region. Sanity-check the image for charging, drift, and detector mode.
8. **Acquire slow or averaged.** Higher SNR for the publication shot.
9. **Iterate.** If something's wrong, identify which parameter and turn that one knob. The diagnosis table in Section 4 above is the recipe.

This protocol is the SEM working hours of a working researcher distilled. Internalizing it cuts session time in half.

### Putting it all together (worked scenario)

A graduate student wants to image a section through a polymer scaffold (epoxy-embedded, microtome-sectioned, 1 μm thick, mounted on a silicon stub). The features of interest are surface texture from the original scaffold pores, ~50 nm scale. The polymer is insulating; the silicon stub is conductive.

- **kV.** 5 kV — penetration ~80 nm, well within the polymer surface region; charging manageable on most polymers at this kV with thin coating.
- **Coat.** 5 nm Au-Pd by sputter (Chapter 8).
- **WD.** 6 mm, short for resolution.
- **Spot size.** Small — the features are 50 nm and we want at least 5–10 pixel sampling, so we need probe ~10 nm.
- **Aperture.** 30 μm, medium.
- **Magnification.** Start at 5,000× for context; zoom to 50,000× for feature-level imaging.
- **Detector.** SE for surface morphology; consider BSE if the polymer has phase contrast.
- **Scan rate.** Fast for navigation; integrate 8 frames at slow scan for the publication.

Run the protocol and the image quality follows.

---

## 6. Pre-lab Checklist (Lab 5 — first hands-on session)

**By the end of this chapter, you should be able to:**

- Name an appropriate kV, WD, and spot size for a given specimen and question.
- Diagnose charging, drift, astigmatism, and focus errors from image symptoms.
- Apply at least two charging mitigations on a real specimen.

**Bring to lab:**

- This chapter, especially Sections 2 and 4.
- Your specimen, mounted and (if appropriate) coated.
- A research question stated as a sentence with a verb.

**Expect on the floor:**

- Setting up an image from scratch on a real specimen with the lab manager watching the parameter choices.
- A controlled charging demonstration: imaging the same uncoated insulator at 25 kV (charging visible) and 1.5 kV (charging suppressed).
- A focus-stigmator-aperture cycle on a feature you brought in.

### Hazards and Safe Practice

The hazards of running an SEM at the operator console are primarily:

- **High voltage** at the column and gun. Modern instruments are interlocked; do not defeat interlocks. Service work — including any opening of the gun chamber — is for trained personnel only.
- **Vacuum implosion** at viewports if compromised. Inspect seals; do not lean on the chamber.
- **X-ray emission** during routine imaging is shielded to negligible levels at the console on commercial instruments. Older or research instruments may not be; if your specimen contains heavy elements and the instrument is not certified for routine use, ask the lab manager.
- **Specimen handling.** Carbon tape leaves residues; wear gloves to avoid skin contact with sputter targets and stub adhesives.

Cross-reference: **Appendix A** for the comprehensive treatment.

---

## 7. Quick-Reference Table

| Goal | kV | WD (mm) | Spot | Aperture | Detector | Scan |
|---|---|---|---|---|---|---|
| Surface morphology, conductive | 5–15 | 4–8 | small | 30 μm | SE | fast + avg |
| Surface morphology, insulating | 1–5 | 4–8 | small | 30 μm | SE | fast + avg |
| Compositional contrast | 15–30 | 8–12 | medium | 60 μm | BSE | slow |
| EDS mapping | 15–25 | 10–15 | large | 60–100 μm | EDS | slow, long acquire |
| Rough topography, depth of focus | 10–15 | 20–30 | medium | 30 μm | SE | medium |
| High-resolution metal | 5–10 | 4–6 | smallest | 30 μm | in-lens SE | slow |
| Beam-sensitive (polymer/biology) | 1–3 | 4–8 | small | 30 μm | SE / TTL | fast + avg |
| Nanoparticle on substrate | 1–5 | 4–6 | smallest | 30 μm | SE / TTL | fast + avg |

[verify: starting points; tune to specimen.]

---

## 8. Exercises

### Warm-up

**Exercise 5.1 (LO: predict effect of kV).**
A specimen images cleanly at 5 kV. The operator changes to 25 kV and the image now shows a strong bright-dark structure that was not visible before. List two physical changes the kV jump caused. Difficulty: easy.

**Exercise 5.2 (LO: identify artifact).**
The image's left side is sharp; the right side is blurred. The specimen is rough, with topography across the field. Most likely cause? Difficulty: easy.

**Exercise 5.3 (LO: choose WD).**
For maximum resolution on a flat polished metal sample, do you choose short or long WD? Why? Difficulty: easy.

### Application

**Exercise 5.4 (LO: choose conditions for biology).**
Lung tissue, chemically fixed, dehydrated, critical-point-dried, sputter-coated with 5 nm of Pt. Features: alveolar surface texture at 200 nm. Choose kV, WD, spot size, aperture, detector. Justify each in one sentence. Difficulty: medium.

**Exercise 5.5 (LO: diagnose charging).**
You are imaging an uncoated polymer at 15 kV with the E-T detector. The image shows extreme bright/dark distortion at the polymer surface. Three solutions, in priority order, and one sentence each on the trade-off. Difficulty: medium.

**Exercise 5.6 (LO: depth-of-focus calculation).**
You are imaging a fractured ceramic with peak-to-valley topography of 8 μm. Required resolution at the displayed magnification is 100 nm. What is the maximum aperture half-angle you can use? Difficulty: medium.

**Exercise 5.7 (LO: scan-rate choice).**
A specimen is beam-sensitive — within 30 seconds of high-kV exposure, contamination grows visibly. You need a publication-quality image at 50,000×. Describe the acquisition strategy (kV, scan rate, frame averaging). Difficulty: medium.

### Synthesis

**Exercise 5.8 (LO: integrate parameter choices for a hard specimen).**
A research group has gold nanoparticles, average diameter 5 nm, dispersed on a 20 nm thick carbon support film over a copper TEM grid. They want to image the gold nanoparticles in SEM (not TEM) for a comparison experiment. The SEM is an FE-SEM with cold-FE source. Choose all parameters: kV, WD, spot size, aperture, detector, scan rate. Predict at least two artifacts the chosen parameters might still produce, and note how to recognize them. Difficulty: hard.

### Challenge

**Exercise 5.9 (open-ended).**
The crossover energy at which SE yield equals 1 varies by material — typically 1–3 kV for insulators, lower for some polymers. Look up the SE yield curve for a polymer you have used (PMMA, polystyrene, or epoxy). Identify the crossover energy. Predict the kV at which uncoated imaging would be charge-free. Compare to standard practice in published papers using that polymer. Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with a vague sense that "SEM has settings." You walk out knowing which settings to start with for which specimen, why the settings interact (kV controls penetration, which controls charging and contrast and depth of feature visibility; aperture controls aberration and depth of focus and current; spot size controls resolution and current), and how to recognize the four most common image artifacts and fix each at the console.

The one idea that matters most: kV is chosen by interaction depth relative to feature depth, not by "more is better." Higher kV is not always sharper; lower kV is not always cleaner. The right kV is the one whose interaction volume sits where your information lives.

The common mistake to watch for: turning multiple knobs simultaneously when something is wrong. The diagnostic discipline is one knob at a time. Identify the artifact, identify the most likely parameter, change only that, observe the result. This is the operator's discipline.

The Feynman test: explain to a labmate why dropping kV from 25 to 1 will eliminate charging on an insulating polymer, without using the word "yield."

---

## 10. Connections Forward

Chapter 6 develops the beam-specimen interactions that underlie the choices in this chapter — what actually happens inside the interaction volume, and why kV controls the depth and shape of it. Chapter 7 returns to detectors with the operating-condition context now in hand. Chapter 8 covers sample preparation, which is the other half of charging mitigation: the conductive coating and the conductive mount.

The question this chapter raised but did not answer: why does SE yield exceed 1 at low kV? That depends on how energetic an SE has to be to escape, and how many of them get generated per beam-energy unit. Chapter 6 names the physics.

---

**What would change my mind:** evidence that a single parameter (e.g., kV alone) determines image quality independent of all others on a real specimen. The trade-off structure described here is repeatedly demonstrated; counterexamples would require a different operating regime (perhaps very-low-voltage instruments below 1 kV) where the rules genuinely change.

**Still puzzling:** the operator-experience literature on SEM is largely tribal. Most working scientists know "what works" without a clean theoretical justification, and the gap between best practice and physics-based prescription is real. This chapter's protocol is one bridge across it.

**Tags:** `SEM-operation`, `accelerating-voltage`, `working-distance`, `charging`, `parameter-choice`

---

### Note to the professor

`[verify]` markers in this chapter:
- Empty-magnification factor (display × 1000 / resolution) — exact prefactor varies by source.
- Quick-Reference Table starting points — these are heuristics for first-pass setup; tune to your instruments.
- Penetration depths in the Section 2 worked example are order-of-magnitude estimates from Kanaya-Okayama scaling (Chapter 6 will derive properly).
- Crossover energy claim ("usually 1–3 kV"). Material-dependent; the range is conventional.
- The geometric aperture-angle relation $\alpha \approx r_{\text{ap}} / \text{WD}$ is approximate.

Voice anchoring is `voice-unanchored`.
