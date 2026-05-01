# Chapter 8 — SEM Sample Preparation

## Title options

1. **Getting the Specimen Ready: Mounting, Coating, Drying, Polishing**
2. **The Half of SEM Work That Happens Before the Beam Turns On**
3. **Preparation Is the Microscopy: How Samples Reach the Chamber**

## TL;DR

The SEM image is at most as good as the sample preparation that produced it. This chapter covers preparation across particles, polymers, biological tissue, and metals, with the central principle that every prep step alters the specimen and the operator's job is to choose alterations that preserve what they want to see.

---

## 1. Chapter Opening

A research technician carries two stubs into the prep room. On one is a tiny chunk of fractured aluminum from a failed turbine blade — heavy, dense, conductive, requiring no preparation beyond mounting on the stub. On the other is a fresh sample of mouse cardiac tissue, a 3 mm cube of soft, hydrated, beam-sensitive material that, in its current state, will boil away in the SEM chamber within seconds. Both are headed for the same instrument the next morning. One needs about ten minutes of preparation. The other needs a chemical fixation rinse, three nights of dehydration through ethanol, a critical-point dryer run, and a sputter-coater session — call it three days, with several stages where one mistake destroys the specimen.

Same instrument. Same operator. Same 20 kV beam. The two specimens require completely different approaches because they are different in three properties that decide all sample preparation: water content, conductivity, and beam sensitivity. Chapters 4 through 7 taught you how to operate the SEM. This chapter teaches you how to put a specimen in front of it.

The principle that runs through everything below: every prep step changes the specimen. The question is never "did I avoid changing the specimen?" — that is impossible — but "did I change it in ways that preserve what I want to see?" A fixative crosslinks proteins; a critical-point dryer removes water without surface tension; a sputter coater deposits a 5-nm layer of platinum that you will then image. Each of these is a deliberate alteration with predictable consequences. Beginners try to "leave the specimen alone." Experienced microscopists choose their alterations carefully.

By the end of this chapter you can prepare specimens across the four major classes — particles, polymers, biological materials, and hard inorganic materials — and predict the artifacts each preparation method will introduce.

### Learning objectives

By the end of this chapter you can:

- **Mount** dry particles, suspension droplets, and bulk specimens on SEM stubs with appropriate conductive adhesive.
- **Choose** fixation, dehydration, and drying protocols for biological specimens.
- **Apply** sputter coating and carbon coating with appropriate thickness and material for the imaging goal.
- **Recognize** drying artifacts (shrinkage, cracking), microtomy artifacts (chatter, knife marks), and coating artifacts (decoration, charge holes).
- **Polish** metallic and ceramic specimens to a finish suitable for SEM and EDS analysis.
- **Match** preparation method to the research question and specimen type.

### Prerequisites

Chapter 5 (operating-condition trade-offs and how charging arises), Chapter 6 (interaction-volume physics for choosing coating thickness), Chapter 7 (detector choice — coating affects what each detector sees). Some chemistry: aldehyde fixation, alcohol dehydration series.

### Why this chapter matters

Preparation determines what your image actually shows. A fixation artifact looks like a real biological feature; a drying crack looks like genuine structure; an over-thick coating obscures the surface you wanted to see. Every artifact recognition skill in Chapter 23 starts here.

---

## 2. Particles, fibers, and powders: the simplest case

The question this section answers is: how do you put a small dry sample onto a stub for SEM imaging without losing it, charging it, or smearing it across the chamber?

### Mechanism — minimal prep, maximum care

A dry powder, fiber, or small particle is the easiest SEM preparation. The protocol takes ten minutes:

```
PROCEDURE — Dry particles on a stub

1. Label the stub with the specimen name on the bottom or side.
2. Apply a piece of double-sided carbon tape to the top of the stub.
3. Use a clean spatula to dust a small amount of the powder onto the tape.
4. Spread thinly and evenly. Heavy clumps charge and obscure each other.
5. Use a blower bulb or compressed air at low pressure to dislodge any
   loose particles that did not adhere.
6. Optionally, paint a thin line of carbon paint from the powder layer
   to the metal stub to ensure conductivity.
7. (For most non-conductive specimens) sputter-coat with 5–10 nm of
   metal. See Section 5.
8. Mount in the SEM and image.
```

The dominant failure modes are clumping (which produces charging halos because the inner particles cannot conduct charge to the stub) and loose particles that fall off in the chamber (which contaminate other specimens and the stage). Both are addressed in steps 4 and 5.

For **particles in suspension** — typical for nanoparticles in biology and materials — the protocol changes:

```
PROCEDURE — Particles in suspension

1. Label the stub.
2. Place a thin layer of carbon tape on the stub, OR a glass coverslip
   secured with carbon tape (the coverslip provides a smoother
   background for high-contrast nanoparticle imaging).
3. Place a single drop of well-dispersed suspension on the prepared
   surface. Volume: 5–20 μL depending on concentration.
4. If using a coverslip, paint a thin conductive line of carbon paint
   from the coverslip surface down to the metal stub for charge
   dissipation.
5. Air-dry, oven-dry (~50 °C), or desiccator-dry. Avoid high temperature
   for biological or polymer particles.
6. Sputter-coat if non-conductive (Section 5).
7. Mount and image.
```

A coverslip background gives a smoother surface than carbon tape, which helps when imaging small particles whose contrast must compete with substrate texture. Carbon paint provides the conductive bridge from the coverslip to the metal stub.

### Trade-off

The simplicity of dry-particle prep optimizes for **speed and minimal handling at the cost of dispersion control**. You cannot reliably control how particles are spaced, how aggregated they are, or whether they sit on edge versus flat side down. For statistical work — measuring particle size distribution, estimating density — drop-cast suspension on a glass coverslip is more controlled. For survey work — "are there any particles here?" — dry tape is fine.

### What Goes Wrong Here

- **Clump-driven charging.** A pile of insulating particles charges from the inside out. Recognition: bright halos around clusters, dark cores. Fix: spread thinner, increase coating thickness, lower kV.
- **Particles falling off in the chamber.** Loose particles dislodged by chamber venting end up on the polepiece, the stage, or other specimens. Fix: use the air blower or low-pressure plasma cleaning before loading.
- **Coverslip cracking under vacuum.** Thin glass cracks if the chamber is vented too quickly. Slow venting is the fix.
- **Surface contamination from the carbon tape.** Some carbon tapes outgas hydrocarbons; long imaging sessions show contamination near the tape edge. Fix: pre-bake the tape in a vacuum oven, or use cleaner adhesives like graphite-loaded conductive epoxy.

---

## 3. Polymers: low contrast, beam sensitivity, non-conductivity

The question this section answers is: how do you image polymers without watching them melt under the beam?

### Mechanism — three problems, three handles

Polymers are difficult for SEM for three reasons the source names directly:

1. **Low atomic number.** Most polymers are mostly C, H, O, sometimes N — all light elements. BSE Z-contrast is weak; SE topography is the dominant signal source.
2. **Beam sensitivity.** Polymer chains break under electron-beam-induced ionization. Mass loss, surface contamination, and feature distortion appear in seconds at high kV.
3. **Non-conductivity.** Most polymers are excellent insulators. Charging dominates uncoated imaging at moderate-to-high kV.

The handles for each:

**Low atomic number** — accept that BSE will not be your imaging mode. Image in SE. Use staining (osmium tetroxide, ruthenium tetroxide, or specific stains for specific polymers) when contrast between polymer phases is needed. Stained polymer can show clear domain structure in BSE that uncoated, unstained polymer cannot.

**Beam sensitivity** — lower kV (1–5 kV typical), lower current, faster scan with frame averaging. Cold stage if available. Avoid long dwell times.

**Non-conductivity** — sputter-coat with 5–10 nm of metal or carbon (Section 5), or image at very low kV (1–2 kV) where the SE crossover energy keeps the surface near zero charge (Chapter 5). Variable-pressure SEM (Chapter 10) provides a third option for polymers that cannot be coated.

### Polymer cutting techniques

**Microtomy.** A polymer specimen is sliced thin (typically 50 nm to a few μm) on an ultramicrotome with a diamond or glass knife (Chapter 20 details ultramicrotomy in the biological-prep context; the same instrument and technique apply to polymers). The result is a flat surface for SEM cross-section work. Challenges:

- **Distortion.** Soft polymer compresses under the knife; the cut face shows compression artifact.
- **Knife marks.** Surface irregularities on the diamond knife edge produce parallel scratches in the cut face.
- **Judder marks.** Vibration during cutting produces periodic ridges across the section.

These all degrade gracefully with technique: sharper knife, slower cut, cooler stage.

**Freeze fracture.** The polymer is cooled to liquid-nitrogen temperature (or in a cryostat), where it becomes brittle. A clean fracture exposes a surface that reveals internal structure without compression. The brittle fracture face is a different, more honest, picture of the polymer's bulk than a microtomed face. Often combined with metal-shadow contrast for surface enhancement.

### Trade-off

Polymer prep optimizes for **dimensional accuracy at the expense of native state**. Microtomy gives you flat sections at the cost of mechanical compression. Freeze fracture gives you bulk-state surfaces at the cost of fracture-path control. Staining gives you contrast at the cost of changing the chemistry. Variable-pressure SEM gives you uncoated imaging at the cost of resolution loss to gas scattering.

### What Goes Wrong Here

- **Beam damage growing during a session.** Polymer surfaces shift, soften, and develop bright contamination spots. Recognition: features at the same location look different in successive frames. Fix: lower kV, lower current, switch to a fresh field.
- **Microtomy chatter.** Periodic ridges across the section. Recognition: parallel lines at consistent spacing, often with consistent direction relative to the knife edge. Fix: slower cutting speed, sharper or cleaner knife, change knife angle.
- **Coating decoration.** Sputter-coated metal preferentially nucleates on certain surface chemistry, producing uneven texture that mimics specimen morphology. Recognition: texture follows polymer phase boundaries in known multi-phase polymers. Fix: thinner coating, different metal, or no coating with low-kV imaging.

---

## 4. Biological materials: fixation, dehydration, drying

The question this section answers is: how do you take a soft, wet, beam-sensitive piece of tissue and convert it into a vacuum-stable, conductive specimen that still shows the structure you cared about?

### Mechanism — preserve structure, remove water, restore conductivity

A typical biological SEM workflow has seven stages, drawn directly from the source:

```
PROCEDURE — Biological SEM specimen preparation

1. Acquisition of specimen — fresh, ideally < 1 hour from organism.
2. Trimming and concentration — section to manageable size; rinse buffer.
3. Fixation — chemical crosslinking (glutaraldehyde, formaldehyde) with
   buffer (cacodylate, phosphate). Time: 1–24 hours.
4. Post-fixation — osmium tetroxide (OsO4) for membrane preservation
   and electron contrast. Time: 1–2 hours.
5. Dehydration — graded ethanol or acetone series (30%, 50%, 70%, 90%,
   100%, 100%) over hours.
6. Drying — critical-point drying (CPD), HMDS, or freeze drying.
7. Mounting and coating — stub, conductive adhesive, sputter coat.
```

Each stage has a specific role and a specific failure mode.

**Fixation.** Glutaraldehyde (a five-carbon dialdehyde, two reactive aldehyde groups bridging proteins) crosslinks proteins by forming covalent bonds between adjacent amino-group sites. The crosslinks lock proteins in place, preventing the structural collapse that would otherwise occur when water is removed. Buffer choice matters: cacodylate buffer is common; phosphate works for many specimens. Different organisms have specific protocols (the source's Watson 1984 table catalogs them by specimen type). Fixation is the most critical step. Consult the literature for your specific specimen.

**Post-fixation with osmium tetroxide.** OsO₄ is a heavy-metal fixative that primarily stabilizes membrane lipids by reacting with double bonds in fatty acid chains. Osmium also adds significant atomic number (Z = 76) at membrane locations, creating natural BSE contrast in cross-section work. **Hazard: osmium tetroxide vapor is acutely toxic.** Use only in a fume hood with appropriate PPE; see Hazards section below and Appendix A.

**Dehydration.** Water cannot survive the SEM vacuum; it must come out. The standard approach is a graded ethanol series — 30%, 50%, 70%, 90%, 100% × 2 — where each step replaces water with ethanol incrementally. Direct immersion in pure ethanol would cause rapid dehydration shrinkage. Acetone is an alternative; methanol is occasionally used. All three slightly extract lipid-soluble material; ethanol extraction is least severe.

**Drying.** This is the artifact-prone step. Three options:

1. **Critical-point drying (CPD).** The specimen is held under pressure in liquid CO₂, brought to the supercritical point (31.1 °C, 73.8 bar) where liquid and gas have the same density and surface tension is zero. Above the critical point, the CO₂ is vented as gas without surface-tension forces ever pulling on the specimen. Result: minimal shape change. CPD is the gold standard for biological SEM. The procedure takes about an hour; equipment is hazardous (high pressure) but well-engineered for safe operation. Some shrinkage and lipid extraction still occur.
2. **Freeze drying (lyophilization).** Specimen is frozen rapidly (liquid nitrogen plunge or slush), then water sublimes from the solid phase under vacuum. No surface-tension forces because no liquid phase. Slower than CPD, can produce ice-crystal damage in larger specimens.
3. **HMDS drying.** Hexamethyldisilazane has very low surface tension and is volatile. The specimen is transferred from 100% ethanol to graded HMDS, then to pure HMDS, then air-dried in a fume hood. The HMDS evaporates quickly without significant surface tension. HMDS works well for many specimens, fails for some (particularly delicate cells), and is much faster and cheaper than CPD. Increasingly common in routine work.

The week-5 source describes all three. CPD remains the standard for "the big specimens" and HMDS for "fast, cheap, good enough."

**Conductive coating.** Section 5 below.

### Trade-off

Biological prep optimizes for **structural preservation at the cost of chemical and physical alteration**. Every step changes something. Fixation crosslinks proteins (locking in some structure, distorting others). Osmium adds heavy atoms (great for contrast; alters chemistry). Ethanol dehydration extracts some lipids. CPD eliminates surface tension (great) but specimens still shrink ~5–10%. Coating obscures very fine surface detail.

### Worked example: a published bacterial-imaging protocol

**Problem.** A microbiology lab wants SEM images of *E. coli* for size, shape, and surface structure measurement. Specify a complete prep protocol.

**Reasoning.**
1. **Acquisition.** Liquid culture in exponential growth. 1 mL aliquot.
2. **Concentration.** Centrifuge gently (~5,000 × g, 5 min) to pellet. Resuspend in fixation buffer.
3. **Fixation.** 2.5% glutaraldehyde in 0.1 M cacodylate buffer, 1 hour at room temperature.
4. **Wash.** Three rinses in cacodylate buffer.
5. **Post-fixation.** 1% OsO₄ in cacodylate, 1 hour. (In fume hood.)
6. **Dehydration.** 30%, 50%, 70%, 90%, 100%, 100% ethanol. 10 min each.
7. **Drying.** HMDS exchange (50% in ethanol, 100%, 100%). Air-dry on a glass coverslip in fume hood.
8. **Mounting.** Coverslip on aluminum stub with carbon paint.
9. **Coating.** 5 nm Pt-Pd by sputter.
10. **Imaging.** 5 kV, in-lens detector, working distance 5 mm.

[verify: this is a plausible, standard E. coli SEM protocol; specific concentrations and times vary by lab; consult primary literature for the specific organism.]

**General lesson.** A typical biological SEM prep takes 4–6 hours of hands-on time and yields one or two specimens per session. The ratio of prep time to imaging time is often 10:1 or higher.

### What Goes Wrong Here

- **Fixation artifacts.** Cells appear shrunken, deformed, or have membrane discontinuities. Causes: under-fixation, wrong buffer pH, fixative penetrated unevenly. Recognition: irregular cell shapes inconsistent with healthy morphology.
- **Dehydration shrinkage.** Cells visibly smaller than fluorescence-microscopy images of the same culture. Causes: too rapid dehydration progression or pure ethanol shock. Recognition: cell volumes ~20% smaller than expected.
- **Drying artifacts.** Cracking, collapsed cells, or "pancake" morphology. Cause: surface tension during drying. Fix: switch from air-drying to CPD or HMDS.
- **Stain precipitation.** Crystals or punctate accumulations of osmium or uranyl in the specimen. Recognition: bright BSE-dense spots that are not biological. Fix: better post-stain rinses; appropriate stain concentrations.

---

## 5. Conductive coating

The question this section answers is: how thick should the coating be, what material, and by what method?

### Mechanism — drain charge, generate SEs, cap the surface

A 5–30 nm metal coating does three things for a non-conducting specimen:

1. **Charge drainage.** A conductive layer connected to the stub provides a path for charge to flow to ground. The coating must be continuous; gaps allow charge to accumulate and the underlying specimen to charge through the gaps.
2. **SE generation.** Coated metal generates SE more strongly and consistently than the underlying specimen, giving brighter, cleaner SE images. The image you see is, in effect, the metal coating's surface; the metal replicates the specimen's geometry conformally.
3. **Heat dissipation.** The coating helps spread heat from beam-impact heating, reducing local damage.

### Coating methods

**Sputter coating.** A target metal (Au, Au-Pd, Pt, Cr) is bombarded with low-energy argon ions in a small chamber at ~10⁻¹ Pa. Sputtered metal atoms travel ballistically and a few percent end up on the specimen, deposited as a thin film. Components from the source: cathode (target), anode, argon gas, rotary vacuum pump, high-voltage supply, glass-jar chamber, stage with specimen.

The procedure:

```
PROCEDURE — Sputter coating

1. Mount the specimen on the stub.
2. Place stub in sputter coater.
3. Pump down to 10⁻¹ Pa or below.
4. Set sputter time per the desired thickness (typically 30 s to 3 min).
5. Initiate plasma; deposit at calibrated rate (~5 nm/min typical).
6. Vent and remove.
```

Typical materials and applications:
- **Gold (Au).** General-purpose; good SE generation. Grain size ~5 nm; for very-high-resolution work, replace with Au-Pd or Pt.
- **Gold-palladium (Au-Pd, ~60:40).** Smaller grain size than pure Au; suitable for higher-resolution SEM.
- **Platinum (Pt).** Smallest practical grain size in sputter; for sub-5 nm feature work.
- **Chromium (Cr).** Even finer grain; less common, requires more careful sputtering.

**Carbon evaporation.** Resistive heating of carbon rods or filaments under vacuum. The carbon vapor condenses on the specimen as a thin layer. Carbon coats are essential for EDS work because they do not interfere with the X-ray spectrum the way Au or Pt do.

**Common pitfalls** (per the week-5 source):
- **Thermal damage** during sputtering. Modern coaters minimize this with magnetron sputtering and low-power operation.
- **Surface contamination** from residual oils and water in the chamber. Drying the sample overnight in a drying oven before coating helps.
- **Surface etching** if water vapor or O₂ remains in the chamber; recognition is plasma-color change from lavender to blue during sputtering.
- **Backstreaming of pump oil** if pumping over long periods. Don't leave the coater running for hours; pump 15–20 min, sputter, vent.

### Coating thickness — how much is enough?

Too thin and the coating is discontinuous, so charging persists. Too thick and the coating obscures fine surface features. The right thickness depends on the imaging goal:

- **High-resolution surface morphology at low kV (1–5 kV):** 2–5 nm. As thin as possible without losing continuity.
- **General-purpose imaging at 5–20 kV:** 5–15 nm.
- **EDS work:** 5–10 nm of carbon (carbon is X-ray-transparent and won't add spurious peaks).
- **Heavily insulating specimens:** 15–30 nm.
- **High-voltage imaging (>20 kV):** 10–20 nm typical.

### Trade-off

Coating optimizes for **stable conductive imaging at the cost of obscuring fine surface detail**. The 5 nm of Pt that prevents charging on your insulating polymer also hides any feature smaller than 5 nm. A choice for every specimen.

### What Goes Wrong Here

- **Discontinuous coating.** Thin coats can island-grow rather than form continuous films. Recognition: charging despite "having coated." Fix: thicker coat or different metal.
- **Decoration.** Different specimen surface chemistry preferentially nucleates the coating, producing texture that mimics specimen morphology. Recognition: texture follows known phase boundaries. Fix: thinner coating with finer-grain metal (Cr, Pt), or carbon coat.
- **Coating contamination from old targets.** A sputter target that has run many hours can deposit oxidized or contaminated material. Recognition: speckly or non-uniform image at high resolution. Fix: clean or replace target.

---

## 6. Hard materials: metallography, polishing, ion milling

The question this section answers is: how do you produce a flat, scratch-free, contamination-free surface on a metal, ceramic, or other hard inorganic specimen?

### Mechanism — section, mount, grind, polish, etch

The metallographic prep sequence is well-established and largely instrument-driven:

```
PROCEDURE — Metallographic SEM preparation

1. Sectioning — saw cut at the region of interest. Water-cooled to
   prevent thermal damage. Fracture is sometimes preferred for brittle
   materials.
2. Mounting — embed in cold or hot resin. Cold mount with two-part
   epoxy is gentler on temperature-sensitive specimens. Hot compression
   (Bakelite, ~177 °C, 28 MPa) gives better edge retention.
3. Grinding — sequence of decreasing grit (60, 120, 240, 320, 400, 600).
   Wet to prevent thermal damage and to clear debris. Each grit
   removes the previous one's damage.
4. Polishing — diamond suspensions from 30 μm down to 1 μm or finer.
   Final polish at 1 μm or 0.05 μm colloidal silica.
5. Cleaning — ultrasonic clean to remove polishing debris.
6. (Optional) Etching — chemical attack to reveal microstructure.
   Etchants from ASM Handbook for the specific alloy.
7. Mounting on SEM stub — usually a final step; the polished surface is
   flat enough that mounting on conductive adhesive works.
```

The mounting medium is important to consider. The source notes two failure modes: (1) the medium itself is non-conductive and must be coated for SEM, and (2) the medium can smear during polishing and contaminate the surface, especially for EDS work where smear can produce spurious composition.

**Etching** for SEM is more restrained than for optical metallography. The source specifically advises avoiding heat tinting and tint etching (which form oxides on the surface) for SEM, where the surface chemistry should be preserved. Direct chemical etchants from the ASM Handbook produce clean topographic relief.

**Electropolishing** uses an electrochemical cell to selectively dissolve the high points on a surface, leaving a flat polish without mechanical damage. The specimen is the anode; an electrolyte (often perchloric acid, methanol-based, or other depending on the metal) provides the ionic path. Result: a very smooth surface with no mechanical damage. The catch: electrolytes can be hazardous (perchloric acid is explosive when mixed wrong; see Hazards), and the cell requires specific setup for each material.

**Vibratory polishing.** Horizontal vibration drives the specimen against a polishing pad with colloidal silica suspension. Slow but very gentle. Result is a flat, low-stress surface without dangerous electrolytes.

**Ion beam milling.** A broad argon ion beam strikes the specimen at a glancing angle (often 80°+ for final polishing). Removes mechanical-polishing damage and surface contamination from previous steps. Can also be used to expose a cross-section of bulk material via a mask (cross-section ion milling, useful for hard-to-mechanically-polish materials).

**Plasma cleaning.** Oxygen plasma chemically removes hydrocarbon contamination from the specimen surface. Particularly important for low-kV high-resolution work where any contamination dominates the SE signal.

### Trade-off

Hard-materials prep optimizes for **flat, clean surfaces at the expense of preparation time**. A serious metallographic prep can take a full day per specimen. The reward is a surface that produces clean BSE Z-contrast, clean EDS spectra, and high-quality SE images with no preparation-induced surface chemistry.

### Worked example: a polishing sequence for stainless steel for EDS

**Problem.** A graduate student needs a polished surface of stainless steel suitable for EDS analysis of trace elements at the 0.1 wt% level.

**Given.** Specimen: 1 cm × 1 cm × 5 mm thick stainless steel coupon.

**Reasoning.**
1. Section to fit the polishing puck (1 cm × 1 cm fits most metallographic mounts).
2. Cold-mount in two-part epoxy if heat-sensitive features matter; otherwise hot-mount in conductive Bakelite for edge retention.
3. Wet grind: 240, 320, 400, 600 grit silicon carbide papers. ~2 min each.
4. Polish with diamond suspension: 9 μm, 3 μm, 1 μm. ~5 min each.
5. Final colloidal silica polish (0.05 μm) for ~10 min.
6. Ultrasonic clean in ethanol, 5 min.
7. Plasma clean in O₂ for ~5 min before SEM/EDS analysis.
8. Mount on stub with conductive carbon tape; 5 nm carbon coat (carbon doesn't interfere with EDS).

**Sanity check.** The above is a standard metallographic protocol; a final colloidal silica polish typically gives surface roughness < 50 nm, adequate for EDS work at the trace level.

**General lesson.** Trace-element EDS analysis requires excellent surface preparation; a poorly polished surface contributes its own roughness-driven X-ray-absorption variation that swamps trace signals.

### What Goes Wrong Here

- **Smearing of the mount medium across the polished surface.** Recognition: dark "stripes" parallel to the polishing direction; EDS spectra show carbon and resin elements where the surface should be just metal. Fix: more polishing time at the final step; thorough cleaning.
- **Polishing artifacts at phase boundaries.** Soft phases polish faster than hard phases, creating local relief. Recognition: BSE bright-dark steps at phase boundaries that are geometric, not compositional. Fix: shorter polishing times, finer abrasive at the end.
- **Surface contamination from cleaning solvents.** Some solvents leave residues. Recognition: thin films visible at high magnification. Fix: ultrasonic clean in clean solvent, or plasma clean.

---

## 7. Synthesis: matching prep to specimen and question

A specimen has properties (water content, conductivity, beam sensitivity, hardness, magnetic state) and a question (surface morphology, composition, internal structure, phase distribution). Preparation is the function that maps from specimen + question to a stub-ready, vacuum-stable sample.

The decision tree:

- **Hard, dry, conductive, no internal structure of interest** → mount on carbon tape; image directly. (A fractured metal blade.)
- **Hard, dry, insulating, surface morphology of interest** → mount; sputter-coat 5–10 nm; image. (A ceramic, a dry mineral.)
- **Hard, internal structure of interest** → cross-section by saw or FIB; metallographic polish; coat (if insulating) or not (if conductive); image. (A semiconductor device.)
- **Soft, hydrated, biological** → fix, dehydrate, dry, mount, coat. Multi-day. (A cell, a tissue.)
- **Soft, beam-sensitive, polymer** → microtome or freeze-fracture; image at low kV with thin coat. (A polymer membrane.)
- **Particles** → spread on tape or drop-cast on coverslip; coat if insulating. (Nanoparticles, fibers.)

**The wonder.** Look at any well-prepared SEM image — a *Drosophila* eye magnified to 1000×, a surface of a fractured turbine blade with grain boundaries on display, a cross-section of an integrated circuit with metallization layers visible — and recognize that each of those images represents days of careful preparation. Days of fixing, dehydrating, drying, coating, polishing, etching. Each step a choice that traded some part of the specimen's nativeness for some part of the image's clarity. The image you see is the *outcome* of dozens of prep decisions, not a passive recording of what was there.

The corollary: the methods section of an SEM paper is the most important paragraph. "*Cells were fixed with 2.5% glutaraldehyde in cacodylate buffer (pH 7.4), post-fixed with 1% OsO₄, dehydrated through a graded ethanol series, critical-point-dried, and sputter-coated with 5 nm Au-Pd. Imaging at 5 kV with a Schottky FE-SEM, in-lens detector, WD = 5 mm.*" Every clause matters. Skipping the methods section and reading only the figures is reading the conclusion of an argument whose premises have been hidden from you.

---

## 8. Pre-lab Checklist (Lab 8 — sample preparation)

**By the end of this chapter, you should be able to:**

- Mount and coat a particulate sample for SEM imaging.
- Choose a fixation, dehydration, and drying protocol for a hypothetical biological specimen.
- Polish a metallographic specimen to EDS-suitable quality.
- Recognize the most common preparation-induced artifacts.

**Bring to lab:**

- This chapter, especially Sections 4 and 5.
- A specimen of your choice (a few options pre-prepared in the lab: dried bacterial culture, polymer film, polished alloy).
- Closed-toe shoes; nitrile gloves at the door.

**Expect on the floor:**

- A guided sputter-coating run on a real specimen.
- A side-by-side comparison of an uncoated vs. coated polymer in the SEM.
- Discussion of the prep history of a specimen the lab has prepared in advance, with the prep artifacts pointed out in the image.

### Hazards and Safe Practice

The hazards specific to sample preparation:

- **Glutaraldehyde** — toxic by inhalation, skin irritant, fixative. Use only in a fume hood with PPE. Disposal as hazardous waste.
- **Osmium tetroxide** — extremely toxic by inhalation; vapor stains corneas and lung tissue. Use only in a fume hood with face protection. Sealed vials, dispose as hazardous waste.
- **Heavy-metal stains** (uranyl acetate, lead citrate). Toxic; uranyl acetate is mildly radioactive. Gloves; designated work area; dispose appropriately.
- **Cryogens** (liquid nitrogen) — cryogen burn; asphyxiation in confined spaces. PPE; well-ventilated rooms.
- **Sputter coater** — high voltage, vacuum implosion of glass jar; small but real hazards.
- **Polishing solvents and electrolytes** — perchloric acid (electropolishing) is explosive when mixed wrong with organic solvents. Methanol-based electrolytes are flammable and toxic. Always follow the published procedure exactly.
- **Sectioning blades** — diamond and glass knives are sharp; saws are loud and produce flying debris. PPE.

For comprehensive treatment, see **Appendix A**.

---

## 9. Quick-Reference Table

| Specimen type | Mount | Fix | Dry | Coat | Notes |
|---|---|---|---|---|---|
| Dry powder | Carbon tape on stub | — | — | 5–10 nm Au or Pt | Spread thin |
| Suspension | Glass coverslip on stub | — | air or oven | 5–10 nm Au or Pt | Carbon paint bridge |
| Bulk metal, polished | Direct on stub | — | — | None or 5 nm C for EDS | Ultrasonic clean |
| Polymer (cross-section) | Stub via tape | — | — | 2–5 nm Cr or Pt | Microtome or freeze-fracture |
| Biological (cell, tissue) | Coverslip on stub | Glutaraldehyde + OsO₄ | CPD or HMDS | 5 nm Au-Pd | Multi-day prep |
| Polymer (whole) | Stub via tape | OsO₄ vapor optional | — | 2–5 nm | Low kV imaging |
| Polished cross-section (alloy) | Mounted in resin or epoxy | — | — | Thin C for EDS | Final 0.05 μm polish |

| Coating goal | Material | Thickness | Method |
|---|---|---|---|
| General SE imaging | Au or Au-Pd | 5–15 nm | Sputter |
| High-resolution low-kV SEM | Cr or Pt | 2–5 nm | Sputter |
| EDS analysis (avoid spurious peaks) | C | 5–10 nm | Carbon evap. |
| Heavy charging, robust | Au-Pd | 15–30 nm | Sputter |

---

## 10. Exercises

### Warm-up

**Exercise 8.1 (LO: choose mount).**
For each: how would you mount on an SEM stub? (a) 50 mg of dried bacterial spores; (b) 1 mL of nanoparticle suspension; (c) a 5 mm × 5 mm fragment of polished stainless steel. Difficulty: easy.

**Exercise 8.2 (LO: name fixative).**
Why is osmium tetroxide used after glutaraldehyde in biological prep? What does each fix? Difficulty: easy.

**Exercise 8.3 (LO: predict drying artifact).**
A bacterial cell air-dried from 100% ethanol on a coverslip looks pancake-flat in the SEM, while CPD-prepared bacteria from the same culture look round. Why? Difficulty: easy.

### Application

**Exercise 8.4 (LO: design protocol).**
Specify a complete prep protocol for SEM imaging of a freshwater diatom population for size and morphology measurement. Difficulty: medium.

**Exercise 8.5 (LO: choose coating).**
You are imaging a cross-section of a polymer-metal composite at 5 kV with EDS analysis. What coating do you choose, what thickness, and why? Difficulty: medium.

**Exercise 8.6 (LO: diagnose artifact).**
A microtomed polymer cross-section shows parallel ridges 200 nm apart oriented perpendicular to a known feature direction. What is the likely cause and what would you change? Difficulty: medium.

**Exercise 8.7 (LO: prep for EDS).**
A polished alloy surface gives EDS spectra showing unexpected carbon and silicon peaks even though the alloy contains neither. What preparation steps could be responsible? Difficulty: medium.

### Synthesis

**Exercise 8.8 (LO: integrate prep choices).**
A biomedical engineering lab needs SEM images of a tissue-scaffold interface (porous polymer scaffold seeded with cardiac fibroblasts) for surface morphology of cells, composition of the scaffold polymer, and 3D architecture. Specify a complete prep protocol from acquisition through imaging, naming each step's purpose and the artifact it might introduce. Justify the coating, kV, and detector choices in the final imaging step. Difficulty: hard.

### Challenge

**Exercise 8.9 (open-ended).**
Find a published SEM paper in your research field. Read the methods section carefully. Identify each prep step. For one of the artifacts you might predict from that protocol, look at the figures and try to spot evidence of that artifact in the published images. Comment on whether the authors discuss it. Difficulty: open-ended.

---

## 11. Summary

You walked into this chapter knowing that a specimen needs to be mounted on a stub. You walk out knowing that preparation is a multi-step alteration of the specimen — fixation, dehydration, drying, coating, polishing — and that every step is a choice with consequences. You can prepare specimens across the four major classes (particles, polymers, biological, hard inorganic). You can recognize the artifacts each preparation method introduces.

The one idea that matters most: every prep step changes the specimen. The best operators do not avoid changes; they choose changes that preserve what they want to see. The worst preparation is the unconsidered one that introduces artifacts the operator does not even recognize.

The common mistake to watch for: skimping on prep time. A 6-hour biological prep cannot be done in 30 minutes; the result is artifacts that will haunt every subsequent image.

The Feynman test: explain to a labmate, without using the word "fixation," why a fresh piece of tissue cannot go directly into an SEM chamber.

---

## 12. Connections Forward

Chapter 9 (EDS) takes the polished metallographic surface this chapter taught you to produce and uses it for elemental analysis. Chapter 10 introduces FIB-SEM for site-specific cross-sectioning beyond what mechanical polishing can achieve. Chapters 20 (biological TEM prep) and 22 (inorganic TEM prep) extend the prep concepts here to the much more demanding requirements of TEM. Appendix B catalogs grids, supports, and stains that are SEM-relevant only by analogy but which apply directly to TEM work.

The question this chapter raised but did not answer: how do you achieve an electron-transparent specimen for TEM? A polished SEM cross-section is opaque to the TEM beam. Chapter 22 shows how ion milling, FIB lift-out, and electropolishing get you to < 100 nm thickness.

---

**What would change my mind:** evidence that a single universal prep protocol works across specimen types without specimen-specific artifact patterns. The artifact specificity demonstrated in 80 years of biological and materials microscopy literature suggests this is unlikely.

**Still puzzling:** the long-running debate between CPD and HMDS for biological specimens has empirical evidence on both sides depending on specimen and application. The choice often depends more on lab tradition than on rigorous comparison.

**Tags:** `sample-preparation`, `fixation`, `coating`, `metallography`, `artifacts`

---

### Note to the professor

`[verify]` markers in this chapter:
- E. coli protocol concentrations and times in Section 4 worked example.
- Coating thickness recommendations for specific imaging goals.
- Critical-point CO₂ values (31.1 °C, 73.8 bar) — standard physical constants.
- Sputter rate "~5 nm/min typical" — instrument-dependent.

Voice anchoring: anchored. Two-specimens hook (turbine blade + cardiac tissue). Capability ending. Wonder grounded in numbers (days of prep, 5–10 nm shrinkage figures). Scale shift in Section 7 (the methods section as the most important paragraph).
