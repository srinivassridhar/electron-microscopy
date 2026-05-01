# Chapter 22 — TEM Sample Preparation for Inorganic and Materials Science Specimens

## Title options

1. **Thinning the Hard Stuff: TEM Prep for Metals, Ceramics, and Semiconductors**
2. **From Bulk to Lamella: Inorganic TEM Prep Techniques**
3. **The Many Routes to Electron Transparency**

## TL;DR

Inorganic TEM specimen preparation has several distinct routes — mechanical polishing, electrochemical polishing, ion milling, and FIB lift-out — chosen by material hardness, conductivity, and spatial specificity needs. The single goal across all routes: 3 mm disc-shaped specimens, less than 100 nm thick at the imaging area, with minimal preparation-induced artifacts.

---

## 1. Chapter Opening

A graduate student carries a small chunk of stainless steel — about 5 mm × 5 mm × 1 mm thick — to the TEM prep lab. Goal: image dislocations in the steel by TEM. The bulk specimen is far too thick for the beam to penetrate; somehow, the student needs to thin it to less than 100 nm at the imaging area while preserving the dislocation structure. The full prep pipeline:

1. **Cut a 3 mm disc** from the slab using an ultrasonic disc cutter or a diamond wire saw. The disc is the size that fits a TEM grid holder.
2. **Mechanically thin** the disc to about 100 μm using a tripod polisher with progressively finer grit.
3. **Dimple grind** the center of the disc to about 10 μm thickness while leaving the rim at 100+ μm for mechanical strength.
4. **Final thinning by ion milling.** Argon ions at low angle remove a few atomic layers per minute, eventually perforating the dimple. The region around the perforation, just before final breakthrough, is electron-transparent (<100 nm).

Three days of work. The student loads the now-perforated disc into a TEM holder, finds the thinned region near the hole, and at 200 kV bright-field sees individual dislocations as fine dark lines crossing the steel grains. Each step in the prep was necessary; skipping any step would have left the specimen too thick or too damaged for the imaging the student wants.

Inorganic TEM prep is a different beast from biological TEM prep (Chapter 20). No fixation, no dehydration, no resin embedding — but mechanical, ionic, and electrochemical thinning chains that take their own days of work. By the end of this chapter you can choose a prep route for a given specimen and predict the artifacts each route produces.

### Learning objectives

By the end of this chapter you can:

- **Identify** the four major prep routes for inorganic TEM specimens: mechanical, electrochemical, broad-ion-beam milling, FIB lift-out.
- **Choose** an appropriate route based on material properties (hardness, conductivity, magnetism) and research question.
- **Recognize** prep-induced artifacts: ion-milling amorphization, electropolishing pitting, FIB curtaining, polymer microtomy chatter.
- **Plan** a multi-step prep workflow combining routes (e.g., dimple + ion mill, FIB lift-out + cleanup pass).
- **Apply** safety procedures for hazardous prep chemistries (electropolishing electrolytes, ion-mill operation).

### Prerequisites

Chapter 20 (biological TEM prep, for the conceptual contrast). Chapter 10 (FIB-SEM, since FIB lift-out is now a major prep method). Chapter 12 (TEM thin-specimen requirement).

### Why this chapter matters

Materials-science TEM is a different specimen-prep ecosystem from biological TEM. Each material class has its preferred routes; a student of materials microscopy must navigate all of them. Cross-cutting prep questions (e.g., "should I use mechanical polishing then ion mill, or skip to FIB?") have practical and quality consequences.

---

## 2. Specimen requirements and the disc-shaped target

The question this section answers is: what is the universal target shape for inorganic TEM specimens, and what does each requirement constrain?

### Mechanism — six requirements per the source

Per the week-13 source, all inorganic TEM specimens must satisfy:

1. **Thin (<100 nm)** for electron transparency at typical TEM voltages.
2. **Uniform thickness** across the area of interest, so contrast variations come from specimen features not from thickness gradients.
3. **Clean** — free of polishing residues, embedding compounds, or dust.
4. **Representative** — the prepared region must reflect the bulk material's properties, not a localized artifact zone.
5. **Stable under the beam** — the specimen must survive electron exposure without degrading.
6. **Conducting and nonmagnetic** — magnetic specimens deflect the beam; nonconducting specimens charge.

These constraints interact. A magnetic specimen (e.g., ferritic steel) can sometimes be thinned to a region small enough that its residual field is acceptable; alternatively, the magnetic phase can be embedded in a nonmagnetic matrix. A perfectly conducting metal needs no coating but may be too soft to support the prep itself. A ceramic is brittle and may shatter during sectioning. Each material's constraints shape the prep choice.

The universal target: a **3 mm diameter disc**, with the imaging region thinned to electron transparency. The 3 mm size matches the TEM holder. Most preparation pipelines work backwards from this disc geometry.

### Three categories of specimens

The source organizes specimens into three categories by their starting shape and required handling:

- **Powders, nanoparticles, and fibers** — small particulates, prepared by dispersion onto a grid (Chapter 8 SEM-prep parallels).
- **Bulk samples** — solid specimens (metals, ceramics, semiconductors) that must be cut to disc and thinned.
- **Thin films** — already deposited as a film on a substrate; the substrate must be removed or the film selectively thinned.

Each category routes through a different combination of techniques. Most of this chapter focuses on bulk-specimen prep, the most common case in materials science.

### Trade-off

Inorganic TEM prep optimizes for **specimen-state preservation at the cost of multi-step processing time**. Each step introduces some artifact; the operator's goal is to choose steps whose artifacts are tolerable for the question being asked. For high-resolution imaging, the cleanest possible final region matters; for survey imaging, faster prep with more residual artifacts is acceptable.

### What Goes Wrong Here

- **Insufficient thinning.** Specimen too thick at imaging area; image dim and low-contrast. Recognition: at 200 kV BF, if the image looks washed out and lacks fine detail, the specimen probably exceeds 200 nm. Fix: longer ion mill, more dimpling.
- **Over-thinning.** Hole is too big or imaging area is destroyed by thinning. Recognition: the perforation extended into the specimen of interest. Fix: stop sooner; better real-time monitoring.
- **Contamination.** Polishing media, embedding residue, or fingerprints. Recognition: amorphous halos in BF; spurious EDS peaks. Fix: ultrasonic clean; fresh polishing materials; gloves.

---

## 3. Mechanical preparation: cutting, dimpling, polishing

The question this section answers is: how do you bring a bulk specimen down to ~100 μm by purely mechanical means, and what artifacts does that introduce?

### Mechanism — saw, grind, polish, dimple

The mechanical pipeline:

```
PROCEDURE — Mechanical thinning

1. CUT to 3 mm disc.
   - Diamond wire saw (MicroSaw-style) for hard ceramics or
     semiconductors. Slice thickness ~100-200 μm.
   - Ultrasonic disc cutter for brittle materials. Tubular blade
     vibrates and cuts down through the slab.
   - For metals: diamond saw or shear-press disc punch.

2. THIN with grinding paper.
   - Sequence: 60, 120, 240, 320, 400, 600 grit silicon carbide.
   - Wet grinding to prevent thermal damage and clear debris.
   - Each grit removes the previous one's damage.
   - Final thickness ~100 μm typical.

3. POLISH with diamond suspension.
   - 30 μm, 9 μm, 3 μm, 1 μm sequence.
   - Final polish at 0.05 μm colloidal silica.
   - Result: surface roughness <50 nm, suitable for further thinning.

4. DIMPLE.
   - Specialized instrument with rotating diamond wheel that creates
     a dimple at the center of the disc.
   - Center thickness ~10 μm; rim thickness ~100 μm for mechanical strength.
   - Dimple greatly reduces the time needed for ion milling later.

5. (Optional) TRIPOD POLISHING.
   - Three-point polishing head for ultra-fine final thinning.
   - Reaches ~100 nm thickness directly on appropriate materials.
   - Replaces ion milling for some specimens.
```

The week-13 source describes each step in detail. The mechanical pipeline alone can reach ~100 nm for some materials; for most, it serves as preparation for ion milling or FIB.

### Polymer materials

Mechanical thinning of polymers is challenging — the material is soft and tends to compress rather than thin uniformly. The source notes that ultramicrotomy can be used for polymer cross-sections, with the same artifacts (chatter, knife marks) as biological ultramicrotomy.

### Magnetic nanoparticles

Magnetic specimens contaminate the TEM column if loose particles deposit on the polepiece. The source notes that magnetic particles can be embedded in epoxy resin and ultramicrotomed — the resin holds the particles in place, eliminating the contamination risk while still allowing electron-transparent sections.

### Trade-off

Mechanical preparation optimizes for **direct material handling at the cost of mechanical damage**. The grinding and polishing steps deform the specimen surface — work-hardening for metals, dislocations for crystals, sub-surface damage that extends below the visibly polished surface. For many questions this is irrelevant; for high-resolution structural work near the surface, ion milling or FIB is needed to remove the damaged layer.

### What Goes Wrong Here

- **Surface scratches from coarse grit.** Recognition: parallel lines crossing the imaging region. Fix: more polishing time at finer grits.
- **Sub-surface damage from mechanical work.** Recognition: dense dislocation networks in BF that don't represent the bulk. Fix: ion milling to remove the damaged layer.
- **Dimple too thin or too thick.** Recognition: ion milling either perforates immediately (too thin) or takes hours (too thick). Fix: better dimple-depth monitoring; calibrate against material-specific ranges.

---

## 4. Electrochemical preparation: jet electropolishing

The question this section answers is: how do you thin a metal specimen without mechanical work-hardening?

### Mechanism — anodic dissolution

**Jet electropolishing** uses an electrochemical cell to remove material from a metal specimen. The specimen is the anode of a DC circuit; an electrolyte (typically a concentrated acid or acid mixture) is the medium; a cathode (often platinum or stainless steel) closes the circuit. Current flows; metal at the anode dissolves into the electrolyte; the cathode produces hydrogen.

In a **jet electropolisher**, the electrolyte is jetted onto the anode at controlled pressure, often while the anode rotates or tilts. The jets concentrate the electrochemical action at the specimen's center, creating a perforation that begins from the center. The region just before perforation is electron-transparent.

```
PROCEDURE — Jet electropolishing

1. Mount the 3 mm disc (already mechanically thinned to ~100 μm).
2. Fill the cell with the appropriate electrolyte for the material.
3. Set voltage and current per material-specific calibration.
4. Apply jets; monitor perforation by light transmission through
   the specimen.
5. When light transmits, terminate immediately.
6. Remove specimen, rinse in solvent (often methanol or water + alcohol).
7. Dry; load into TEM.
```

Common electrolytes [verify all]:
- Iron / steel / nickel: perchloric acid + acetic acid (Struers A2-style).
- Aluminum: perchloric acid + ethanol.
- Copper: phosphoric acid + ethanol.

**Electrolyte choice depends on the material**, and using the wrong electrolyte produces poor polishing or hazards.

### Hazards and Safe Practice

Electropolishing electrolytes are seriously hazardous chemistries:

- **Perchloric acid + alcohols are explosive when mishandled.** The acid is a strong oxidizer; alcohols are fuel. The mixture is stable at controlled temperature but can detonate from heat, friction, or contamination. Strict protocols apply: published recipes, controlled temperatures, no organic mineral oils on equipment.
- **Acid burns** from concentrated electrolytes.
- **Hydrogen evolution at the cathode** is flammable in confined spaces.
- **Toxic fumes** from many electrolytes.

PPE: face shield, acid-resistant gloves, lab coat, fume hood. Never improvise an electropolishing recipe; always use published protocols. Cross-reference Appendix A.

### Trade-off

Electropolishing optimizes for **damage-free thinning of conducting metals at the cost of electrolyte hazards and material restrictions**. No mechanical work-hardening; surfaces are smooth. But electropolishing only works on conducting specimens (does not work on ceramics or insulators); each material has its own electrolyte; the chemistry is dangerous.

### What Goes Wrong Here

- **Pitting at the perforation.** Recognition: perforation has irregular ragged edges; thin region is uneven. Fix: better jet alignment, fresher electrolyte, lower current density.
- **Premature perforation.** Specimen perforates before reaching the thin region the operator wanted. Fix: shorter polish times; better real-time monitoring.
- **Surface contamination from electrolyte residue.** Recognition: amorphous deposits on the thinned region. Fix: thorough rinsing; switch electrolytes if residue persists.

---

## 5. Ion-beam milling

The question this section answers is: how do you reach the final 100 nm thickness using a non-mechanical, non-chemical method?

### Mechanism — argon ions at glancing angle

**Broad ion beam milling** (precision ion polishing, PIPS) uses a beam of argon ions to sputter atoms from the specimen surface (Chapter 10 introduced sputtering for FIB).

For TEM thinning, ions hit at a shallow angle (~5° from surface, per week-13 source), which:
- Maximizes sputter yield (Section 10.3 noted yield peaks at 60-80° from surface normal, equivalent to 10-30° from surface).
- Minimizes ion penetration depth into the specimen.
- Produces uniform thinning across a wide area.

```
PROCEDURE — Ion-beam milling

1. Mount the dimpled disc in the ion mill.
2. Set ion energy (typically 3-6 keV for polishing).
3. Set incidence angle (typically 4-8° from specimen surface).
4. Mill until perforation occurs at the dimple center.
5. (Optional) Low-energy cleanup pass at 0.5-1 keV to remove
   amorphized surface layer from the high-energy mill.
6. Remove specimen; load into TEM immediately to avoid contamination.
```

**Final-stage low-energy ion milling** (0.5-1 keV at glancing angle) removes the damaged surface layer and reduces ion-induced amorphization. This is now standard for high-resolution TEM and HRTEM specimens.

### Advantages of ion milling per the source

- **Precise thinning** — controllable to <100 nm.
- **Minimal mechanical damage** — no work-hardening or surface defects.
- **Electron transparency** — produces flat, smooth thinned regions.
- **Versatility** — works on metals, ceramics, semiconductors, polymers, even biological specimens.
- **Site-specificity for FIB** — Chapter 10 covered the localized-thinning aspect.

### Trade-off

Ion milling optimizes for **damage-controlled thinning of any material at the cost of ion-induced amorphization and time**. A typical ion mill for a TEM specimen takes 4-12 hours. The amorphization (first few nm of damaged surface) is unavoidable but reduceable through low-energy cleanup.

### What Goes Wrong Here

- **Ion-implantation amorphization.** Surface few nm becomes amorphous from ion bombardment. Recognition: HRTEM lattice fringes do not extend to the imaged surface. Fix: low-energy cleanup pass.
- **Differential thinning** in multi-phase materials. Different phases sputter at different rates. Recognition: thinning preferentially in soft phases; hard phases remain. Fix: lower angle of incidence; rotation during milling.
- **Surface contamination.** Backstreaming of pump oils or residual gases. Fix: cleaner vacuum; final argon-only mill.

---

## 6. FIB lift-out: site-specific TEM lamellae

The question this section answers is: how do you prepare a TEM specimen from a precise location (a specific transistor, a specific grain, a specific defect)?

### Mechanism — focused ion beam, in-situ manipulator

**FIB lift-out** (introduced in Chapter 10) is the modern site-specific TEM-prep method. The dual-beam FIB-SEM:

1. **Locates the target** in SEM mode at moderate magnification.
2. **Deposits a protective platinum layer** over the target via FIB-induced gas decomposition.
3. **Mills two parallel trenches** alongside the target, leaving a thin "lamella" of specimen between them.
4. **Mills underneath** to release the lamella from the bulk.
5. **Lifts out** the lamella using a micromanipulator (a tungsten needle on an in-vacuum stage).
6. **Mounts** the lamella onto a TEM grid (typically a Cu Omniprobe grid with multiple lift-out positions).
7. **Thins** the lamella by FIB ion-mill to ~50-100 nm at the imaging area.
8. **Final cleanup** at low FIB voltage (~5 keV) to reduce amorphization.

The whole process takes 2-6 hours; modern automated FIBs can run unattended overnight.

### When FIB lift-out wins

- **Site specificity.** Down to ~100 nm precision in lamella position.
- **Hard-to-prepare materials.** Multi-phase, layered, or fragile materials that would shatter under conventional thinning.
- **Localized features.** Specific failures, specific transistors, specific grain boundaries.
- **3D analysis.** Slice-and-view (Chapter 10) builds 3D from sequential FIB sections.

### Trade-off

FIB lift-out optimizes for **site specificity at the cost of ion-beam damage, gallium contamination, and operator skill**. The damaged surface (~5-20 nm of amorphized material with implanted gallium) requires cleanup; the operator skill is non-trivial; the FIB-SEM instrument is expensive ($1M+ class).

### What Goes Wrong Here

- **Curtaining.** Vertical streaks across the lamella's milled face. Recognition: parallel vertical lines at the cross-section. Fix: protective Pt deposition; lower current; specific scan patterns.
- **Redeposition.** Sputtered material lands back on the lamella, creating walls. Recognition: bumpy texture on what should be smooth. Fix: oxygen-assisted etching or higher scan rate.
- **Gallium contamination.** Implanted Ga affects local chemistry and EDS spectra. Recognition: spurious Ga peaks in EDS. Fix: low-voltage cleanup; chemical removal.
- **Ion-beam-induced amorphization.** Surface layer is amorphous, blocks HRTEM. Fix: low-voltage cleanup pass at 5 keV or 2 keV.

---

## 7. Synthesis: choosing a route for the question

The four prep routes — mechanical, electrochemical, broad-ion-beam, FIB lift-out — each have their material and question constraints:

| Specimen / question | Preferred route |
|---|---|
| Powder / nanoparticles | dispersion on grid (Chapter 8 parallel) |
| Bulk metal, dislocation imaging | mechanical + dimple + ion mill |
| Bulk metal, no work-hardening | jet electropolishing (if electrolyte exists) |
| Ceramic | mechanical + dimple + ion mill (or tripod polish) |
| Semiconductor, site-specific feature | FIB lift-out |
| Polymer, internal structure | ultramicrotomy (Chapter 20-style) |
| Multi-phase or layered structure | FIB lift-out |
| Failure analysis | FIB lift-out |
| Magnetic nanoparticles | resin embedding + microtomy |
| Thin film on substrate | careful mechanical thinning + ion mill from substrate side |

### Putting it all together (worked synthesis)

A research group needs to characterize a Si-Ge multilayer device for a memory application:
- (a) Confirm layer thicknesses across a 1 mm × 1 mm area.
- (b) Image a specific failure site identified by electrical testing.
- (c) HRTEM the Si-Ge interface for atomic-level structure.

Plan:
- (a) Cleave the wafer along a [110] direction; mechanically polish the cleaved face to <50 μm; jet electropolish from the wafer side; ion mill to perforation. Several specimens per session.
- (b) FIB lift-out of the failure site with site precision <100 nm. Single specimen per session, 4-6 hours.
- (c) Final low-voltage FIB cleanup of the lift-out lamella to remove amorphous surface, then HRTEM imaging at 200 kV.

Three goals, three different prep routes, all on the same Si-Ge stack. This is typical of materials-TEM workflows.

### Hazards and Safe Practice

The hazards specific to inorganic TEM prep:

- **Electropolishing electrolytes** — perchloric acid, methanol-based solutions, fluorides. Acid burns, explosion risk (perchlorate + alcohol mixtures), toxic fumes. PPE: face shield, acid-resistant gloves, fume hood. Cross-reference Chapter 8 (SEM electropolishing) for additional discussion.
- **Ion mill operation** — high voltage, vacuum implosion, RF interference. Standard TEM-instrument-class hazards. Argon gas cylinder requires standard handling.
- **FIB-SEM operation** — gallium contamination, ion-beam exposure, GIS chemistries. Cross-reference Chapter 10.
- **Polishing slurries** — colloidal silica, alumina suspensions; some are sensitizers. PPE: gloves.
- **Chemical etchants** — material-specific (HF for silicon dioxide, KOH for silicon, etc.). Each requires specific handling; cross-reference SDS sheets.
- **Diamond and glass knives** — same hazards as Chapter 20.

For comprehensive treatment, see **Appendix A**.

### Scale shift

Inorganic TEM prep operates at multiple length scales simultaneously. The 5 mm bulk specimen is reduced through mechanical steps to a 3 mm disc, then to a 100 μm thickness, then to a 10 μm dimple, then to a <100 nm thinned region. Each step reduces the dimension by one or two orders of magnitude. The final imaging area — a few μm² of <100 nm thickness — is the result of compressing five orders of magnitude in length scale through a multi-day chain of techniques. The wonder is that the molecular-scale order of the original material survives.

---

## 8. Pre-lab Checklist (Lab 22 — inorganic TEM prep)

**By the end of this chapter, you should be able to:**

- Choose a prep route for a given inorganic specimen.
- Execute one stage of the prep pipeline (typically dimpling or ion milling) under supervision.
- Recognize prep-induced artifacts in a TEM image.

**Bring to lab:**

- This chapter, especially Sections 3 and 6.
- A pre-cut 3 mm disc of an inorganic material (typically provided by the lab).

**Expect on the floor:**

- A guided dimpling demonstration; possibly hands-on dimpling under supervision.
- A walkthrough of the ion-mill setup and operating cycle.
- A discussion of FIB lift-out for site-specific prep; possibly a cross-lab FIB demo.

---

## 9. Quick-Reference Table

| Step | Method | Typical thickness produced |
|---|---|---|
| Disc cut | diamond saw, ultrasonic cutter | 100-200 μm |
| Mechanical thin | grinding papers (60-600 grit) | 100 μm |
| Polishing | diamond suspensions (30 μm to 0.05 μm) | scratch-free surface |
| Dimpling | dimple grinder | rim 100 μm, center 10 μm |
| Tripod polish | 3-point polishing | ~100 nm direct |
| Jet electropolish | electrolyte, anodic dissolution | <100 nm at perforation |
| Ion milling | Ar at 3-6 keV, 5° angle | <100 nm |
| Low-energy cleanup | Ar at 0.5-1 keV | reduces amorphization |
| FIB lift-out | Ga at 30 keV; cleanup at 5 keV | <100 nm |

| Material | Preferred route(s) |
|---|---|
| Aluminum (soft) | mechanical + ion mill or jet electropolish |
| Steel | mechanical + ion mill or jet electropolish (perchloric) |
| Silicon | mechanical + ion mill (or tripod for thin films) |
| Ceramic | mechanical + ion mill |
| Semiconductor multilayer | FIB lift-out |
| Polymer | ultramicrotomy or FIB |
| Magnetic | resin embed + microtomy |

---

## 10. Exercises

### Warm-up

**Exercise 22.1 (LO: name route).**
For each specimen, name an appropriate prep route: (a) gold nanoparticles in suspension, (b) bulk steel for dislocation imaging, (c) specific transistor in a packaged IC, (d) thin polymer film. Difficulty: easy.

**Exercise 22.2 (LO: identify artifact).**
A TEM image shows the lamella surface with a clear amorphous band at the edges. Cause? Mitigation? Difficulty: easy.

**Exercise 22.3 (LO: order steps).**
Put in correct order for typical bulk-metal prep: ion mill, dimple, polish, cut disc, grind. Difficulty: easy.

### Application

**Exercise 22.4 (LO: design protocol).**
Specify a complete prep protocol for TEM imaging of a polycrystalline ceramic for grain-boundary characterization. Include all steps with timings and termination criteria. Difficulty: medium.

**Exercise 22.5 (LO: choose between routes).**
A multilayer thin film consists of alternating Au and amorphous Si layers each 5 nm thick. Goal: HRTEM image of the interface. Mechanical+ion-mill, electropolish, or FIB? Justify in two sentences. Difficulty: medium.

**Exercise 22.6 (LO: recognize prep failure).**
A jet-electropolished disc has perforated, but the thin region has irregular pitted edges and the imaging area shows non-uniform composition by EDS. What went wrong, and how would you re-prep? Difficulty: medium.

**Exercise 22.7 (LO: identify hazard).**
A new graduate student is asked to mix perchloric acid with ethanol for a Cu electropolish. Why is this potentially dangerous, and what is the safe protocol? Difficulty: medium.

### Synthesis

**Exercise 22.8 (LO: integrate methods).**
A failure analyst has a packaged GaN power transistor that has shorted at its gate. Specify a prep workflow that combines FIB-SEM site-specific lift-out with TEM imaging at HRTEM resolution. Note where each technique adds value and what artifacts each introduces. Difficulty: hard.

### Challenge

**Exercise 22.9 (open-ended).**
Find a published HRTEM image with a methods section describing FIB lift-out. Identify the cleanup-pass parameters (voltage, angle, time). Comment on whether the imaged region appears to have residual amorphization at the surface and how this affects the resolution claim. Difficulty: open-ended.

---

## 11. Summary

You walked into this chapter with bulk inorganic specimens and the TEM thin-specimen requirement. You walk out with four major prep routes, the operator's discipline for choosing among them, and the artifacts to recognize. You can plan a multi-step prep workflow and predict its damage and time costs.

The one idea that matters most: every prep route has its own damage signature, and the operator's job is to choose damage that is tolerable for the imaging question. Mechanical work-hardening, electropolish pitting, ion-beam amorphization, gallium contamination — none can be eliminated, only managed.

The common mistake to watch for is skipping the cleanup pass on FIB lamellae. The 5-20 nm of amorphized surface from 30 keV gallium milling blocks HRTEM lattice imaging; a 1-2 keV cleanup pass at glancing angle removes most of it.

The Feynman test: explain to a labmate, without using the word "milling," why a bulk metal cannot go directly into a TEM column.

---

## 12. Connections Forward

Chapter 23 returns to artifact recognition with the prep-induced artifacts in this chapter as part of the comparative synthesis. Chapter 25 covers cross-technique applications including materials-science workflows that use FIB lift-out for TEM. Appendix B catalogs grids and supports relevant to inorganic TEM specimens.

The question this chapter raised but did not answer: how do you compare and integrate artifacts from prep, imaging, and detection into a coherent diagnostic framework? Chapter 23 provides the comparative synthesis.

---

**What would change my mind:** evidence that a single prep route could match all the others in damage and quality across different materials. The empirical record consistently shows that material-specific prep routes outperform general-purpose ones.

**Still puzzling:** the practical decision of when to switch from conventional mechanical+ion mill to FIB lift-out is mostly cost-driven. FIB is faster but instrument-expensive; conventional is slower but cheaper. The break-even depends on local lab economics rather than a clean pedagogical rule.

**Tags:** `inorganic-TEM-prep`, `dimpling`, `ion-milling`, `electropolishing`, `FIB-lift-out`

---

### Note to the professor

`[verify]` markers in this chapter:
- Specific electrolyte recipes for various materials.
- Ion-mill parameters (voltage, angle, time) — material-dependent.
- FIB cleanup-pass parameters.
- Damage-layer thickness ranges.
- FIB instrument cost ($1M+).

Voice anchoring: anchored. Steel-disc chapter opening (one scene only). Capability ending. Hazards callout for electropolishing chemistries. Scale shift in Section 7. Wonder grounded in numbers (5 mm bulk → 100 nm imaging area = 5 orders of magnitude reduction; 4-12 hour ion mill; FIB lamella site precision <100 nm). Length ~5500 words.
