# Chapter 9 — Energy Dispersive X-ray Spectroscopy (EDS)

## Title options

1. **Reading the Atoms: How an SEM Identifies Elements**
2. **Characteristic X-rays and What They Tell You**
3. **The Spectrometer Inside the SEM: Composition, One Photon at a Time**

## TL;DR

When the electron beam ionizes an inner-shell electron, the atom relaxes by emitting an X-ray photon at an energy fingerprint of the element; an EDS detector measures those photons and builds a histogram in energy that names the elements present. This chapter is the physics of characteristic X-rays, the operation of the EDS detector, and the artifacts that haunt the spectrum.

---

## 1. Chapter Opening

A geologist returns from a hike with a pebble that catches the light in three colors — green-black, yellow-tan, rust-red. The pebble might be anything: a copper-rich mineral, an iron oxide weathering crust, an unusual silicate. The optical microscope cannot tell. The XRD pattern would help but requires preparing a powder. The fastest answer is in the next room, where the SEM with EDS sits.

The geologist mounts a fresh-broken face on a stub, sputter-coats with carbon (carbon doesn't show up in the X-ray spectrum), pumps down, sets the kV to 25, parks the beam on the green-black region for 30 seconds. The spectrum on the screen builds peak by peak — Cu at 8.05 keV, S at 2.31 keV, Fe at 6.40 keV. The green-black phase is chalcopyrite, copper iron sulfide. Move the beam to the yellow-tan region: Si dominates, Al second, K third — likely a clay mineral. Move to the rust-red: Fe and O, with traces of S — iron oxide weathering crust, possibly hematite. Three minutes, three phases identified, no powder grinding, no chemical attack. The same sample under the same beam, photons read from the interaction volume, elements named by photon energy.

That is what EDS does. It identifies elements with a precision set by the energies of the inner-shell transitions of every atom on the periodic table. Each element's characteristic X-rays sit at energies as distinct as fingerprints. If you can read the energies, you can name the elements. The detector reads the energies; the analysis software reads the names. The geologist gets a verdict.

By the end of this chapter you can run an EDS analysis from setup through quantification, recognize the spectrum's three principal artifacts and decide when each matters, and choose acquisition parameters that match the question being asked.

### Learning objectives

By the end of this chapter you can:

- **Explain** how characteristic X-rays are produced from inner-shell ionization and vacancy filling.
- **Predict** the K, L, and M lines of an element using the periodic table and a transition energy table.
- **Choose** beam energy, beam current, dead time, and counting time for a given EDS analysis goal.
- **Recognize** principal EDS artifacts (peak broadening, escape peaks, sum/coincidence peaks, Si internal fluorescence, peak overlaps).
- **Calculate** approximate detection limit and spatial resolution.
- **Match** EDS to the right question (qualitative ID, semi-quantitative analysis, mapping, line scan).

### Prerequisites

Chapter 6 (interaction volume, where X-rays come from). Chapter 7 (detector geometry). Some atomic physics: shells, subshells, energy levels.

### Why this chapter matters

EDS is the most-used analytical technique on an SEM. Almost every materials-science and many biological/medical SEM sessions end with at least one spectrum collected. Understanding the spectrum — what it can tell you, what artifacts to watch for, what counts as good data — is essential to publishable analytical work.

---

## 2. Where characteristic X-rays come from

The question this section answers is: when an electron beam knocks an inner-shell electron out of an atom, what photon comes out, and why is its energy specific to the element?

### Mechanism — ionize, relax, photon

Bound electrons in an atom occupy shells with sharply defined energies — the K shell (1s, two electrons), the L shell (2s, 2p — three subshells, eight electrons total), the M shell (3s, 3p, 3d — five subshells, eighteen electrons), and so on. Each shell sits at a specific energy below the vacuum level, set by Coulomb attraction to the nucleus minus screening from the other electrons. The energies are sharply defined because the quantum states are eigenstates of the atom's Hamiltonian.

A beam electron with enough energy can ionize an inner-shell electron — knock it out into the vacuum, leaving the atom in an excited state with a vacancy. The minimum beam energy needed to do this for a specific shell is the **critical ionization energy** $E_c$, also called the *excitation energy* or *binding energy* of the shell. For copper:

$$
E_{c,K} \approx 8.98 \text{ keV}, \quad E_{c,L_{III}} \approx 0.93 \text{ keV}.
$$

The K-shell needs much more energy to ionize because K-shell electrons are deeply bound. To ionize a K-shell electron in copper, the beam electron must arrive with at least 8.98 keV of kinetic energy. Lower beam energy and the K-shell stays full.

Once a vacancy exists, the atom relaxes within femtoseconds. An outer-shell electron drops into the vacant inner shell; the atom releases the energy difference. Two competing processes:

1. **Characteristic X-ray emission.** The energy difference is emitted as a single photon at exactly $E_{\text{shell, vacancy}} - E_{\text{shell, source}}$. For a Cu K-shell vacancy filled by an L-shell electron, the photon has energy $\approx 8.98 - 0.93 = 8.05$ keV — a Cu Kα line. The energy is a fingerprint of the element and the transition.
2. **Auger electron emission.** Instead of emitting a photon, the atom ejects another outer-shell electron with kinetic energy equal to the same energy difference (minus the binding energy of the ejected electron). This is the Auger process, named for Pierre Auger; it is a competing channel for de-excitation.

The fraction of vacancies that produce X-rays rather than Auger electrons is the **fluorescence yield** $\omega$. For the K-shell:

$$
\omega_K = \frac{\#K \text{ photons produced}}{\#K \text{-shell ionizations}}
$$

$\omega_K$ depends strongly on atomic number. For carbon (Z=6), $\omega_K \approx 0.005$ — half a percent of K-shell ionizations produce X-rays; the rest produce Auger electrons. For germanium (Z=32), $\omega_K \approx 0.5$. For high-Z elements like tungsten (Z=74), $\omega_K$ approaches unity.

This is why EDS struggles with light elements. A 0.5% fluorescence yield means that to detect carbon in a specimen, you need to count enough events to overcome both the low yield and the spectrum background; light-element detection is always slow. For heavy elements, almost every ionization produces a photon, and detection is fast.

### X-ray families

Every element produces a family of characteristic X-rays, depending on which subshell the filling electron came from and which subshell had the vacancy. Selection rules (the dipole approximation, with allowed transitions $\Delta\ell = \pm 1$, $\Delta j = 0, \pm 1$) say only certain transitions actually emit X-rays.

For copper, the K-shell vacancy can be filled by:
- $L_{III}$ → K (2p₃/₂ → 1s): the **Cu Kα₁** line at 8.048 keV
- $L_{II}$ → K (2p₁/₂ → 1s): the **Cu Kα₂** line at 8.028 keV (these two together are the "Kα doublet," typically unresolved by EDS)
- $M_{III}$ → K: the **Cu Kβ₁** line at 8.905 keV
- $M_{IV,V}$ → K: the **Cu Kβ₅** line at 8.977 keV
- $N_{II,III}$ → K: the **Cu Kβ₂** line at 8.976 keV

Different transitions have different probabilities — the **weights of lines**. Generally, the larger the energy gap, the less probable the transition. Kβ lines are less intense than Kα lines.

For each element you analyze, the spectrum shows a characteristic K family (in light/medium-Z elements), an L family (in medium/heavy-Z elements), and sometimes M (heavy). The EDS detector resolves the families but typically not the individual subshell lines within them.

### Overvoltage — the rule of two

For efficient X-ray generation, the beam energy must comfortably exceed the critical ionization energy. The ratio is the **overvoltage**:

$$
U_0 = \frac{E_0}{E_c}.
$$

Practical EDS work needs $U_0 \geq 2$. At overvoltage just above 1, ionization cross-section is very low and X-ray yield is poor. At $U_0 = 2$, ionization is efficient. At $U_0 = 5$ or higher, ionization saturates and adding more kV gains nothing for that line — but does enlarge the interaction volume and worsens spatial resolution.

For example, to analyze copper at the K-line ($E_c = 8.98$ keV), beam energy should be at least 18 keV. To analyze gold at the L-line ($E_c \approx 11.92$ keV), at least 24 keV. To analyze gold at the M-line ($E_c \approx 2.20$ keV), 5 keV suffices for the line itself but at 5 keV the L-line and K-line don't appear.

### Trade-off

Beam energy choice for EDS optimizes for **adequate overvoltage on the heaviest line of interest at the cost of spatial resolution from a larger interaction volume**. Higher kV → bigger interaction volume → larger sampled region (Chapter 6 Kanaya–Okayama scaling). The standard compromise: pick kV at 1.5–2.5× the highest $E_c$ in your sample.

### Worked example: choosing kV for an Al-Cu analysis

**Problem.** A specimen contains aluminum (Al Kα at 1.49 keV, $E_{c,K} = 1.56$ keV) and copper (Cu Kα at 8.05 keV, $E_{c,K} = 8.98$ keV). Choose beam energy.

**Reasoning.** The overvoltage rule says $U_0 \geq 2$ for both elements:

- For Al: $E_0 \geq 2 \times 1.56 = 3.1$ keV.
- For Cu: $E_0 \geq 2 \times 8.98 = 18.0$ keV.

Cu is the binding constraint. Choose $E_0 = 20$ keV. At 20 keV: $U_0$ for Al is 12.8 (over-saturated, not a problem), $U_0$ for Cu is 2.2 (efficient).

**Sanity check.** Standard practice for analyzing alloys with both light and medium-heavy elements is 15–25 kV. Match.

**General lesson.** Pick kV to cover the heaviest line in your sample. The light-element overvoltage is rarely the constraint.

### What Goes Wrong Here

- **Beam energy below the heaviest element's $E_c$.** That element simply does not appear in the spectrum, even though it is in the sample. Diagnostic: if you expected an element and don't see it, check if the beam energy is high enough.
- **Beam energy too high for the question.** The interaction volume balloons, spatial resolution is lost. For analyzing thin films or buried interfaces, lower kV is better even if you sacrifice some sensitivity to heavier lines.
- **Forgotten overvoltage in mixed analyses.** A 5 kV analysis on a steel-aluminum interface will show Al cleanly but miss the iron entirely. Match kV to the question.

---

## 3. The detector and the spectrum

The question this section answers is: how does the detector convert an X-ray photon into a count in an energy bin, and what determines the spectrum's shape?

### Mechanism — solid-state detection in silicon

The EDS detector is a thin slab of silicon — historically lithium-drifted Si(Li), now usually a **silicon drift detector (SDD)** in modern instruments — held at low temperature (down to liquid-nitrogen temperatures, −196 °C, for Si(Li); thermoelectrically cooled to −20 °C or so for SDD). The cooling reduces thermal noise that would otherwise swamp the small charge signals from individual photons.

When an X-ray photon enters the silicon, it deposits its energy through one or several inelastic interactions, producing electron-hole pairs at a rate of about 3.6 eV per pair. A 5 keV X-ray creates roughly 1,400 e-h pairs; a 25 keV X-ray creates about 7,000.

Electronics collect the charge from the resulting photoelectric absorption event, amplify it, and digitize the total. Each photon produces one "count" in an energy bin proportional to its measured charge. Over many photons, the histogram builds up — the **EDS spectrum**.

The detector is, from the operator's view, a black box that takes in photons and produces a histogram of "this many counts at this energy." The black-box description matches the source's framing: input X-ray photon, output energy bin assignment, accumulated over time.

### Spectrum shape

Two principal contributors:

1. **Characteristic peaks** at element-specific energies. Sharp in principle (intrinsic linewidth ~2–10 eV), broadened by detector physics to 70–150 eV FWHM (full width at half maximum). The natural linewidth comes from the lifetime of the inner-shell vacancy; the broadening comes from statistical fluctuations in the number of e-h pairs created per photon. A 5.9 keV photon (Mn Kα) on average produces about 1,650 e-h pairs, but with statistical scatter of about ±30. That scatter translates to an energy uncertainty of ~110 eV — the peak's width.

2. **Continuum (bremsstrahlung) background** that varies smoothly from zero up to the beam energy. *Bremsstrahlung*, German for "braking radiation," named for what causes it: beam electrons decelerating in the Coulomb field of nuclei emit photons with whatever energy they happen to lose in that deceleration. Because deceleration is random, the energy spectrum is continuous from zero to $E_0$.

The spectrum the operator reads is characteristic peaks superimposed on a sloping continuum. Peak identification means subtracting the continuum to find the peak above background.

### Energy resolution and what it costs

EDS detector resolution at the Mn Kα line (5.9 keV) is conventionally ~125–135 eV for modern SDDs and ~140–150 eV for older Si(Li). At lower energies, resolution improves; at higher energies, it slightly worsens. The 70× spread between intrinsic linewidth and detector FWHM is the price paid for the SDD's broad energy range and high count-rate capability. (Wavelength-dispersive spectrometers — WDS, Chapter 25 in the cross-technique discussion — give 5–20 eV resolution but only one element at a time and at much slower rates.)

Energy resolution sets which lines you can resolve from each other. Cu Kα₁ at 8.048 keV and Kα₂ at 8.028 keV are 20 eV apart — far below detector resolution; they appear as one peak. Cu Kα at 8.05 keV and Cu Kβ at 8.91 keV are 860 eV apart — well-resolved. The trick is that the K-family lines are usually well-separated within each element, but across elements you can have **peak overlap** problems.

### Trade-off

EDS optimizes for **broad energy coverage and high count-rate at the cost of energy resolution**. WDS optimizes for high resolution at the cost of speed and parallel coverage. EDS is right for 95% of analytical work; WDS is right for the remaining 5% where you need to resolve closely-spaced lines or quantify low-concentration elements.

### Worked example: counting requirement for trace detection

**Problem.** You want to detect 0.1 wt% iron in a copper-silicon matrix. Approximately how many counts do you need in the Fe Kα peak to call it "detected"?

**Given.** 0.1 wt% Fe; you want statistical detection.

**Reasoning.** A peak is conventionally "detected" when its counts above background exceed three times the standard deviation of the background. For Poisson-distributed counts, $\sigma_{\text{bg}} = \sqrt{N_{\text{bg}}}$ where $N_{\text{bg}}$ is background counts. For Fe in Cu-Si at 0.1 wt%, the Fe Kα peak might be 3% of the matrix Cu Kα peak, on a continuum background that depends on dwell time. As a rule of thumb: you need at least 100 counts in the peak above background to claim detection. To get 100 counts on a 0.1% element, you need roughly 100,000 counts on the matrix matrix peak. At a typical EDS count rate of 5,000 cps total on a metal, that's ~10 minutes of acquisition.

**Sanity check.** Standard EDS detection limits are quoted at ~0.1 wt% (1000 ppm) under reasonable counting times. Our calculation matches.

**General lesson.** Trace detection in EDS is a counting-time problem. Doubling the time roughly halves the trace level you can detect (signal/background scales as $\sqrt{t}$). For very-low-trace work you need much longer counting and ideally WDS.

### What Goes Wrong Here

The principal artifacts of the EDS spectrum:

- **Peak broadening (FWHM).** Real, unavoidable. Mitigation: choose detectors with the best resolution available; recognize that 125-eV resolution means closely-spaced lines blend.
- **Si escape peak.** When an X-ray photon is absorbed in the silicon detector and the resulting Si Kα photon (1.74 keV) escapes the detector instead of being absorbed, the recorded energy is the parent peak energy minus 1.74 keV. Recognition: a small peak at $E_{\text{parent}} - 1.74$ keV. Common for parent peaks in the 2–10 keV range. Mitigation: software automatically flags escape peaks; check the analysis.
- **Sum (coincidence) peaks.** If two photons arrive at the detector during the same measurement period, the electronics register one event at the sum of the two energies. Recognition: a peak at exactly twice the energy of a strong line, or at the sum of two strong lines. Common at high count rates. Mitigation: lower count rate (lower beam current, smaller solid angle).
- **Si internal fluorescence and absorption edge.** Within the silicon detector itself, X-rays produce silicon Kα photons internally. The artifact appears as a small Si peak even when the specimen contains no silicon. Recognition: a small Si peak with a particular profile. Standard correction is applied automatically by the analysis software.
- **Peak overlaps.** Two elements whose lines fall within the FWHM of each other are ambiguous. The week-6 source provides a misidentification table for common overlap pairs (e.g., O Kα at 0.523 keV vs. V Lα at 0.511 keV; Mn Kα at 5.90 keV vs. Cr Kβ at 5.95 keV). Analysis software does peak deconvolution; the operator must verify the result.

---

## 4. Acquisition strategy

The question this section answers is: what knobs does the operator turn to get a usable spectrum?

### Mechanism — five parameters, five trade-offs

Per the source's "best practices":

**1. Beam energy.** Section 2 covered this. Pick kV at 1.5–2.5× the highest critical ionization energy of interest. Higher kV gains heavy-line sensitivity at the cost of interaction volume and spatial resolution.

**2. Beam current.** Higher current → more X-rays per second → faster spectrum acquisition. Limited by:
- **Dead time.** The detector cannot process events arriving faster than its electronics can clear. Dead time is

$$
\text{Dead time} = \left(1 - \frac{\text{OCR}}{\text{ICR}}\right) \times 100\%
$$

where ICR is input count rate (events arriving) and OCR is output count rate (events processed). At 30% dead time, 30% of arriving events are missed because the detector is busy. Recommended operating range: 20–30% dead time. Above 50% the spectrum quality degrades from sum peaks and pulse pileup.

**3. Amp time (shaping time, process time).** The detector electronics integrate each event over a specific time window — the amp time. Longer amp time gives better energy resolution (more accurate charge measurement) but lower count-rate capability. Typical settings: 1–6 (manufacturer-specific units), with longer numbers for high-resolution work and shorter for high-count work.

**4. Counting time / live time.** The longer you count, the better your statistics on weak peaks. For routine elemental ID, 30–60 s is plenty. For trace detection, 10+ minutes. For mapping, the per-pixel dwell × number of pixels sets the total time.

**5. Solid angle of the detector.** Often controllable by detector translation in/out along its axis. Larger solid angle = more X-rays collected per unit time, at the cost of geometric constraints. Most modern SDDs allow this.

### Spectrum collection, line scan, mapping

**Spot analysis.** Park the beam at one point; collect a spectrum. Best for identifying composition at one specific feature.

**Spectrum imaging (mapping).** Scan the beam across a region; for each pixel, store the full spectrum (or selected element peaks). Build a 2D map of where each element is present. Modern SDDs handle map collection in 1–10 minutes.

**Line scan.** Beam moves along a line; spectra collected at intervals. Useful for diffusion profiles, interface composition gradients, etc.

### Take-off angle and detector geometry

The EDS detector mounts on the chamber wall at a fixed elevation angle (typically 30–40°). The **take-off angle** for X-rays is the angle from the specimen surface to the line connecting the beam impact point to the detector face. For a flat specimen at 0° tilt at the optimal working distance, the take-off angle equals the elevation angle. If the specimen is tilted, the take-off angle changes — the operator must compute or read the new angle from the software.

The detector's solid angle $\Omega$ depends on its distance from the specimen. Closer detector, larger solid angle, more counts. Most instruments have a sliding mechanism that lets the operator translate the detector toward or away from the specimen along the snout axis.

### Trade-off

EDS acquisition optimizes for **count rate at the cost of dead time degradation and spectrum quality** at high count rates. The operator's job is to balance count rate against acquisition time against detector saturation. The 20–30% dead time recommendation captures the sweet spot.

### Worked example: setting up an analysis for a polished steel

**Problem.** You need to identify the elements in a polished steel specimen (likely Fe, possibly Cr, Ni, Mn, Si, C, others). The instrument is a 25 kV W-thermionic SEM with a 30 mm² SDD.

**Reasoning.**
- **Beam energy:** 20 kV. Cu has $E_c = 8.98$ keV; Ni at 8.33; Cr at 5.99; Fe at 7.11. Choose kV = 20 to cover all $K$ lines comfortably.
- **Beam current:** Set so dead time is ~25% on the spectrum view. Target ICR: 5,000–10,000 cps.
- **Amp time:** Default mid-range setting (typically "3" or equivalent).
- **Counting time:** 60 s for a survey spectrum; 5+ min for trace elements (Mn at 0.5 wt% in stainless, for example).
- **Detector position:** Fully extended for max solid angle.
- **Sample tilt:** 0°; standard take-off angle.

**Sanity check.** Standard parameters for steel composition analysis at the 0.1 wt% level. At 60 s, expect to identify all major elements; trace elements at the 0.05 wt% level need more time.

### What Goes Wrong Here

- **Dead time too high (>50%).** Spectrum has prominent sum peaks; quantification fails. Diagnostic: read dead time on the screen; reduce beam current or pull the detector back.
- **Counting time too short for trace elements.** Spectrum looks clean but trace elements are below detection. Diagnostic: examine the noise level near where the trace peak should be.
- **Specimen tilt confusing software.** Quantification software assumes a specific take-off angle; if the specimen is tilted and the software doesn't know, quant numbers are wrong. Diagnostic: enter tilt explicitly into the software.
- **Detector position inconsistent between specimens.** If the operator forgot to standardize detector position, count rates and quant calibration drift between specimens. Fix: settle on one detector position; always run standards there.

---

## 5. Synthesis: putting the spectrum to work

EDS is qualitative, semi-quantitative, mapping, and line scan all in one detector. The questions you can answer:

- **What elements are here?** Qualitative ID. 30 s spot acquisition.
- **In what proportions?** Semi-quantitative analysis. Software calculates ZAF or PhiRhoZ corrections from the spectrum and matrix. Standard corrections include atomic-number (Z), absorption (A), and fluorescence (F) effects. Accuracy ~±5% relative for major elements (>10 wt%) and ~±10–20% for minor elements (1–10 wt%). For accurate trace quantification, you need standards-based calibration, not standardless analysis.
- **Where are the elements located?** Spectrum imaging. Map collection, then per-element images. Useful for phase distribution, interface composition, and segregation.
- **How does composition vary across an interface?** Line scan across the interface, individual spectra at each pixel.

The spatial resolution of EDS is set by the X-ray-generating volume — roughly the Kanaya–Okayama interaction volume (Chapter 6). For 25 kV in copper: ~1–2 μm. So an EDS map at 25 kV cannot resolve features below ~1 μm, even if the SE image has nanometer resolution. To improve EDS spatial resolution, drop kV (smaller interaction volume), but also drop heavy-line sensitivity. Modern EDS work on thin films often runs at 5–10 kV for both reasons.

The composition of a specimen is, at heart, a question about which atoms are present and where. EDS answers that question by counting photons whose energies are atomic fingerprints. The wonder is that the entire periodic table is encoded in the inner-shell binding energies — a quantum-mechanical accident of nuclear charge and electron screening — and the SEM-EDS pair reads that encoding from a few cubic micrometers of material in a minute. A geologist's pebble in three minutes; an alloy's phase distribution in fifteen; a tissue section's iron-rich inclusions in ten. The same physics across all three.

**Putting it together (worked scenario).** A nanomedicine PI brings a polymeric nanoparticle drug delivery vehicle with iron oxide cores intended for magnetic guidance. Goals: (a) confirm Fe is present in the particles, (b) measure approximate Fe loading, (c) check whether Fe is uniformly distributed inside particles or surface-localized.

- **Goal (a).** 20 kV, 60 s spot spectrum on a particle. Fe Kα peak at 6.40 keV identifies Fe presence.
- **Goal (b).** Standardless quantification on the same spectrum. Fe wt% relative to C, O, polymer matrix elements.
- **Goal (c).** EDS spectrum imaging at 5 kV (smaller interaction volume; better spatial resolution). 5–10 min per map. Fe map shows whether the iron is in cores or shells.

Three questions, one specimen, one EDS session.

---

## 6. Pre-lab Checklist (Lab 9 — first EDS analysis)

**By the end of this chapter, you should be able to:**

- Set up an EDS analysis with appropriate kV, beam current, dead time, and counting time.
- Interpret a spectrum and identify principal peaks.
- Recognize escape peaks, sum peaks, and Si internal-fluorescence artifacts.
- Distinguish elemental ID from semi-quantitative analysis.

**Bring to lab:**

- This chapter, especially Sections 2 and 4.
- A polished or dry specimen with at least two known elements (a polished steel is convenient).
- A periodic table or X-ray-line lookup table.

**Expect on the floor:**

- A guided EDS spectrum acquisition on a known standard (often a steel or nickel-base alloy).
- Identification of escape peaks and sum peaks in real time.
- A first attempt at quantification with standardless ZAF correction.
- Discussion of detection limits: where can you trust the trace numbers, where are you below detection?

### Hazards and Safe Practice

The hazards specific to EDS:

- **X-ray emission from the specimen.** The same X-rays you measure also leak out of the chamber. Modern SEMs are shielded for routine imaging; check that the X-ray dosimeter (if your lab has one) is at background. For specimens with high-Z elements at extended high-current operation, the dose may rise.
- **Liquid nitrogen for Si(Li) detector cooling** (older instruments). Cryogen burn risk and asphyxiation in confined spaces. PPE; ventilated rooms.
- **High-voltage detector electronics.** Service work only by trained personnel.
- **Specimen contamination from heavy elements.** EDS routinely identifies elements you didn't expect; the spectrum tells you what's actually on the surface, not what you intended to put there. Hydrocarbon contamination, polishing media residue, fingerprints — all show up. This is a feature for forensics and a nuisance for clean analysis.

For comprehensive treatment, see **Appendix A**.

---

## 7. Quick-Reference Table

| Parameter | Symbol / units | Typical range | Notes |
|---|---|---|---|
| Critical ionization energy K-shell | $E_{c,K}$ (keV) | 0.28 (C) to 100+ (heavy elements) | sets minimum kV |
| Overvoltage | $U_0 = E_0/E_c$ | $\geq$ 2 for efficient X-ray generation | rule of two |
| Fluorescence yield K-shell | $\omega_K$ | 0.005 (C) to ~1 (heavy) | hard for light elements |
| EDS energy resolution | FWHM at Mn Kα | 125–150 eV | vs. WDS at ~5 eV |
| Dead time | (1 − OCR/ICR)×100 | recommend 20–30% | <50% always |
| Detection limit | wt% | ~0.1% (1000 ppm) | longer counting → lower |
| Spatial resolution | μm | ~1 μm at 25 kV in metals | scales with interaction volume |
| Counting time (qualitative) | s | 30–60 | for major elements |
| Counting time (trace) | min | 5–30 | for 0.01–0.1 wt% |
| Beam energy (alloy survey) | keV | 15–25 | covers most K and L lines |

---

## 8. Exercises

### Warm-up

**Exercise 9.1 (LO: explain X-ray generation).**
In one or two sentences, explain why the energy of a Cu Kα X-ray photon is the same regardless of which beam electron caused it. Difficulty: easy.

**Exercise 9.2 (LO: predict overvoltage requirement).**
The Au L₃ critical ionization energy is 11.92 keV. What is the minimum beam energy for efficient EDS analysis using the L line? Difficulty: easy.

**Exercise 9.3 (LO: name an artifact).**
You see a peak at 6.31 keV in your EDS spectrum, and the analysis software does not assign it to any element. The strongest peak in the spectrum is at 8.05 keV. What artifact might this be? Difficulty: easy.

### Application

**Exercise 9.4 (LO: choose kV).**
You need to analyze a thin coating of titanium nitride (Ti, N) on tungsten. The film thickness is 200 nm; the substrate is bulk W. What kV would let you see the TiN film without dominating the signal from the W substrate? Difficulty: medium.

**Exercise 9.5 (LO: calculate detection limit).**
A 60-second EDS spectrum shows about 200,000 total counts. The Fe Kα peak you can detect with 99% confidence has 100 counts above background. Estimate the Fe weight percentage detection limit if Fe Kα is roughly 5% efficiency-corrected of the total signal at 1 wt%. Difficulty: medium.

**Exercise 9.6 (LO: interpret peak overlap).**
You see a single peak at 5.40 keV in a spectrum from an unknown specimen. The two most likely candidates are V Kα (4.95) and Mn Kα (5.90). Are these resolved or not? What additional information would help you decide? Difficulty: medium.

**Exercise 9.7 (LO: choose mode for the question).**
For each scenario, name the EDS mode (point, line scan, map, spectrum imaging): (a) confirm an alloy is mostly iron; (b) measure how silicon concentration changes across a 1 μm grain boundary; (c) image where lead is present in a polished cross-section of a leaded brass. Difficulty: medium.

### Synthesis

**Exercise 9.8 (LO: integrate full EDS workflow).**
A nanomedicine lab has hollow polymer nanocapsules, ~200 nm diameter, intended to load gadolinium for MRI contrast. The lab needs to (a) confirm gadolinium is loaded, (b) measure the loading per capsule, (c) check whether Gd is in the polymer shell or the inner cavity. Specify EDS parameters (kV, current, counting time, mode) for each, and explain in one sentence each how the chapter's physics drove the choice. Difficulty: hard.

### Challenge

**Exercise 9.9 (open-ended).**
Run an EDS spectrum on the most ordinary metal object in your lab (a paperclip, a screw, a coin). Identify the elements. Compare to the published composition of the alloy. Note any discrepancies and possible explanations (contamination, sub-trace alloying, surface oxidation, etc.). Difficulty: open-ended.

---

## 9. Summary

You walked into this chapter knowing that an SEM can measure composition. You walk out with the physics — inner-shell ionization and characteristic X-ray emission — that makes that measurement possible, the operator's controls (kV, current, dead time, counting time, detector position) that decide whether the measurement is good, and the artifacts (peak broadening, escape, sum, internal fluorescence, peak overlap) that haunt every spectrum. You can run an EDS analysis end-to-end and interpret the result.

The one idea that matters most: the energy of a characteristic X-ray photon is a fingerprint of the atom that emitted it. Read the energies, name the atoms. Everything else — overvoltage, dead time, peak overlap — is engineering around that one piece of physics.

The common mistake to watch for: trusting standardless quantification at trace levels. Standardless ZAF gives ±5% relative for major elements, but at 0.1 wt% the same correction has uncertainties as large as the value. For trace work, run standards.

The Feynman test: explain to a labmate, without using the word "shell," why every element has its own characteristic X-ray energies.

---

## 10. Connections Forward

Chapter 18 (EELS) introduces an analytical technique with complementary strengths to EDS — better spatial resolution, better light-element sensitivity, but in TEM not SEM. Chapter 23 synthesizes EDS artifacts comparatively with other technique-specific artifacts. Chapter 25 covers cross-technique applications, including how EDS combines with HAADF and EELS for complete analytical characterization in modern STEM work.

The question this chapter raised but did not answer: how do you quantify accurately when the specimen is rough, embedded in a substrate, or layered? The matrix-correction methods (ZAF, PhiRhoZ) work for flat homogeneous samples; for the others, more careful standards-based work is required. The full treatment is beyond this chapter's scope; consult Goldstein 2018 Chapters 14–19 for the comprehensive approach.

---

**What would change my mind:** evidence that standardless EDS quantification can routinely achieve ±2% relative accuracy on trace elements (<1 wt%) without standards. This is not what current technology delivers. Standards-based work remains the gold standard for trace quantification.

**Still puzzling:** the practical decision of when to switch from EDS to WDS (or to EELS in TEM) is rarely formalized; most labs default to EDS and don't reach for the alternative even when it would help. The 5-eV resolution of WDS could resolve many overlap problems that EDS struggles with.

**Tags:** `EDS`, `characteristic-X-rays`, `fluorescence-yield`, `peak-overlap`, `spectrum-artifacts`

---

### Note to the professor

`[verify]` markers in this chapter:
- Cu critical ionization energies (8.98 keV K, 0.93 keV L₃) — standard textbook values, source-stated for similar elements.
- Au L critical ionization energy (~11.92 keV).
- Specific X-ray line energies (Cu Kα₁ 8.048, Cu Kα₂ 8.028) — standard tabulated values.
- Detector resolution at Mn Kα (~125–150 eV) — manufacturer-specific.
- Some specific transition probabilities and weights of lines.

Voice anchoring: anchored. Cold open with the geologist's pebble. Etymology used at "Auger" (Pierre Auger), "bremsstrahlung" (German for braking radiation), "fluorescence" implicit. Capability ending. Wonder grounded in numbers (3.6 eV per e-h pair; 1,400 e-h pairs per 5 keV photon; 100,000 counts for 0.1 wt% detection).
