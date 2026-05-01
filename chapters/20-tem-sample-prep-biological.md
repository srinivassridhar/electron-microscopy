# Chapter 20 — TEM Sample Preparation for Biological Materials

## Title options

1. **From Cell to Section: Biological TEM Prep**
2. **Fixation, Dehydration, Embedding, Sectioning: The Bio-TEM Pipeline**
3. **The Five-Day Specimen: How a Cell Reaches the TEM**

## TL;DR

Biological TEM requires turning soft, hydrated, beam-sensitive cells into hard-resin-embedded thin sections that can survive vacuum and electron beam. The standard pipeline takes 4-5 days: chemical fixation, post-fixation, dehydration, embedding, ultramicrotomy, and staining. Every step alters the specimen; the operator's job is to choose alterations that preserve what they want to see.

---

## 1. Chapter Opening

A graduate student wraps a freshly-extracted 1-mm piece of mouse cardiac tissue in dialysis tubing and submerges it in a vial of cold 2.5% glutaraldehyde in cacodylate buffer at pH 7.4. The clock starts. Two hours of fixation in the cold room. Three rinses. One hour of post-fixation in 1% osmium tetroxide — the vapor catches the student's eye even with proper fume-hood discipline; protein structures lock into place; lipid membranes accept osmium atoms and become electron-dense. Three more rinses. The graded ethanol series begins: 30%, 50%, 70%, 90%, 100%, 100%, 100% — each step a few minutes to gently exchange water for solvent. Overnight in 50:50 ethanol-resin mix. A day in pure resin with rotation. Into a flat embedding mold. Sixty hours in a 60°C oven, where the resin polymerizes around the now-rigid tissue. The student returns five days later, takes the polymerized block to the ultramicrotome, trims the block face, and starts cutting 70-nm sections. Each section, lighter than gossamer, floats away from the diamond knife onto a water surface and is picked up onto a copper TEM grid. Stain with uranyl acetate, then lead citrate. Dry. The grid is ready.

The first TEM image at 50,000× shows mitochondria with crisp inner-membrane cristae, ribosomes as discrete dots on rough ER, and intercalated discs holding cardiac myocytes together. None of this would have been visible if any one step in those five days had been done sloppily.

This is biological TEM specimen preparation: a multi-day chemical pipeline that turns living tissue into a vacuum-stable, electron-transparent, contrast-enhanced specimen. By the end of this chapter you can plan and execute each step, recognize the artifacts that arise from common mistakes, and choose between conventional chemical fixation and high-pressure cryo-fixation when the question demands it.

### Learning objectives

By the end of this chapter you can:

- **Plan** a complete biological TEM prep protocol from acquisition through imaging.
- **Choose** appropriate fixative, buffer, and dehydration solvent for a given specimen.
- **Execute** ultramicrotomy: block trimming, knife alignment, thick-to-thin sectioning, section pickup.
- **Apply** positive and negative staining protocols.
- **Recognize** ultramicrotomy artifacts (scratches, chatter, crevasses, wrinkles).
- **Choose** between chemical fixation and high-pressure freezing for the research question.

### Prerequisites

Chapter 8 (SEM sample prep — much carries over). Chapter 12 (TEM thin-specimen requirement). Some basic biochemistry: aldehyde chemistry, lipids, proteins, buffers.

### Why this chapter matters

Biological TEM preparation is the longest single time investment in any TEM session — multiple days for a single specimen. Mistakes propagate; recognizing them in advance saves weeks of work. Almost every paper using biological TEM rests on this pipeline.

---

## 2. The conventional seven-step protocol

The question this section answers is: what does the standard biological TEM prep pipeline look like end to end?

### Mechanism — preserve, dehydrate, harden, slice, stain

Per the week-12 source, the conventional protocol has seven steps:

```
PROCEDURE — Conventional biological TEM prep (4-5 days)

1. Fixation in buffered aldehyde (1-24 hours)
2. Post-fixation in osmium tetroxide (1-2 hours)
3. Dehydration in graded ethanol or acetone (2-3 hours)
4. Embedding in resin (overnight + polymerization for 1-3 days)
5. Ultramicrotomy (sections at 60-80 nm)
6. Staining (uranyl acetate + lead citrate, 15-20 minutes)
7. Viewing in the TEM
```

Each step has a specific role and a specific failure mode. The chapter unpacks them in order.

### Step 1: Fixation

The aldehyde fixative — typically **glutaraldehyde** (a 5-carbon dialdehyde, two reactive aldehyde groups) — penetrates the tissue rapidly and crosslinks proteins. Aldehyde groups bind to amino groups on proteins, forming covalent bridges that lock the molecular machinery in place. Cells are considered "fixed" — biologically dead, structurally preserved.

Glutaraldehyde fixes mainly proteins and protein-associated macromolecules (lipoproteins, histoproteins). It does not preserve carbohydrates well.

**Buffer choice.** A buffered solution maintains pH and osmolarity during fixation. Common choices per the source: **phosphate buffer**, **cacodylate buffer**, and (increasingly) organic buffers (HEPES, MOPS) that are nontoxic and have less detrimental effect on fine structure. The buffer's three roles:

- **pH control.** Resists pH change as the fixative reacts; preserves cellular morphology.
- **Fixative vehicle.** Carries the fixative evenly through the tissue.
- **Osmolarity regulation.** Prevents shrinkage or swelling during fixation.

Standard glutaraldehyde concentrations for tissue: 2.0-2.5%, in 0.1 M cacodylate or phosphate buffer at pH 7.2-7.4 [verify].

### Step 2: Post-fixation in osmium tetroxide

After aldehyde fixation, the specimen is rinsed and post-fixed in osmium tetroxide (OsO₄, 1-2%) for 1-2 hours. Osmium does two important things:

1. **Stabilizes lipids.** OsO₄ reacts with double bonds in unsaturated fatty acids, locking lipid membranes in place. Aldehydes do not do this; without OsO₄, membranes can disorganize during dehydration.
2. **Adds electron contrast.** The reduced osmium is heavy ($Z = 76$), so membrane regions appear electron-dense in TEM. This is what makes the cristae and other lipid structures visible.

After the oxidative reaction, the cell is hardened — brittle, easily damaged by rough handling. Pipetting and centrifugation must be gentle.

**Hazard:** OsO₄ vapor is acutely toxic. Vapor exposure to corneas and lungs is severe. Use only in a fume hood with face protection. Sealed vials, dispose as hazardous waste. (See Hazards section below.)

### Step 3: Dehydration

Water cannot survive the TEM vacuum. The standard approach: graded ethanol series (or methanol or acetone), gradually replacing water with solvent.

```
PROCEDURE — Graded dehydration

1. 30% ethanol, 10 min
2. 50% ethanol, 10 min
3. 70% ethanol, 10 min  (specimens can be stored here briefly)
4. 90% ethanol, 10 min
5. 100% ethanol, 10 min × 3 changes
```

The slow exchange is the principle. Direct immersion in pure ethanol would cause rapid dehydration shrinkage; the gradient minimizes osmotic stress. All three solvents (ethanol, methanol, acetone) extract lipid-soluble material to some extent; ethanol is gentlest.

### Step 4: Embedding

After dehydration, the specimen is in pure ethanol. The next step replaces the ethanol with a resin that will polymerize to a hard but cuttable solid. This is **infiltration**:

```
PROCEDURE — Resin infiltration

1. 70% ethanol + 30% resin, 2 hours (rotating)
2. 50% ethanol + 50% resin, 2 hours
3. 30% ethanol + 70% resin, 2 hours
4. 100% resin, 2 hours × 3 changes (rotating)
5. Place in embedding mold or capsule.
6. Polymerize in oven at 60-70°C for 1-3 days.
```

Common resins: epoxy (Epon, Spurr's, Araldite) and acrylic (LR White, Lowicryl). Each has its trade-offs in cutting quality, hydration behavior, and immunoreactivity preservation. Standard biology uses Epon-class epoxy resins.

After polymerization, the specimen is enclosed in a hard resin block, ready for ultramicrotomy.

### Step 5: Ultramicrotomy

The microtome cuts thin sections (50-100 nm thick) for TEM imaging. The week-12 source describes the procedure step by step:

**Block trimming.** Use a single-edged razor under a stereomicroscope. Trim the block face to a trapezoidal shape exposing the specimen, with parallel top and bottom edges for clean ribbon production.

**Knife.** Glass knives are cheap and made fresh from plate glass; suitable for soft materials. Diamond knives are expensive ($1,000-5,000+) and last for many sessions; suitable for harder materials. Either knife sits in a "boat" or "trough" of water that catches the floating sections.

**Alignment.** The block face must be parallel to the knife edge in all directions. Use the reflection of the knife on the block face to check alignment. Don't touch the block to the knife.

**Thick sectioning.** First cut thick sections (1-2 μm) and dry them onto a glass slide for light-microscope examination. Confirms that the correct specimen area is at the cutting face.

**Thin sectioning.** Cut sections at 60-80 nm using mechanically advanced specimen arm. Thin sections form ribbons on the water surface, color-coded by thickness (gray = ~40 nm, silver = ~50-70 nm, gold = ~70-90 nm, purple = ~100+ nm) [verify color coding precisely].

**Section collection.** Pick up sections from the water surface with a clean TEM grid (typically 200-400 mesh copper). The sections adhere to the grid; dry in a clean environment.

### Step 6: Staining

After sectioning, sections are typically too thin for sufficient inherent contrast. Heavy-metal stains (per the source: uranium $Z=92$, lead $Z=82$, osmium $Z=76$) bind to specific cellular components and increase electron density.

**Positive staining:** the most common. Sections on grids are floated on a drop of stain solution.

```
PROCEDURE — Positive staining

1. Place grid on a drop of 2% uranyl acetate (filtered, in water) for
   15 minutes. Protect from light (uranyl is photosensitive).
2. Wash in distilled water (multiple changes).
3. Place grid on a drop of 0.04% lead citrate (in CO₂-free water) for
   4-5 minutes. Use NaOH pellets in the staining chamber to absorb CO₂.
4. Wash in distilled water.
5. Air-dry on filter paper.
```

The two-step uranyl-then-lead protocol is widely used. Uranyl acts as a "mordant" — its presence enhances the lead staining at sites where the uranyl bound first. The combination gives strong, balanced contrast across membranes, ribosomes, nucleic acids, and protein-rich regions.

**Negative staining** (for isolated particles like viruses, bacteria, macromolecular complexes): the specimen is surrounded by an electron-dense agent (uranyl acetate at 1-2%). The particle excludes the stain; the stain forms a dark "negative" surround. The result: bright particles on a dark background.

**Hazard:** Uranyl acetate is mildly radioactive and toxic. Use gloves; work in a designated area; dispose as radioactive waste. Lead citrate is toxic. Glutaraldehyde is a sensitizer and known irritant. (See Hazards section below.)

### Step 7: Viewing

The grid is loaded into the TEM holder (Chapter 13), inserted through the airlock, and imaged. The five-day pipeline produces approximately one specimen ready for imaging.

### Trade-off

The conventional protocol optimizes for **structural preservation at the cost of time and chemical alteration**. Multi-day protocols give clean, contrast-rich, vacuum-stable sections. The cost: every chemical step alters the specimen. Cellular processes are halted at the moment of fixation; chemical states may be locked in non-native configurations. The trade is universal in biological microscopy.

### What Goes Wrong Here

The week-12 source enumerates the principal artifacts:

- **Fixation artifacts.** Cells appear shrunken, deformed, or have membrane discontinuities. Cause: under-fixation, wrong buffer pH, fixative penetrated unevenly. Recognition: irregular cell shapes inconsistent with healthy morphology. Mitigation: optimize fixative concentration and buffer for the specimen type.
- **Dehydration shrinkage.** Cells visibly smaller than fluorescence-microscopy images. Cause: too rapid dehydration progression. Mitigation: longer steps in graded series.
- **Sectioning compression and chatter.** Compression: sections shorter in the cutting direction than expected. Chatter: parallel ridges across the section from vibration. Mitigation: sharper knife, slower cutting, vibration isolation.
- **Stain precipitation.** Heavy-metal "snow" or punctate accumulations. Cause: contaminated stain solutions, exposure of uranyl acetate to light. Mitigation: filter stains, work in dark.
- **Knife marks.** Parallel scratches in the section perpendicular to the knife edge. Cause: defective or dirty knife. Mitigation: clean, sharp knife.

---

## 3. High-pressure freezing and freeze substitution

The question this section answers is: when is conventional chemical fixation inadequate, and what is the alternative?

### Mechanism — vitrification at high pressure plus solvent substitution

Conventional fixation introduces artifacts: slow diffusion of fixatives (especially in dense tissues or thick samples), selective reactions with cellular components, and osmolarity differences between fixative and specimen. Proteins can cluster from crosslinking; membranes can become "wobbly"; antigenicity (the molecule's ability to react with antibodies) can be lost.

**High-pressure freezing (HPF)** addresses these problems by replacing chemical fixation with physical immobilization. The specimen is rapidly frozen under very high pressure (>2,000 bar [verify]). At these pressures, water vitrifies rather than crystallizing — solidifies into glassy amorphous ice instead of forming sharp crystalline ice that would shatter cell components. The result: instant, simultaneous immobilization of all cell components without ice-crystal formation.

The catch: vitrification is effective only to a depth of ~200 μm [verify]. Tissue must be very small (a few microliters of cell suspension or a thin tissue piece) for HPF to vitrify throughout.

After HPF, the vitreous water is replaced with a solvent containing fixatives — **freeze substitution (FS)**. This is done at low temperature (~-90°C [verify]) over hours or days, slowly bringing the specimen to room temperature with minimal structural disruption. The result: a chemically fixed specimen that started its preservation as a vitrified solid rather than a dehydrating liquid.

### When HPF/FS wins

- **Specimens with active cellular dynamics** — fast processes that conventional fixation halts unevenly.
- **Tissues with tight intercellular junctions** that conventional fixative cannot penetrate quickly.
- **Specimens for immunolabeling** — antigenicity better preserved.
- **Specimens for cryo-EM tomography** — the same vitrified specimen can be imaged directly without going through resin (see Chapter 21).

### Trade-off

HPF/FS optimizes for **structural fidelity at the cost of equipment, time, and specimen-size constraint**. The high-pressure freezer alone costs $50,000+ [verify]; FS protocols take days. The maximum effective vitrification depth limits specimen size. Conventional chemical fixation works on larger tissues with cheaper equipment.

### What Goes Wrong Here

- **Crystalline ice formation.** Vitrification failed. Recognition: ice crystals visible in the TEM image as electron-lucent regions with sharp edges. Mitigation: faster freezing, smaller specimen volume.
- **Specimen compression at the freezing chamber wall.** Mechanical artifact from the high-pressure compression. Mitigation: appropriate carrier choice.
- **Failure to substitute throughout.** Solvent does not reach the interior. Mitigation: longer FS protocols.

---

## 4. Synthesis: protocols for the research question

The choice of preparation method depends on the question:

| Goal | Method |
|---|---|
| Survey of cell ultrastructure | conventional chemical fixation + Epon |
| Fast cellular dynamics, immunolabeling | HPF + FS |
| Single-particle structural biology | negative staining (cryo-EM if higher resolution) |
| 3D ultrastructure of small tissue piece | conventional + tomography (Chapter 19) |
| Native hydrated state | cryo-EM (Chapter 21) |

The conventional protocol is the workhorse — most textbook-style ultrastructural images of cells use it. HPF/FS is reserved for the specific cases where it wins. Cryo-EM (Chapter 21) extends both into the cryogenic regime.

### Putting it all together (worked synthesis)

A nanomedicine PI brings cardiac myocytes that have been pretreated with a drug intended to alter mitochondrial cristae structure. Goals:
- (a) Document baseline mitochondrial structure (control cells).
- (b) Document drug-treated mitochondrial structure.
- (c) Compare cristae density and morphology quantitatively.

Protocol:
- Both control and drug-treated cells fixed at the same time point (same day, same protocol).
- Conventional protocol: glutaraldehyde + cacodylate, OsO₄, ethanol dehydration, Epon embedding, ultramicrotomy at 70 nm, uranyl + lead staining.
- Acquire TEM images at 50,000× of multiple cells per condition.
- Quantitative analysis: cristae density (cristae per μm² of mitochondrial section) compared between groups.

Result: a defensible, statistically supported comparison of cellular ultrastructure with and without drug treatment.

### Hazards and Safe Practice

The hazards specific to biological TEM prep:

- **Glutaraldehyde** — toxic by inhalation, skin sensitizer, fixative. Use only in a fume hood with PPE. Disposal as hazardous waste.
- **Osmium tetroxide** — extremely toxic by inhalation; vapor stains corneas and lung tissue. Use only in a fume hood with face protection. Sealed vials. Disposal as hazardous waste.
- **Heavy-metal stains** — uranyl acetate is mildly radioactive (uranium-238 + small fraction of natural daughter products) and toxic; lead citrate is toxic. Gloves; designated work area; dispose appropriately. Uranyl acetate is photosensitive; protect from UV.
- **Resin chemicals** — many epoxy and acrylic resins are skin sensitizers or known carcinogens before polymerization. Gloves and ventilation while handling unmixed resins.
- **Diamond and glass knives** — sharp; injuries during handling are common. Always use the knife block when storing or transporting.
- **Liquid nitrogen** for HPF and cryo-handling — cryogen burns; asphyxiation risk in confined spaces.
- **High-pressure freezer equipment** — confined high-pressure release at -190°C; specific safety procedures required by manufacturer.

For comprehensive treatment, see **Appendix A**.

---

## 5. Pre-lab Checklist (Lab 20 — biological TEM prep)

**By the end of this chapter, you should be able to:**

- Plan a complete biological TEM prep protocol with timing and chemicals.
- Execute one stage of the prep pipeline (e.g., dehydration) under supervision.
- Identify ultramicrotomy artifacts in a sample image.

**Bring to lab:**

- This chapter, especially Sections 2 and 3.
- Closed-toe shoes, lab coat, nitrile gloves; the lab handles cytotoxic and (for OsO4 work) acutely toxic materials.

**Expect on the floor:**

- A guided fixation step on a tissue specimen (in the fume hood).
- A demonstration of ultramicrotomy on a previously-prepared block.
- A first attempt at section pickup on a TEM grid.
- A discussion of the ethics and safety of cytotoxic chemicals.

---

## 6. Quick-Reference Table

| Step | Reagent | Concentration | Time | Notes |
|---|---|---|---|---|
| Fixation | glutaraldehyde | 2.0-2.5% | 1-24 h | in cacodylate or phosphate buffer |
| Buffer | cacodylate | 0.1 M, pH 7.2-7.4 | — | most common |
| Post-fixation | OsO₄ | 1-2% | 1-2 h | hazardous; fume hood only |
| Dehydration | ethanol | 30→100% graded | 10 min/step | acetone alternative |
| Resin | Epon (epoxy) | various ratios with solvent | 2 h/step + cure | polymerize 60-70°C |
| Cure | — | — | 1-3 days at 60-70°C | until hard |
| Sectioning | diamond/glass knife | — | — | 60-80 nm sections |
| Stain 1 | uranyl acetate | 2% | 15 min | photosensitive |
| Stain 2 | lead citrate | 0.04% | 4-5 min | CO₂-free |

| Section thickness | Color | Comments |
|---|---|---|
| < 50 nm | gray | thin enough for HRTEM |
| 50-70 nm | silver | standard for routine TEM |
| 70-90 nm | gold | thicker; may show contrast better but lose resolution |
| > 100 nm | purple | thick for general bright-field at low magnification |

---

## 7. Exercises

### Warm-up

**Exercise 20.1 (LO: order steps).**
Put the following in correct order: fixation, dehydration, embedding, post-fixation, sectioning, staining. Difficulty: easy.

**Exercise 20.2 (LO: identify reagent).**
Why is osmium tetroxide used after glutaraldehyde rather than at the same time? Difficulty: easy.

**Exercise 20.3 (LO: predict color).**
A microtome operator cuts sections that look "purple" in the boat. What thickness range is this, and what is the implication for TEM imaging? Difficulty: easy.

### Application

**Exercise 20.4 (LO: design protocol).**
Specify a complete prep protocol for SEM imaging of mouse cardiac myocyte mitochondria. Include all reagents, times, and a section-collection strategy. Difficulty: medium.

**Exercise 20.5 (LO: identify artifact).**
A TEM image of a stained tissue section shows parallel ridges crossing all features. Cause? How to mitigate? Difficulty: medium.

**Exercise 20.6 (LO: choose between protocols).**
A researcher wants to image dynamic cellular processes that happen on the millisecond timescale. Conventional chemical fixation or HPF? Why? Difficulty: medium.

**Exercise 20.7 (LO: identify hazard).**
A graduate student is asked to "rinse the OsO4 vials in the lab sink." Why is this a problem and what is the correct disposal? Difficulty: medium.

### Synthesis

**Exercise 20.8 (LO: plan multi-day session).**
A PhD student needs to compare wild-type and knockout mouse heart tissue at the ultrastructural level. Both samples available simultaneously. Plan a complete prep workflow including timeline, reagent inventory, equipment needs, and quality-control checkpoints. Difficulty: hard.

### Challenge

**Exercise 20.9 (open-ended).**
Find a published paper that uses biological TEM. Reconstruct the prep protocol from the methods section. Identify which steps the authors specified and which they left out. List one missing piece of information and explain how it might affect interpretation of the figures. Difficulty: open-ended.

---

## 8. Summary

You walked into this chapter knowing biological TEM requires sample prep. You walk out with the seven-step conventional protocol, the alternatives (HPF + FS) for specific questions, the hazards and safety practices, and the artifacts to recognize. You can plan a multi-day biological prep session and execute key steps under supervision.

The one idea that matters most: every prep step changes the specimen, and the operator's discipline is to choose changes that preserve what matters for the question. The skilled biological TEM microscopist is the one who has internalized which artifacts are acceptable and which are not for each kind of investigation.

The common mistake to watch for is rushing dehydration. The graded series exists for a reason; jumping from 70% ethanol to 100% causes shrinkage that propagates through every later step.

The Feynman test: explain to a labmate, without using the words "fixation" or "dehydration," why a fresh piece of tissue cannot go directly into a TEM column.

---

## 9. Connections Forward

Chapter 21 (cryo-EM) extends biological TEM into the cryogenic regime, replacing chemical fixation with vitrification and adding low-dose imaging (Chapter 19). Chapter 22 covers TEM prep for inorganic specimens — different physical-chemistry but similar conceptual structure. Chapter 23 returns to artifacts comparatively across techniques.

The question this chapter raised but did not answer: how do you image specimens in their hydrated, native state without resin embedding? Chapter 21 covers cryo-EM.

---

**What would change my mind:** evidence that conventional chemical fixation can match HPF/FS for fast cellular dynamics. The empirical record consistently shows HPF/FS preserves rapid processes that aldehyde fixation halts non-uniformly.

**Still puzzling:** the choice between Epon, Spurr's, LR White, and Lowicryl resins is largely tradition-driven in many labs. Systematic comparisons of cutting quality and immunoreactivity preservation exist but are not always consulted.

**Tags:** `biological-TEM-prep`, `fixation`, `embedding`, `ultramicrotomy`, `staining`

---

### Note to the professor

`[verify]` markers in this chapter:
- Buffer pH range 7.2-7.4 — standard but specific values may vary by lab.
- HPF pressure ">2000 bar" — source-stated; current high-pressure systems achieve higher.
- Vitrification depth ~200 μm — material-dependent.
- Specific section-color-vs-thickness coding — varies by resin and operator.
- HPF equipment cost (~$50K+) — order-of-magnitude only.
- Standard glutaraldehyde concentrations 2.0-2.5%.
- Lead citrate concentration 0.04% — varies.

Voice anchoring: anchored. Cardiac-tissue chapter opening (one scene only). Capability ending. Hazards callout per outline.md authoring rules. Wonder grounded in numbers (5-day pipeline; 70-nm sections; 2,000-bar HPF pressures; protein crosslinking timescales). Length ~5300 words.
