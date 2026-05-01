# Chapter 6 — Electron Beam–Specimen Interactions in SEM

## Title options

1. **What the Beam Actually Does to the Sample**
2. **Inside the Interaction Volume: Where the SEM Image Comes From**
3. **Elastic, Inelastic, and the Pear-Shaped Cloud**

## TL;DR

When the focused electron beam strikes the specimen, it does not stay where you aimed it; it spreads through a micrometer-scale volume, scattering elastically off nuclei and inelastically off bound electrons, and the signals you image — secondary electrons, backscattered electrons, characteristic X-rays — emerge from different depths within that volume. This chapter is the physics that decides how much of the specimen the SEM is actually sampling.

---

## 1. Chapter Opening

The block of polymethyl methacrylate sits in the chamber of a 20 keV scanning electron microscope. PMMA — the same plastic in safety goggles and contact lenses, soft enough to take a fingernail mark. The beam parks for a few seconds on a single point. Nothing visible happens. The block comes out, gets dropped in a beaker of methyl isobutyl ketone, etches for a minute, and back to the optical microscope.

A teardrop crater has appeared in the surface, open at the top, dropping nearly a micrometer below the entry point, swelling into a bulb wider than the beam ever was. The crater is hollow because the polymer chains were broken by the beam — broken not just where the beam went in but everywhere it deposited its energy. Etch longer and the crater grows; the beam left a soft halo of damage out at the edges, where energy deposition was lower but not zero. Etch longer still and the contour map of the beam's path through the solid emerges, layer by layer.

That teardrop is not the beam. The beam came in as a point. The teardrop is the **interaction volume** — the three-dimensional region of the specimen that the beam actually touches once it gets inside. A focused 1 nm probe at 20 keV produces an interaction volume several micrometers across in low-density plastic. A million times wider than the beam.

Every signal you collect with an SEM detector — every secondary electron, every backscattered electron, every characteristic X-ray, every photon of cathodoluminescence — comes from somewhere inside that volume. The signal you read on the screen for a single pixel is not the surface at the beam impact point. It is some depth-averaged, lateral-averaged sample from a teardrop you cannot see, whose size and shape depend on the kV you chose, the elements in your specimen, and the angle at which the beam meets the surface.

By the end of this chapter you can predict the size and shape of the interaction volume for any SEM operating point, identify which signals come from which depths, and stop being surprised when a 1 nm probe gives you a 100 nm-wide image.

### Learning objectives

By the end of this chapter you can:

- **Describe** elastic and inelastic scattering and identify which produces which SEM signal.
- **Predict** how interaction volume scales with beam energy and atomic number.
- **Distinguish** secondary electrons (SE), backscattered electrons (BSE), and characteristic X-rays by their kinetic energy, escape depth, and information content.
- **Calculate** approximate penetration depth using the Kanaya–Okayama range relation.
- **Choose** kV and tilt to bias the interaction volume toward the information you want.
- **Recognize** beam damage, mass loss, and contamination as artifacts of beam-specimen interaction.

### Prerequisites

Chapter 2 (electron wavelength, accelerating voltage), Chapter 3 (gun and lens basics), Chapter 5 (operating-condition trade-offs). Some classical mechanics: elastic and inelastic collisions, conservation of momentum and energy.

### Why this chapter matters

Every SEM image is a sample of the interaction volume. If you do not know how big that volume is, you cannot say what region of your specimen the image actually represents. Chapter 7 will build the detectors that read the signals; this chapter is the physics that produces them.

---

## 2. Elastic vs. inelastic scattering, and the cloud they make

The question this section answers is: when an electron enters a solid, what happens — and why does the trajectory bend, slow down, and finally stop?

### Mechanism — two interactions, two consequences

An electron at 1–30 keV is fast. Not relativistic, but fast — at 20 keV, the electron moves at about 27% the speed of light. When it encounters an atom, two things can happen.

**Elastic scattering.** The electron interacts with the electrostatic field of the atom — primarily the positively charged nucleus, with the electron cloud screening at large distances. The collision conserves kinetic energy. The electron's direction changes; its speed does not. *Elastic*, from the Greek *elastikos*, "able to spring back" — same energy, new direction.

The cross-section for elastic scattering scales roughly as $Z^2 / E^2$, where $Z$ is the atomic number of the target and $E$ is the electron energy. Heavier elements scatter more strongly. Faster electrons scatter less. Both relations matter for the interaction volume, in opposite directions.

**Inelastic scattering.** The electron interacts with bound electrons in the atom, transferring energy to ionize, excite, or eject them. The collision does *not* conserve kinetic energy of the incident particle — some of the energy goes into changing the internal state of the target. *Inelastic*, "not able to spring back" — energy lost.

Inelastic scattering is what produces secondary electrons (Chapter 6, Section 4), characteristic X-rays (Chapter 9), and bremsstrahlung continuum (Chapter 9). It is also what slows the beam electron down: each inelastic event takes a small bite, on the order of 30–100 eV per event, until after many such events the electron has lost all its kinetic energy and stopped somewhere in the solid.

For an electron entering an SEM specimen, inelastic events are typically more frequent than elastic events, but elastic events deflect more strongly. The combined effect is a random walk: the electron diffuses through the solid, occasionally redirected by big elastic kicks, continuously bled of energy by small inelastic ones, until it stops.

### Visualizing the cloud

The week-3 source presents the PMMA experiment that opened this chapter as a real measurement: contour maps of energy deposition revealed by chemical etching. The experiment is not a hypothesis. The cloud is observed.

Modern microscopists do this calculation rather than the experiment. **Monte Carlo simulation** — from the casino, named for the way the algorithm uses random numbers to approximate physical processes that are deterministic in principle but intractable in practice — tracks tens of thousands of simulated electron trajectories one at a time, sampling random scattering events from physically motivated cross-sections. Each trajectory is one electron's random walk; the ensemble of trajectories produces a density map. The CASINO software (cited in the week-3 source) is one widely used implementation [verify: spelling and authorship of CASINO Monte Carlo, available since the 1990s].

The simulated cloud reproduces the etched cloud. We have two independent measurements of the same physics, and they agree.

### Trade-off

The physics of elastic and inelastic scattering hands the operator a real choice. Higher kV gives the beam more energy to spend before stopping, so it goes deeper — but every elastic event deflects it less, so the trajectories stay closer to the optic axis at first, and the interaction volume is *deeper but not proportionally wider*. The net cloud shape changes from teardrop at low Z to hemispherical at high Z, and from compact at low kV to elongated at high kV.

The trade-off, named: **higher kV optimizes for penetration depth at the expense of surface specificity**. Lower kV optimizes for surface signal at the expense of depth and resolution-limiting chromatic aberration (Chapter 2).

### Worked example: range and the $V^{1.7}$ scaling

**Problem.** Estimate the maximum penetration depth of a 20 keV electron beam in copper ($Z = 29$, density $\rho = 8.96$ g/cm³).

**Given.** $E_0 = 20$ keV, $\rho = 8.96$ g/cm³, $A = 63.55$ g/mol, $Z = 29$.

**Reasoning.** Use the **Kanaya–Okayama range** approximation, a widely-used empirical relation:

$$
R_{\text{KO}} \text{ [μm]} = \frac{0.0276 \, A \, E_0^{1.67}}{\rho \, Z^{0.889}}
$$

with $E_0$ in keV, $A$ in g/mol, $\rho$ in g/cm³ [verify: this is the standard form; prefactor and exponents are conventional, attributed to Kanaya and Okayama 1972].

Plug in:

$$
R_{\text{KO}} = \frac{0.0276 \times 63.55 \times 20^{1.67}}{8.96 \times 29^{0.889}}
= \frac{0.0276 \times 63.55 \times 142.0}{8.96 \times 19.8}
= \frac{249.1}{177.4}
\approx 1.4 \text{ μm}.
$$

**Sanity check.** Cu at 20 keV: textbooks quote interaction volume depth around 1–2 μm. Match.

**General lesson.** The depth scales as $E_0^{1.67}$ and inversely as a Z-dependent factor. Halve the kV from 20 to 10, depth drops by $2^{1.67} \approx 3.2\times$. Move from copper to aluminum at the same kV, depth grows by roughly $(13/29)^{0.889} (27/63.55) (8.96/2.7) \approx 0.51 \times 0.42 \times 3.32 \approx 0.71$ — Al is lower-Z and lower-density; the lower density wins, so interaction depth in Al at 20 keV is actually *larger* than in Cu, around 2 μm [verify: numerical].

For a quick mental model: at 20 keV, interaction-volume depth is on the order of 1 μm in metals, several μm in plastics and biological materials. At 5 keV, scale by $4^{1.67} \approx 9.5$ smaller — so 100 nm in metals, 500 nm in plastics. At 1 keV, smaller still — tens of nanometers in metals.

### What Goes Wrong Here

The most consequential failure mode in this section's physics is **interpreting an SEM image as if the beam saw only what was at the surface**. A 20 kV image of a 50 nm gold nanoparticle on a silicon substrate is not a picture of the nanoparticle — it is a picture of an interaction volume that extends a micrometer into the silicon below the particle, and the BSE signal is dominated by the silicon, not the gold. The fix is operating-point: drop kV until the interaction depth is comparable to or smaller than the feature you want to see.

**Beam damage** is the other direct consequence. Inelastic events deposit energy; deposited energy breaks bonds in soft materials (polymers, biological tissue) and can drive vacancies and radiolytic decomposition in some inorganic materials. The PMMA etch experiment is *intentional* damage; in normal SEM work, the same process degrades the specimen during imaging. Mitigations: lower kV, lower current, shorter dwell, lower temperature (Chapter 5).

**Mass loss** is a special case of damage: energy deposited fast enough volatilizes specimen material, which then disappears. Common in resins, polymers, and some biological prep. Recognition: features shrink during a long imaging session, sample mass on the stub decreases.

**Contamination** is the inverse: hydrocarbons in the chamber crack on the specimen surface under the beam, depositing carbon. Recognition: bright square outline of where you imaged at high kV after the session moves elsewhere. Mitigations: cleaner vacuum, plasma-clean the specimen before imaging, lower current.

---

## 3. Backscattered electrons: a Z-contrast signal from the depth of the cloud

The question this section answers is: where do backscattered electrons come from, what do they tell you, and why does composition show up in BSE images as gray-level differences?

### Mechanism — multiple elastic events, escape from the entrance face

A backscattered electron is a beam electron that has undergone enough elastic scattering events — usually many — to reverse its direction and exit the specimen back through the entrance surface. *Backscattered* because it scatters back; the path inside is a tortuous accumulation of small kicks, rarely a single bounce.

Two numbers bound the BSE population:

- **Energy.** Because elastic scattering conserves kinetic energy and inelastic events deposit energy slowly, BSEs typically retain a large fraction of the beam energy. The energy distribution peaks in the range $0.7\,E_0$ to $0.9\,E_0$ for medium- and high-Z targets. Low-Z targets give a broader, flatter distribution because BSEs from low-Z material undergo proportionally more inelastic events relative to the elastic deflections needed to come back out.
- **Yield.** The **backscatter coefficient** $\eta$ is defined as

$$
\eta = \frac{n_{\text{BSE}}}{n_B} = \frac{i_{\text{BSE}}}{i_B}
$$

— the number of BSEs leaving the specimen per beam electron entering. $\eta$ ranges from about 0.05 for carbon to about 0.5 for gold.

The week-3 source presents the central result of BSE physics as a plot: $\eta$ rises monotonically with $Z$. Steeply at first — the slope from carbon ($Z=6$) to silicon ($Z=14$) is large. Then the slope flattens; above $Z = 50$ or so the curve goes nearly horizontal, so distinguishing tantalum ($Z=73$) from tungsten ($Z=74$) by $\eta$ alone is hard.

That monotonic relation is the basis of **atomic-number contrast**, also called **compositional contrast** or **Z-contrast**. Imagine a polished alloy with two phases: an aluminum-rich phase ($Z_{\text{av}} = 13.2$) and a nickel-rich phase ($Z_{\text{av}} = 21.7$). The week-4 source provides exactly this measurement on a Raney-nickel alloy: Phase 1 (mostly Al) gives $\eta = 0.155$; Phase 4 (mostly Ni) gives $\eta = 0.243$. The contrast — defined as the relative gray-level difference — between phase 1 and phase 2 is 0.24, which is huge in SEM terms; you can see it across a busy room.

BSE imaging reveals composition. SE imaging reveals topography. Same specimen, two detectors, two pictures.

### Three other dependencies (briefly)

**Beam energy.** Within the SEM kV range (5–50 keV), $\eta$ depends only weakly on $E_0$ — typically less than 10% variation across this range. So you can change kV to change interaction volume and resolution without disturbing the gray-level scale. This is helpful: the BSE Z-contrast you see at 25 kV is roughly the same as at 15 kV.

**Tilt.** As the specimen tilts away from normal incidence, $\eta$ rises monotonically. This is the basis of **topographic contrast in BSE** — slopes facing the detector look bright, slopes facing away look dark. Tilt also drives an angular asymmetry in the BSE distribution: at normal incidence, BSEs leave in a cosine pattern around the surface normal; at tilt, the distribution develops a forward lobe in the down-slope direction. Detector position then matters even more.

**Depth.** BSEs sample a substantial fraction of the interaction volume's depth. For low-Z materials, BSEs come from up to half the Kanaya–Okayama range; for high-Z materials, from a smaller fraction (the heavy atoms scatter electrons back faster, so they don't have to penetrate as deep before reversing). Either way, BSE depth sampling is much greater than SE depth sampling. A subsurface inclusion at 200 nm depth shows up in BSE long before SE.

### Trade-off

BSE imaging optimizes for **composition information at the expense of surface specificity**. The 200 nm sampling depth that lets BSE detect a buried inclusion also blurs out fine surface features that an SE image would resolve. For a surface-morphological question, SE wins. For a composition question, BSE wins. Many modern SEMs let you collect both signals simultaneously and switch or combine in post.

### Worked example: BSE contrast between two phases

**Problem.** Two adjacent phases in an alloy have $\eta_1 = 0.155$ and $\eta_2 = 0.204$. Compute the contrast and predict whether the boundary will be visible at standard imaging conditions.

**Given.** $\eta_1 = 0.155$, $\eta_2 = 0.204$.

**Reasoning.** Define **contrast** as the relative difference:

$$
C = \frac{\eta_2 - \eta_1}{\eta_2} = \frac{0.204 - 0.155}{0.204} = \frac{0.049}{0.204} \approx 0.24.
$$

**Sanity check.** A contrast of 0.24 is well above the visibility threshold (typically 0.05 or 5%) for routine SEM imaging. The phase boundary will be visible without long dwell-time accumulation.

**General lesson.** SEM contrast visibility scales roughly as $\sqrt{N}$ where $N$ is electrons collected per pixel, so low-contrast features need more counts. BSE contrast between adjacent elements falls as $Z$ rises (slope of $\eta$ vs $Z$ flattens), so distinguishing Pt from Au is much harder than distinguishing Al from Si.

### What Goes Wrong Here

- **Mistaking BSE compositional contrast for SE topographic contrast.** A bright spot in a BSE image looks like a hill (because the eye reads bright = high) but might be a heavy-element inclusion. Diagnostic: check the detector. Always.
- **Hidden subsurface inclusions misread as surface features.** A BSE image at 25 kV samples 1+ μm into a metal; a bright dot may be an inclusion 800 nm below the surface, not an inclusion *at* the surface. Diagnostic: drop kV, see if the bright spot fades. If it does, the feature was subsurface.
- **Tilt-induced asymmetry mistaken for composition.** A specimen tilted toward the BSE detector shows a downhill brightening that has nothing to do with composition. Diagnostic: rotate the stage; the brightening should rotate with it if it is geometric, not stay fixed if it is compositional.

---

## 4. Secondary electrons: a surface signal at low energy

The question this section answers is: where do secondary electrons come from, why are they so surface-sensitive, and how does that surface specificity show up in the image?

### Mechanism — loosely bound, low energy, short escape

A **secondary electron** is, by source definition, a specimen electron with kinetic energy below 50 eV. Most are below 10 eV. The peak of the SE energy distribution sits at 2–5 eV. The cutoff is conservative: more than 90% of SEs are emitted with less than 10 eV.

How do they appear? An incident beam electron, in an inelastic collision, transfers a small amount of kinetic energy — a few eV to a few tens of eV — to a loosely bound outer-shell electron in a specimen atom. If the energy received exceeds the work function of the material (a few eV) and the electron's trajectory takes it toward a surface, it can escape into the vacuum. If not, it loses its energy to further inelastic events and stays put.

The SE coefficient is

$$
\delta = \frac{n_{\text{SE}}}{n_B}
$$

— number of SEs leaving per incident beam electron. $\delta$ is order 0.1 at 20 keV and rises *as kV decreases*, reaching values above 1 at 1–2 keV for some materials. That last fact is consequential: when $\delta > 1$, the specimen emits more electrons than it receives, so a non-conducting specimen actually charges *positively*, not negatively. This is why the **crossover energy** (the kV at which $\delta = 1$) sits at 1–3 keV for typical insulators — and why imaging insulating polymers at 1.5 kV often eliminates charging without any conductive coating.

### Why so surface-sensitive

SEs come out at low energy. A 5 eV electron in a solid loses energy to further inelastic events at a fearsome rate; after traveling a few nanometers, it has typically lost enough energy to fall below the work function and be trapped. The **escape depth** of an SE — the depth from which it can still exit the specimen — is therefore on the order of a few nanometers.

Compare to BSEs at $0.7\,E_0$ — kilo-electron-volts of energy — escaping from depths up to a micrometer. The two signals come from completely different parts of the interaction volume. SE is a thin surface skin; BSE is the depth.

### SE1, SE2, SE3 — three populations, one image

The week-3 and week-4 sources are explicit about a subtlety: not all SEs are created equal. Three populations, distinguished by where they originated:

- **SE1.** Generated at the beam impact point, in the very small footprint of the focused probe. SE1 carries the lateral spatial resolution of the beam. This is the high-resolution surface signal.
- **SE2.** Generated where BSEs exit the specimen surface — a region that can be hundreds of nanometers across. SE2 is *modulated* by the BSE distribution, so SE2 carries Z-information and depth-information from the BSE that produced it. SE2 broadens the apparent SE image relative to the focused-beam footprint.
- **SE3.** Generated where BSEs strike the chamber walls or the objective polepiece, far from the specimen. SE3 has no spatial information about the specimen; it just adds a roughly uniform pedestal to the signal — except where chamber geometry creates direction-dependent SE3 collection.

In a conventional Everhart-Thornley detector at 20 kV on a polished metal, SE2 and SE3 can together account for more than half the SE signal collected. The high-resolution SE1 is buried in a sea of BSE-derived noise. **Through-the-lens** detectors (Chapter 7) work because the strong objective field captures SE1 and SE2 selectively while excluding SE3, dramatically improving image quality.

### Other dependencies

- **Tilt.** $\delta$ rises with tilt as $\sec\theta$ approximately, where $\theta$ is the angle from normal. This is the basis of **topographic contrast** in SE images: faces tilted toward the detector emit more SEs and look bright; faces tilted away look dark. The eye reads this as light-and-shadow, which is why SE images look like photographs.
- **Composition.** $\delta$ is mostly insensitive to atomic number for clean elemental surfaces — a happy circumstance. SE images are mostly geometry, BSE images are mostly composition.
- **Surface contamination.** The mostly-Z-insensitive δ becomes very sensitive to adsorbed water, hydrocarbons, oxide layers, and so on. A surface that looks contaminated *will* image inconsistently; SE yield jumps with adsorbed monolayers. This is one reason plasma cleaning is sometimes necessary before high-resolution work (Chapter 8).

### Trade-off

SE imaging optimizes for **surface morphology and topographic visualization at the expense of composition information**. The light-optical analogy works for SE images: the detector takes the role of a light source, the beam is the eye's line of sight. Top-mounted detectors give "top-lit" images that the brain reads correctly; side-mounted detectors give dramatic but potentially misleading "side-lit" images. Read the detector label every time.

### Worked example: SE escape depth and the carbon-coating choice

**Problem.** A polymer specimen has been sputter-coated with 5 nm of platinum. The SEM operator wants to know whether SE imaging at 5 keV reveals features in the underlying polymer or features in the Pt coating.

**Given.** Pt coating thickness 5 nm. SE escape depth ~2–3 nm in metals [verify: standard textbook value]. Beam at 5 keV, interaction depth ~100 nm in polymer ≈ 50 nm in Pt [verify].

**Reasoning.** Most of the beam penetrates through 5 nm of Pt easily (Pt is dense but very thin). The interaction volume extends far beyond the Pt into the polymer. But: SE escape depth is shorter than the Pt coating thickness. SEs generated in the polymer cannot escape back through the Pt; they get absorbed.

**Answer.** The SE image at 5 keV is *predominantly Pt*, not polymer. The image looks like the surface of the Pt film. Because the Pt coats the polymer surface conformally, the image still shows the polymer's topography — but only through the Pt's geometric replication, not through the Pt's transparency.

For real polymer-internal information, you would need TEM (Chapters 12+) or much thinner coating or no coating at lower kV.

**General lesson.** The SEM image for a coated specimen is the coating's image, geometrically imitating the substrate's surface. This is the right answer for surface morphology; it is the wrong answer for composition or near-surface chemistry of the substrate itself.

### What Goes Wrong Here

- **Reading SE topographic shading as if it were optical reflectance.** It is not. SE intensity comes from local tilt and edge effects, not from reflectivity. An overhang appears bright in SE because edge geometry boosts SE escape; the same overhang in a photograph would shadow itself.
- **Assuming SE is "the surface".** SE escape depth is a few nm; the *interaction volume that produces SE2* extends much deeper. SE2 contributions blur the apparent SE resolution. TTL detectors mitigate this; E-T detectors do not.
- **Beam-induced contamination dominating SE signal.** Hydrocarbons crack on the surface during prolonged scanning; the carbon layer alters $\delta$. Recognition: a square dark patch where you previously imaged at higher kV.

---

## 5. Synthesis: matching the signal to the question

A focused electron beam enters the specimen at a single point with a single energy. Within picoseconds it has spread into a teardrop or hemisphere micrometers across, exchanging energy with hundreds of atoms before stopping. The signals you collect are samples from different layers of that cloud:

- **Auger electrons** — surface layer, < 2 nm. Used in dedicated Auger spectrometers, rare on standard SEMs.
- **SE1** — top few nm, lateral resolution of the focused beam.
- **SE2** — surface few nm, but modulated by BSE arrival positions hundreds of nm away.
- **SE3** — chamber walls and polepiece; no specimen spatial information.
- **BSEs** — top hundreds of nm to ~half the Kanaya–Okayama range. Z-contrast.
- **Characteristic X-rays** — full interaction volume depth and width. Elemental composition (Chapter 9).
- **Bremsstrahlung continuum** — full interaction volume. Background under the X-ray spectrum.
- **Cathodoluminescence** — most of the interaction volume in luminescent materials. Specialty technique.

**The trade-off the operator faces every session.** You want surface morphology at the highest possible spatial resolution; that means SE1, which means low kV and an SE1-selective detector (TTL on FE-SEM). You want composition; that means BSE, which means moderate-to-high kV and a BSE detector. You want elemental composition with reasonable spatial resolution; that means EDS, which means kV at least twice the energy of the heaviest line of interest (Chapter 9). You want a hidden inclusion; BSE at high kV. You want surface contamination identification; EDS at low kV (small interaction volume, surface-sensitive).

**Putting it together (worked scenario).** An imaging session on a polished steel inclusion-bearing alloy:

- 25 kV, BSE, polished surface flat: gray-level mosaic shows phase distribution. Bright phases are heavy-element-rich; dark phases are light-element-rich.
- 5 kV, SE, same surface: shows polishing scratches and surface oxide texture. Phase boundaries are mostly invisible in SE because $\delta$ is composition-insensitive.
- 25 kV, EDS, point analysis on bright phase: spectrum identifies Mn, Si, S as heavy components.
- 25 kV, EDS map: spatial distribution of elements over the area.

Same specimen, same imaging session, four distinct pictures. The question dictates which is the right one to look at.

**Scale shift.** Out at the cosmic end of the beam-matter scale: a particle accelerator collides 10 TeV protons to peer inside the proton itself, ten thousand kilometers below the threshold of an electron microscope's resolution. In at the intimate end: a 1 keV electron in your SEM, with a few-nanometer escape depth, samples just the topmost atomic layers of your specimen — close enough to count atomic terraces on a clean crystal surface. The SEM is the middle of that range, and the interaction volume is the price you pay for being there. Imaging at every length scale comes with a fundamental mismatch between the probe and the thing it touches; in SEM, that mismatch is a teardrop the beam never sees from the outside.

---

## 6. Pre-lab Checklist (Lab 6 — interaction volume and signal selection)

**By the end of this chapter, you should be able to:**

- Estimate interaction-volume depth for a given kV and material.
- Choose the right signal (SE, BSE, EDS) for a given research question.
- Identify subsurface features in a BSE image and verify by varying kV.

**Bring to lab:**

- This chapter, especially Sections 2–5.
- A polished or naturally smooth specimen with at least two phases or a known buried feature.
- A scientific calculator for Kanaya–Okayama estimates.

**Expect on the floor:**

- A demonstration of the same specimen imaged in SE at 5 kV and BSE at 25 kV, showing how the two signals reveal different aspects.
- A through-kV series on a heavy-element inclusion just below a polished surface, watching the BSE signal change as the interaction volume shrinks.
- Beam damage and contamination demonstration on a polymer or biological sample at moderate kV.

### Hazards and Safe Practice

The hazards specific to this chapter's content:

- **X-ray emission near the specimen.** When the beam excites characteristic X-rays, those photons radiate. Modern SEMs are shielded for routine imaging, but extended high-current work on heavy-element specimens raises the dose. Chapter 9 (EDS) will treat this in detail.
- **Beam damage to specimens.** Prolonged exposure decomposes biological and polymer samples; mass loss can render expensive specimens useless. The mitigations — lower kV, lower current, shorter dwell, cold stage — are discussed in Chapter 5 and will reappear in Chapters 19–21.

Cross-reference: **Appendix A** for the comprehensive treatment of high voltage, X-ray emission, and chemical hazards from beam-driven decomposition products.

---

## 7. Quick-Reference Table

| Signal | Energy | Escape / sampling depth | Information |
|---|---|---|---|
| Auger e⁻ | element-specific, < ~3 keV | < 2 nm | surface chemistry |
| SE1 | < 50 eV (peak 2–5 eV) | 2–5 nm | high-res surface morphology |
| SE2 | < 50 eV | a few nm (but emerges over BSE footprint) | BSE-modulated surface signal |
| SE3 | < 50 eV | irrelevant; chamber walls | uniform pedestal |
| BSE | $0.5\,E_0$ to $E_0$ | tens to hundreds of nm | Z-contrast, deep features |
| Characteristic X-ray | element-specific | full interaction volume | elemental composition |
| Bremsstrahlung | continuous, $0$ to $E_0$ | full interaction volume | spectrum background |
| Cathodoluminescence | photon, eV–10 eV | most of interaction volume | luminescent materials |

| Quantity | Scaling | Notes |
|---|---|---|
| Kanaya–Okayama range $R$ | $R \propto E_0^{1.67} A / (\rho Z^{0.889})$ | depth into solid |
| BSE coefficient $\eta$ | rises with $Z$, weak $E_0$ dep. | basis of Z-contrast |
| SE coefficient $\delta$ | rises as $E_0$ decreases | crossover at 1–3 keV |
| Interaction volume shape | pear (low Z) → hemispherical (high Z) | fixed at given $E_0$ |

---

## 8. Exercises

### Warm-up

**Exercise 6.1 (LO: distinguish elastic from inelastic).**
Classify each of the following SEM signals as primarily a product of elastic or inelastic scattering: (a) backscattered electrons, (b) characteristic X-rays, (c) secondary electrons, (d) bremsstrahlung. Difficulty: easy.

**Exercise 6.2 (LO: predict scaling).**
Without computing a number, predict whether interaction volume in carbon ($Z=6$) or in iron ($Z=26$) is larger at the same beam energy. State the physical reason. Difficulty: easy.

**Exercise 6.3 (LO: identify signal by depth).**
Order the following sampling depths from shortest to longest: SE1, BSE, characteristic X-ray, Auger electron. Difficulty: easy.

### Application

**Exercise 6.4 (LO: compute range).**
A 15 keV beam strikes a specimen of pure aluminum ($A = 27$, $\rho = 2.70$ g/cm³, $Z = 13$). Compute the Kanaya–Okayama range. Compare to the same beam striking pure tungsten ($A = 184$, $\rho = 19.3$ g/cm³, $Z = 74$). Difficulty: medium.

**Exercise 6.5 (LO: bias the volume).**
You are imaging gold nanoparticles ~10 nm in diameter on a carbon support film. You want SE images dominated by signal from the gold. Choose kV and justify in one sentence. What is the dominant artifact you will need to recognize? Difficulty: medium.

**Exercise 6.6 (LO: interpret BSE contrast).**
A BSE image at 20 kV shows a bright spot embedded in a darker matrix. You drop the kV to 5 kV and the bright spot fades. What does that tell you about its location? What might it be? Difficulty: medium.

**Exercise 6.7 (LO: choose signal for question).**
For each scenario, name the signal you would choose: (a) imaging surface fungal spore ornamentation; (b) detecting buried tungsten interconnects through 200 nm of silicon dioxide; (c) measuring iron concentration in a cell nucleus; (d) detecting surface oxidation on a polished alloy. Difficulty: medium.

### Synthesis

**Exercise 6.8 (LO: integrate signals and operating conditions).**
A graduate student has a polished sample of a porous calcium phosphate scaffold (Ca, P, O — all low-Z, $Z_{\text{av}} \approx 14$) infiltrated with 50 nm gold nanoparticles. The student wants to (a) confirm gold particle locations, (b) measure approximate Au:Ca ratio in different regions, (c) image the scaffold's surface topography. Specify the kV and detector for each, and explain in one sentence each how interaction-volume physics drove the choice. Difficulty: hard.

### Challenge

**Exercise 6.9 (open-ended).**
Run a Monte Carlo simulation in CASINO or a similar tool. Pick a material (your specimen of choice) and three beam energies (1, 5, 25 keV). Plot the simulated interaction volume for each. Predict the dominant signal at each kV before running. Compare your prediction to the simulation. Where did you predict wrong, and why? Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with a 1 nm focused probe in your mind. You walk out knowing that the probe gets blurred by physics into a teardrop the beam never sees, that every signal you collect samples a different layer of that teardrop, and that the operator's job is to bias the layers — by kV, by tilt, by detector, by signal choice — toward the question you want answered.

The one idea that matters most: the SEM image is not the beam impact point; it is the interaction volume. A 50 nm beam at 25 kV sees a micrometer of specimen. The mismatch between probe and sampling region is the central fact of SEM physics.

The common mistake to watch for is assuming the surface visible in your image is *the* surface. It might be the surface, or it might be a few hundred nanometers below the surface. Detector choice, kV choice, and depth-of-signal awareness decide which.

The Feynman test: explain to a labmate, without using the word "scattering," why a 25 keV electron beam striking copper produces an interaction volume about a micrometer deep — and why dropping the kV to 5 keV shrinks it to about 100 nm.

---

## 10. Connections Forward

Chapter 7 takes the signals you now know exist and turns each into an image — the detectors, the geometries, the operating choices that decide how an SE image differs from a BSE image of the same specimen. Chapter 8 covers sample preparation, much of which is about controlling beam-specimen interaction. Chapter 9 unpacks characteristic X-rays into elemental analysis. Chapter 10 builds the dual-beam systems that combine an electron column with an ion column for site-specific milling.

The question this chapter raised but did not answer: how does the detector geometry interact with the angular distribution of BSEs and SEs? Chapter 7 names the detector solutions and their trade-offs.

---

**What would change my mind:** evidence that interaction-volume depth in standard materials is significantly different from the Kanaya–Okayama prediction across most of the SEM kV range. The empirical scaling has been validated for decades; alternative parameterizations (Bethe range, modified KO) differ by tens of percent in specific cases but agree on the central scaling.

**Still puzzling:** the precise cutoff between "SE" and "BSE" at 50 eV is operationally useful but physically arbitrary. The energy distribution of inelastically scattered electrons is continuous; the 50 eV line is a convention for instrument calibration, not a physical break.

**Tags:** `interaction-volume`, `scattering`, `BSE`, `SE`, `Kanaya-Okayama`

---

### Note to the professor

`[verify]` markers in this chapter:
- Kanaya–Okayama range formula prefactor and exponents (1972 attribution; standard form).
- CASINO Monte Carlo authorship and dating.
- SE escape depth ~2–3 nm in metals.
- 5 keV interaction depth in Pt and polymer (worked example).
- Numerical comparison of Al vs. Cu range at 20 keV.

Voice anchoring: **anchored** to the workshop voice baseline established in Ch. 1 and now supported by `style/VOICE.md`. The chapter uses the chapter-opening hook (PMMA etch) only at the chapter level, with a scale shift in the synthesis section (cosmic-to-intimate beam-matter range). Capability-ending closer.
