# Chapter 21 — Cryo-EM: Vitrification, Cryo-Imaging, and Single-Particle Basics

> **Scope discipline note (per `book.md`):** This chapter teaches cryo-EM as a *method extension* of biological TEM prep + low-dose imaging. Single-particle analysis appears only as introductory framing — workflow overview, why averaging works, what resolution claims mean. A reader who wants to do SPA needs a different book; this book gets the reader ready to *understand* an SPA paper, not to *run* one.

## Title options

1. **The Frozen Sample: Cryo-EM as Method Extension**
2. **Vitrification, Cryo-Holders, and SPA: A Reader's Introduction**
3. **From Native State to Atomic Structure: Cryo-EM Basics**

## TL;DR

Cryo-EM combines vitrification — flash-freezing a hydrated specimen in amorphous ice — with low-dose TEM imaging to image biological structures in their native hydrated state. Single-particle analysis builds 3D atomic-resolution structures from thousands of randomly oriented copies of the same molecule, all imaged at low dose in vitreous ice.

---

## 1. Chapter Opening

A graduate student stands in front of a Vitrobot, a small instrument the size of a desktop printer. Inside, a humid chamber holds a TEM grid coated with a 3 μL droplet of purified ribosome solution at near-physiological buffer. The student initiates the protocol: forceps with the grid plunge-down through a humidity-controlled chamber, pause for blotting (a piece of filter paper draws away most of the liquid film, leaving 50–100 nm of buffer across the grid holes), then plunge — the grid drops at high speed into a small reservoir of liquid ethane held at −180 °C by a surrounding bath of liquid nitrogen. The plunge takes a few hundred milliseconds. The buffer film vitrifies — freezes faster than ice crystals can nucleate, locking the ribosomes in random orientations within an amorphous-ice glass.

The grid is now a vitrified specimen. It cannot warm above ~−140 °C without crystalline ice forming, which would destroy the structure. The student transfers it under liquid nitrogen to a cryo-holder, then into the TEM, where it stays at cryogenic temperature throughout imaging. The TEM operator runs a low-dose protocol (Chapter 19) — search at low magnification to find good ice, focus on a tracking area away from the imaging target, then expose the imaging area for 1–3 seconds at 30–50 electrons per Å². Each acquisition captures hundreds to thousands of ribosome projections in random orientations, frozen mid-step in their function.

A few months and a few terabytes of data later, the student's analysis software has classified the projections, aligned them, and reconstructed a 3D density map at 2.8 Å resolution. The ribosome's individual atoms are not quite visible at that resolution, but the atomic backbone of every ribosomal protein and the RNA helices are clear. The structure was determined from 200,000 individual ribosomes, each one a snapshot from the original purified suspension, none of them ever heated above cryogenic temperature, none of them ever fixed by chemicals.

This is what cryo-EM does. By the end of this chapter you understand vitrification as method extension of the biological prep pipeline, can recognize the components of a cryo-EM workflow, and can read a published cryo-EM paper at the level of "what they did and why."

### Learning objectives

By the end of this chapter you can:

- **Explain** vitrification as freezing fast enough to bypass ice-crystal formation.
- **Identify** the components of a cryo-EM workflow: vitrification, cryo-holder, low-dose imaging, motion correction, alignment, classification, reconstruction.
- **Recognize** common cryo-EM artifacts: crystalline ice, thick ice, beam-induced motion, charging in vitreous ice, preferred orientation.
- **Read** an SPA paper at the level of identifying dose budget, particle count, resolution claim, and the limitations the authors acknowledge.
- **Choose** between cryo-EM and conventional TEM (Chapter 20) for a given structural-biology question.

### Prerequisites

Chapter 20 (biological TEM prep, including HPF/FS introduction). Chapter 19 (low-dose TEM, tomography). Chapter 13 (cryo-holders mentioned). Some structural biology: protein architecture, complexes, why averaging across copies of the same molecule reduces noise.

### Why this chapter matters

Cryo-EM has captured several Nobel Prizes in the past decade [verify] and is now the dominant structure-determination technique for membrane proteins, large complexes, and dynamic assemblies. Reading current structural-biology and nanomedicine literature requires understanding the cryo-EM pipeline at this orientation level.

---

## 2. Vitrification: freezing without crystals

The question this section answers is: how do you freeze a hydrated specimen so quickly that ice crystals do not form, and why does that matter?

### Mechanism — outpace nucleation

Pure water has a thermodynamically preferred state below 0 °C: crystalline ice. The first ice crystals form when water cools through the freezing point. Once they form, they grow rapidly, packing molecules into a regular hexagonal lattice. The crystallization process disrupts any structure that was in the water, including biological structures — proteins crushed between growing ice crystals, lipid membranes shredded, hydration shells stripped.

Vitrification escapes crystallization by **kinetic competition**. If the water cools fast enough — typically faster than $10^4$ °C/s [verify] — molecules do not have time to reorganize into the crystalline lattice before they immobilize. The result is **amorphous ice** (or **vitreous ice**, from Latin *vitrum*, "glass"): water frozen in the random orientation it had as liquid, locked in place without crystal formation. The glassy water preserves the structures dispersed in it.

For thin films of buffer (~50–100 nm thick), plunge-freezing into liquid ethane at −180 °C achieves cooling rates faster than $10^5$ °C/s [verify] — well above the vitrification threshold. Water films thicker than ~1 μm cannot vitrify uniformly by simple plunge freezing; the surface freezes fast, the interior cannot keep up, and crystalline ice forms in the deeper regions. This is why **plunge freezing** works for thin specimens (single particles in solution) and **high-pressure freezing** (Chapter 20) is needed for thicker tissue.

### The plunge-freezing instrument

Modern cryo-EM uses an automated plunger (the Vitrobot is one common brand; other manufacturers exist):

```
PROCEDURE — Plunge-freezing for cryo-EM grid prep

1. Glow-discharge a holey-carbon TEM grid for hydrophilization
   (Chapter 20's glow-discharge step is the same).
2. Apply 3-4 μL of purified specimen suspension to the grid.
3. Insert grid into plunger humidity chamber (high humidity, ~85-95%
   RH; temperature 4-8 °C).
4. Blot for 2-5 seconds with filter paper to leave thin film.
5. Plunge into liquid ethane (held by surrounding LN2 bath at -196 °C).
6. Transfer the vitrified grid to LN2 storage; never warm above -140 °C.
```

Liquid ethane at −180 °C is colder than its melting point; it does not freeze immediately on contact with the warm grid. This is why ethane works better than direct LN2 (which would form an insulating gas film around the warm grid, slowing the cooling rate).

### Hazards and Safe Practice

**Liquid ethane** is hazardous. At −180 °C it is a contact-burn risk; vapor displaces oxygen in confined spaces (asphyxiation hazard); liquid ethane is *flammable* — a vial of liquid ethane near an ignition source is a fire hazard. The combined risks make ethane handling a serious operator-safety topic:

- Use only in a fume hood or well-ventilated workspace.
- No ignition sources nearby (no flames, no soldering irons, no static-electric charges).
- Standard cryogen PPE: face shield, cryo gloves, lab coat.
- Dispose of contaminated ethane carefully — small spills may be allowed to evaporate in the hood; large spills are emergency-response situations.

**Liquid nitrogen** for cryo-handling is the routine cryogen — cold burn risk, asphyxiation in confined spaces. Cross-reference Chapter 13.

**Vitrification accidents** include: pre-mature warming (loss of vitreous ice), spill of molten cryogen, contamination of the grid with liquid nitrogen frost. None are catastrophic if handled with normal cryo-discipline; all are time-consuming to recover from.

For comprehensive treatment, see **Appendix A**.

### Trade-off

Vitrification optimizes for **native-state structural preservation at the cost of cryogenic discipline throughout the workflow**. Once the specimen is vitrified, every subsequent step must keep it cold — no warming above ~−140 °C without inducing crystalline ice. The cost is the cold-chain logistics: cryo-storage, cryo-transfer, cryo-holder, cryo-stage. The reward is preservation of conformations that conventional fixation cannot reach (membrane proteins in lipid bilayers, transient-state assemblies, dynamic complexes).

### What Goes Wrong Here

- **Crystalline ice formation.** Vitrification failed; the ice is hexagonal or cubic ice instead of amorphous. Recognition: clear diffraction rings on the SAED of the ice region (vitreous ice gives only diffuse halos). Fix: faster cooling, thinner ice, fresh ethane.
- **Ice contamination.** Cracks, frost, or dust on the grid surface. Recognition: bright crystalline structures in the imaging area. Fix: cleaner grid handling; cryo-cycler grid storage.
- **Thick ice.** The buffer was not blotted enough. Recognition: dim, low-contrast images. Fix: longer blot times; specific blot paper.
- **Devitrification on warming.** Specimen warmed above −140 °C accidentally. Recognition: fine granular crystalline ice appearing where smooth vitreous ice had been. Fix: re-vitrify the specimen.

---

## 3. Cryo-imaging in the TEM

The question this section answers is: how do you image a vitrified specimen at cryogenic temperature, and what new constraints does cryo-imaging introduce?

### Mechanism — cryo-holder, cold stage, low-dose discipline

A **cryo-holder** is a specimen holder with a built-in liquid-nitrogen reservoir that keeps the specimen at cryogenic temperature inside the TEM column. Standard cryo-holders cool to ~−175 °C; specialized helium-cooled holders reach −250 °C or lower [verify]. The holder accepts a vitrified grid via a cryo-transfer station (a small antechamber maintained under LN₂) and mounts it in the column without warming.

Once mounted, the specimen sees only the imaging electrons — the rest of the column geometry stays at cryogenic temperature throughout the session. Standard cryo-EM sessions last 8-72 hours during which the cryo-holder is continuously refilled with liquid nitrogen.

**Low-dose discipline** (Chapter 19) is non-negotiable for cryo-EM. Vitrified biological specimens damage at very low total doses (~50–100 electrons/Å² for room-temperature imaging; a similar threshold at cryo despite the ~10× radiation-damage tolerance increase from low temperature [verify]). The three-area protocol (search, focus, exposure) is standard.

The week-12 source described HPF + FS as related cryo-prep techniques (Chapter 20). HPF is for thicker tissue; plunge-freezing is for thin biological suspensions (single-particle work, viruses, bacteria, liposomes).

### Direct-electron-detection cameras

Cryo-EM single-particle reconstruction reached its current capability in part because of **direct-electron-detection (DED) cameras** (Chapter 13). Three properties of DEDs that matter for cryo-EM:

- **High DQE.** Detective quantum efficiency captures more of the limited information per electron than scintillator-CCD cameras.
- **Frame-by-frame readout.** A 2-3 second exposure is recorded as 30-50 frames at ~10 fps. Software aligns the frames before summing, correcting for **beam-induced motion** (the specimen moves slightly under the beam in the first second of exposure).
- **Low noise.** DEDs add less electronic noise than indirect-detection cameras.

Together, DEDs increased the resolution achievable from cryo-EM SPA from ~1 nm pre-2013 to <0.3 nm now [verify]. This is the engine of cryo-EM's recent ascent.

### What Goes Wrong Here (cryo-specific)

- **Beam-induced motion** in the first 1-2 e/Å² of exposure. Specimen lurches under the beam. Mitigation: motion correction in DED frames; reject the first frames if motion is severe.
- **Charging in vitreous ice.** Cryo-specimens charge differently from dehydrated specimens; vitreous ice itself is poorly conducting. Recognition: streaks or instability in long exposures. Mitigation: LN₂-cold conductive coating on the grid; thinner ice.
- **Preferred orientation.** Particles in vitreous ice can preferentially orient at the air-water interfaces (top and bottom of the thin film) rather than randomly. Recognition: SPA reconstruction shows artifacts in directions orthogonal to the preferred orientation. Fix: detergent additives to break interface preferences; tilted-grid imaging.

---

## 4. Single-particle analysis: a reader's overview

The question this section answers is: how does cryo-EM go from individual low-SNR images to a 3D atomic-resolution structure, and what should a reader know to evaluate an SPA paper?

> **Scope reminder:** this section is *introductory framing only*. A reader pursuing actual SPA work needs Frank, *Three-Dimensional Electron Microscopy of Macromolecular Assemblies*, Oxford, current ed. — and ~6 months of computational training.

### Mechanism — averaging across thousands of randomly oriented copies

Each cryo-EM micrograph captures hundreds to thousands of individual macromolecular complexes (e.g., ribosomes, viruses, membrane proteins) embedded in vitreous ice. Each complex is a single copy of the same molecule, but each one is in a different orientation in the ice — random rotations across the field. Each one is a 2D projection of the 3D structure from a different angle.

Single-particle analysis exploits this by:

1. **Particle picking.** Identify each individual complex in the micrograph (manual or automated).
2. **Per-particle CTF correction.** The contrast transfer function (CTF, the optical transfer function of the lens at a given defocus) modulates each particle's signal differently depending on local defocus. Software corrects.
3. **2D classification.** Cluster particles by orientation similarity. Particles in the same orientation get aligned and averaged together. The result: 2D class averages with much higher SNR than individual particles.
4. **3D classification and ab-initio reconstruction.** From the 2D classes, software constructs an initial 3D model. Particles are then classified by which 3D conformation (or orientation) they belong to. Multiple 3D classes can emerge if the specimen has dynamic conformations.
5. **3D refinement.** The 3D model is iteratively refined by re-projecting it, comparing to the 2D class averages, and adjusting. The cycle continues until the model stabilizes.
6. **Resolution estimation.** Measure how well the model agrees with the data; report a resolution metric (Fourier shell correlation, FSC).
7. **Atomic model fitting.** If resolution is sufficient (~3 Å or better), an atomic model can be fit into the density map.

### Why averaging works

Each individual particle image has terrible SNR — a few hundred electrons per square Å, on a ribosome that is ~25 nm in diameter. Most pixels are dominated by noise. But the noise is uncorrelated between particles, and the signal is correlated (the same molecule, same structure). Averaging $N$ particles reduces the noise by $\sqrt{N}$ while preserving the signal. With $10^5$ particles, the SNR improves by ~300×. This is why SPA can reach atomic resolution despite the low-dose constraint.

### Resolution claims

When a cryo-EM paper claims "2.8 Å resolution," what does that mean? Several conventions exist [verify]; the most common is the **Fourier Shell Correlation (FSC) at 0.143 cutoff**: the resolution at which the FSC between two halves of the dataset (independent reconstructions) drops to 0.143. This convention is widely accepted [verify]; it gives a number that roughly corresponds to "the spatial scale at which features become unreliable."

A 2.8 Å resolution map can show side chains for many amino acids; a 4 Å map shows the protein backbone but not side-chains; a 7 Å map shows secondary structure (α-helices, β-sheets) but not backbone; a 12 Å map shows overall shape only.

### Trade-off

Cryo-EM SPA optimizes for **near-native-state atomic-resolution structures at the cost of computational complexity, particle count, and specimen optimization**. A typical SPA project requires:
- 10⁵ to 10⁶ particles.
- Multi-day TEM sessions.
- Significant computational time (often days on GPU clusters).
- Months of optimization to find conditions that produce good ice with good particle distribution.

For some questions, the reward is structures that no other technique provides. For other questions, X-ray crystallography or NMR may be faster or cheaper.

### What Goes Wrong Here (SPA-specific)

- **Heterogeneous specimens.** Some molecules are in different conformations; classification splits them. Recognition: 3D classification produces multiple classes with different shapes. Fix: better biochemistry to homogenize the sample, or accept the heterogeneity and characterize multiple conformations.
- **Preferred orientation.** Particles biased toward certain orientations; reconstruction has anisotropic resolution. Recognition: FSC at low resolution in some directions, high in others.
- **Wrong resolution claims.** Authors report a single FSC number that may not reflect the resolution in all parts of the structure. Fix: report local-resolution maps; check the methods section for FSC details.

---

## 5. Synthesis: where cryo-EM lives in the technique landscape

Cryo-EM is the right tool when the research question requires:

- **Native hydrated state** of a biological specimen. Vitrification preserves it; chemical fixation does not.
- **High-resolution 3D structure** of a macromolecular complex (ribosome, membrane protein, virus capsid, large ATPase).
- **Multiple conformational states.** SPA classification can resolve different states from the same dataset.
- **Specimens that resist crystallization.** Many membrane proteins crystallize poorly for X-ray; cryo-EM does not require crystals.

Cryo-EM is *not* the right tool when:

- **Surface morphology is the question** — SEM or VP-SEM (Chapter 10).
- **Bulk material composition is the question** — EDS in conventional SEM/TEM.
- **Live/dynamic processes** are the question — fluorescence microscopy.
- **Atomic-resolution position of every atom** is required — X-ray crystallography may give better resolution if crystals can be grown.

For nanomedicine, cryo-EM has become essential: most high-resolution structures of drug-target complexes from the last few years are cryo-EM structures. For nanoparticle work — especially lipid nanoparticles for mRNA delivery — cryo-EM in conjunction with cryo-tomography (Chapter 19) provides 3D structural information unavailable from any other technique.

### Putting it all together (worked synthesis)

A nanomedicine PI brings 200 nm lipid nanoparticles loaded with mRNA. Goals:
- (a) Confirm the lipid-bilayer structure.
- (b) Determine if the mRNA is in the core or membrane-associated.
- (c) Compare empty and loaded particles.

Plan:
- **Plunge-freeze** the samples. Optimize ice thickness and particle distribution (likely several iterations; weeks of work).
- **Cryo-TEM** at low dose. Image hundreds of particles per micrograph; document distribution.
- **Cryo-tomography** (Chapter 19) on a single particle. 3D reconstruction shows mRNA location relative to bilayer.
- **2D class averaging** of empty vs loaded particles. Comparative population statistics.
- **3D SPA** if particle homogeneity allows.

Three to six months of work for full structural characterization. The lab's confidence in the drug-delivery mechanism comes from this kind of detailed cryo-EM.

### Scale shift

Cryo-EM bridges scales remarkably. The Vitrobot's blotting paper takes 2-3 seconds; the plunge into ethane takes 200 milliseconds; the cooling-front velocity inside the freezing droplet is millimeters per second [verify]; the molecular motion time of ribosomal proteins at room temperature is picoseconds. By plunging fast enough, cryo-EM freezes a snapshot taken on the picosecond timescale of biology, locking it into a glass that can be probed at angstrom resolution months later. The wonder is that the technique works at all — that water's natural inclination to crystallize can be outpaced by sufficiently fast cooling.

---

## 6. Pre-lab Checklist (Lab 21 — cryo-EM grid prep and imaging)

**By the end of this chapter, you should be able to:**

- Describe the vitrification process and identify when it works versus fails.
- Use a Vitrobot or equivalent plunger to prepare a cryo-EM grid (under supervision).
- Recognize cryo-imaging artifacts: crystalline ice, thick ice, beam-induced motion.
- Read an SPA paper's methods at the level of dose budget, particle count, resolution claim.

**Bring to lab:**

- This chapter, especially Sections 2 and 3.
- A purified specimen suitable for plunge-freezing (typically provided by the lab).

**Expect on the floor:**

- A Vitrobot demonstration; possibly a hands-on grid prep under supervision.
- A first cryo-TEM session: cryo-holder loading, low-dose imaging, observation of vitreous ice.
- A discussion of an SPA paper's claimed resolution and how to evaluate it.

### Hazards and Safe Practice (cryo-specific)

In addition to the conventional TEM hazards (Chapters 13, 20):

- **Liquid ethane.** Cold burn, asphyxiation, and **flammability**. Detailed protocol:
  - Use only in fume hood with no ignition sources.
  - Cryo-gloves and face shield mandatory.
  - Liquid ethane vials sealed when not in use.
  - Disposal protocol: small spills allowed to evaporate in the hood; large spills are emergency-response.
- **Liquid nitrogen** for grid handling, holder cooling, and storage. Standard cryogen safety: face shield, cryo gloves, ventilation. Asphyxiation risk in confined spaces.
- **Asphyxiation in cryogen-rich rooms.** A small spill of LN₂ in a closed room can rapidly displace breathable oxygen. Adequate ventilation, oxygen monitor if available.

For comprehensive treatment, see **Appendix A**.

---

## 7. Quick-Reference Table

| Step | Reagent / equipment | Temperature | Notes |
|---|---|---|---|
| Glow discharge | air or H₂/O₂ plasma | RT | hydrophilizes carbon |
| Specimen application | 3-4 μL droplet | 4-8 °C | onto holey carbon grid |
| Blot | filter paper | RT to chamber temp | 2-5 s typical |
| Plunge | liquid ethane | -180 °C | fast plunge ~200 ms |
| Storage | LN₂ | -196 °C | cryo-storage indefinitely |
| Transfer | cryo-transfer station | < -140 °C | maintain throughout |
| Imaging | cryo-holder in TEM | < -150 °C | typical |

| Resolution range | What's visible (cryo-EM map) |
|---|---|
| 12+ Å | overall shape only |
| 7-12 Å | secondary structure (α-helices, β-sheets) |
| 4-7 Å | protein backbone trace |
| 2.5-4 Å | side chains, atomic backbone |
| < 2.5 Å | full atomic model |

| Dose budget (cryo-EM) | Per-image | Total (SPA) | Total (Cryo-ET) |
|---|---|---|---|
| Conservative | 30 e/Å² | 50-70 e/Å² | 70-100 e/Å² |
| Standard | 30-50 e/Å² | 50-100 e/Å² | 100-150 e/Å² |

[verify all]

---

## 8. Exercises

### Warm-up

**Exercise 21.1 (LO: distinguish vitrification from crystallization).**
Why is liquid ethane used as the cryogen for plunge-freezing rather than liquid nitrogen directly? Difficulty: easy.

**Exercise 21.2 (LO: identify artifact).**
A cryo-EM micrograph shows discrete diffraction rings overlaying the specimen. What artifact is this, and what is the cause? Difficulty: easy.

**Exercise 21.3 (LO: understand averaging).**
If averaging $N$ particles reduces noise by $\sqrt{N}$, how many particles need to be averaged to improve SNR by 100×? Difficulty: easy.

### Application

**Exercise 21.4 (LO: choose between cryo-EM techniques).**
For each goal, choose plunge-freezing, HPF/FS, or conventional fixation: (a) image purified ribosome structure at high resolution, (b) image cellular ultrastructure of mouse liver, (c) image a 200-nm lipid nanoparticle in 3D. Difficulty: medium.

**Exercise 21.5 (LO: evaluate resolution claim).**
A paper reports cryo-EM SPA resolution of 3.2 Å using FSC at 0.143 cutoff with 250,000 particles. Predict what features should be visible in the map and what should not. Difficulty: medium.

**Exercise 21.6 (LO: identify cryo artifact).**
A cryo-EM image of ribosome particles shows that particles preferentially appear in one orientation on the grid. What is the artifact, and how would you address it? Difficulty: medium.

**Exercise 21.7 (LO: design SPA workflow).**
A graduate student has purified membrane protein at 1 mg/mL. Outline the cryo-EM SPA workflow from grid prep through 3D reconstruction. Specify approximate timeline. Difficulty: medium.

### Synthesis

**Exercise 21.8 (LO: integrate cryo-EM with prior chapters).**
A nanomedicine PI studies lipid nanoparticles that delivery mRNA to cells. The PI needs: (a) confirm bilayer structure, (b) localize mRNA inside the particle, (c) compare empty vs loaded particle morphology, (d) measure particle size distribution at the population level. Specify a multi-technique workflow combining cryo-TEM, cryo-tomography (Chapter 19), and conventional methods (Chapter 20). Difficulty: hard.

### Challenge

**Exercise 21.9 (open-ended).**
Find a recent published cryo-EM SPA paper. Identify in the methods section: dose budget, particle count, resolution metric, software pipeline. Comment on whether the claimed resolution is consistent with the data presented. Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter with cryo-EM as a vague technique. You walk out with the workflow: vitrification, cryo-imaging at low dose, single-particle analysis (or tomography). You can recognize the artifacts and read a published paper at orientation level.

The one idea that matters most: cryo-EM is not a separate microscope; it is a method extension of conventional biological TEM (Chapter 20) plus low-dose imaging (Chapter 19) plus vitrification (this chapter). The combined discipline is what produces atomic-resolution structures of native biological complexes.

The common mistake to watch for: treating cryo-EM as a turnkey technique. The optimization of grid conditions, ice quality, and particle distribution typically takes months of work before usable data appears. Reading a finished paper does not show this overhead.

The Feynman test: explain to a labmate, without using the word "vitrification," why a biological specimen for cryo-EM must be frozen so quickly.

---

## 10. Connections Forward

Chapter 22 covers the analogous prep pipeline for inorganic specimens — different physical chemistry, same conceptual structure. Chapter 23 returns to artifact recognition with cryo-EM specific artifacts in the synthesis. Chapter 25 covers cross-technique applications including cryo-EM as part of multi-technique nanomedicine workflows.

The question this chapter raised but did not answer: how do you actually thin a hard inorganic specimen to TEM electron-transparency without the chemical and biological discipline this chapter assumed? Chapter 22 covers it.

---

**What would change my mind:** evidence that conventional chemical fixation could match cryo-EM for membrane-protein structural work. The empirical record consistently shows cryo-EM preserves conformations chemical fixation does not. The resolution gap, post-DED, is also large.

**Still puzzling:** the practical decision of when to invest the months of optimization needed for a cryo-EM project versus when to use conventional methods is mostly intuition-driven. Some labs invest heavily and succeed; others go through the cycle without good outcomes. The factors that predict success are not fully formalized.

**Tags:** `cryo-EM`, `vitrification`, `single-particle-analysis`, `low-dose`, `structural-biology`

---

### Note to the professor

`[verify]` markers in this chapter:
- Specific cooling rate threshold for vitrification ($10^4$ to $10^5$ °C/s).
- Beam-induced motion characterization.
- Cryo-holder cooling temperature ranges.
- DED resolution improvements from ~1 nm to <0.3 nm.
- FSC 0.143 convention for resolution.
- Specific dose-budget figures.
- Cryogen-handling specifics.
- Nobel-prize timing for cryo-EM.

This chapter is built from week-12 (HPF/FS as cryo-prep), week-11 (low-dose), and standard cryo-EM textbook material. Several technical details are convention-dependent; the professor should verify against current literature.

Voice anchoring: anchored. Vitrobot chapter opening (one scene only). Capability ending. Hazards callout for cryogens including liquid ethane. Wonder grounded in numbers (200 ms plunge time; $10^4$-$10^5$ °C/s cooling rate; 200,000 particles for atomic-resolution; 6 months optimization). Length ~5500 words.

The scope-discipline note at the top of the chapter is preserved per book.md authoring rules: SPA is introductory framing only, not a full how-to. The reader is prepared to *understand* an SPA paper, not *run* one.
