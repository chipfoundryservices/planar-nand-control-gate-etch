# Chapter 2: Control Gate Stack Materials: Polysilicon, Polycide, Silicide Caps, and Word Line Conductors

## Executive Summary

The control gate, as etched, is rarely a single material. In its most common planar NAND implementation it is a bilayer — a heavily doped polysilicon base, topped by a refractory metal silicide or polycide cap — and each layer exists to satisfy a requirement the other layer cannot satisfy alone. This chapter develops the materials science of each component: why polysilicon remains the base conductor despite its resistance limitations, why tungsten silicide (WSix) became the dominant cap material, what alternative silicide chemistries exist and why they saw limited adoption, and how dopant strategy and grain structure in the polysilicon base interact with both gate electrical behavior and the etch chemistry developed in Part II. Readers should treat this chapter as establishing the "what" and "why" of the materials stack that Chapters 6 and 7 etch.

---

## Part 1: The Polysilicon Base

### 1.1 Why Polysilicon, Not Single-Crystal Silicon or a Pure Metal

Control gate polysilicon is deposited by low-pressure chemical vapor deposition (LPCVD) as a conformal, polycrystalline film over the ONO interpoly dielectric. Polysilicon is used rather than a deposited metal for reasons largely inherited from conventional logic gate engineering: polysilicon's work function can be tuned via doping to set an appropriate threshold voltage, it forms a stable, well-characterized interface with the dielectric beneath it, and — critically for this book's concerns — it etches in well-understood halogen-based plasma chemistry (Chapter 6) with the selectivity and profile control multi-decade industry experience has optimized.

### 1.2 Doping Strategy

| Property | Typical Value (advanced planar node) | Significance |
|----------|----------------------------------------|--------------|
| **Dopant species** | Phosphorus (n+ poly, dominant case) | Sets polysilicon sheet resistance and work function |
| **Doping method** | In-situ doped LPCVD or post-deposition implant + anneal | Affects grain structure and subsequent etch behavior |
| **As-deposited sheet resistance** | 200–500 Ω/sq (heavily doped) | Still too high for word line conductor alone at scaled pitch — motivates silicide cap (Chapter 3) |
| **Grain size** | 50–150 nm, depending on deposition temperature and anneal | Affects etch rate uniformity and line edge roughness (Chapter 10) |

**Consequence for etch:** Grain boundaries etch at a measurably different rate than grain interiors in halogen plasma chemistry, because grain boundaries present a higher density of dangling bonds and a different local doping concentration than bulk crystallite material. At scaled gate lengths, where a gate line may span only a handful of grains across its width, grain-boundary-driven etch rate variation becomes a measurable contributor to line edge roughness (LER) — a connection developed quantitatively in Chapter 10.

### 1.3 Why Phosphorus Doping Specifically

Phosphorus is preferred over alternative n-type dopants (arsenic, antimony) for control gate polysilicon primarily because of its higher solid solubility in silicon at LPCVD and anneal temperatures, enabling the heavier doping levels needed to minimize sheet resistance, combined with well-characterized diffusion behavior that process integration teams can model reliably across thermal budget variations in the rest of the flow.

---

## Part 2: The Silicide/Polycide Cap

### 2.1 What "Silicide" and "Polycide" Mean, and the Difference Between Them

- **Silicide:** A compound formed by the reaction of a metal with silicon (e.g., WSi₂, the fully reacted tungsten silicide stoichiometry), typically formed by depositing a metal layer and annealing it to react with the underlying polysilicon, or by directly depositing a pre-reacted silicide film
- **Polycide:** The industry term for the complete bilayer structure — silicide cap directly on top of polysilicon base — used as a single word line conductor stack

This book, like most process literature, uses "polycide" to refer to the stack and "silicide" to refer specifically to the cap material's chemistry, a convention followed throughout the remaining chapters.

### 2.2 Why Tungsten Silicide (WSix)

| Candidate Silicide | Resistivity (µΩ·cm, as formed) | Thermal Stability | Industrial Adoption |
|---------------------|-------------------------------|---------------------|----------------------|
| **WSix (tungsten silicide)** | 60–100 | Stable to >900°C; compatible with downstream anneal budget | Dominant choice for planar NAND control gate caps |
| **TiSi₂ (titanium silicide)** | 15–20 (C54 phase) | Phase transformation and agglomeration issues at narrow line widths | Common in logic contacts; limited control gate adoption due to narrow-line resistance degradation |
| **CoSi₂ (cobalt silicide)** | 15–20 | Better narrow-line behavior than TiSi₂ | Logic salicide processes; less common as a deposited (non-self-aligned) control gate cap |

WSix's resistivity is higher than TiSi₂ or CoSi₂ in absolute terms, but its thermal stability and compatibility with the specific deposition approach used for control gate caps (typically direct CVD or sputter deposition of a pre-formed or co-deposited silicide layer, rather than the self-aligned salicide process common in logic source/drain contacts) made it the dominant practical choice for planar NAND word lines across most of the technology's production history. Chapter 3 quantifies the resistance benefit this choice delivers relative to bare polysilicon.

### 2.3 Deposition Approach and Its Etch Consequences

Control gate silicide caps are typically deposited directly (CVD tungsten silicide, or sputtered W followed by an anneal step that reacts it with the polysilicon surface) rather than through a self-aligned salicide process. This means the as-deposited cap is already a continuous blanket film requiring full pattern definition by etch — unlike self-aligned logic salicide, which forms only where exposed silicon is present after gate patterning is complete. This distinction matters directly to Chapter 6: the control gate etch must pattern the *entire* silicide cap thickness as part of the stack etch sequence, rather than patterning bare polysilicon and forming silicide afterward on an already-defined gate.

---

## Part 3: Stack Summary and Interfaces

### 3.1 The Complete Control Gate Stack, Top to Bottom

| Layer | Typical Thickness | Function | Etch Treatment |
|-------|---------------------|----------|------------------|
| **Hard mask** | Process-dependent | Pattern transfer | Chapter 5 |
| **WSix (or equivalent) silicide cap** | 50–100 nm | Sheet resistance reduction | Chapter 6 |
| **Control gate polysilicon** | 60–100 nm | Gate conductor, work function, coupling plate | Chapter 7 |
| **ONO interpoly dielectric** | 10–15 nm (oxide equivalent) | Landing/stop interface — not etched by this book's process (see companion volume Ch. 7 for breakthrough etch) | Chapter 7 (landing only), Chapter 13 (damage) |

### 3.2 Interfaces That Matter to Etch Process Design

Two interfaces within this stack carry disproportionate process risk:
1. **Silicide/polysilicon interface:** A deliberate chemistry transition point (Chapter 6), where incomplete silicide removal leaves a conductive residue that can bridge adjacent gates (Chapter 11), while over-aggressive transition risks attacking polysilicon with a chemistry not yet tuned for it
2. **Polysilicon/ONO interface:** The soft-landing transition (Chapter 7), where the overetch budget must be large enough to clear polysilicon residue across full wafer non-uniformity, yet small enough to avoid meaningful ONO thinning or damage (Chapter 13)

---

## Chapter Summary

- Control gate polysilicon is heavily phosphorus-doped for low resistivity and tunable work function, with grain structure that measurably affects etch uniformity and line edge roughness at scaled pitch
- WSix is the dominant silicide cap material for planar NAND control gates, chosen for thermal stability and deposition compatibility despite higher resistivity than alternative silicides like TiSi₂ or CoSi₂
- Control gate silicide caps are typically deposited as continuous blanket films requiring full pattern definition by etch, unlike self-aligned logic salicide
- The complete stack (hard mask, silicide, polysilicon, down to ONO) has two high-risk interfaces — silicide/polysilicon and polysilicon/ONO — that organize the process design chapters in Part II

## Study Questions

1. Why does control gate polysilicon remain the base conductor material despite silicide's much lower resistivity?
2. Explain the distinction between "silicide" and "polycide" as used in this book, and why the complete bilayer is the relevant etch target.
3. Why was WSix the dominant practical choice for planar NAND control gate caps despite TiSi₂ and CoSi₂ offering lower resistivity?
4. Why does the fact that control gate silicide is deposited as a blanket film (rather than formed by self-aligned salicide) directly affect the scope of the etch process described in Chapter 6?

---

[← Chapter 1](01-control-gate-role.md) · [Index](../INDEX.md) · [Next: Chapter 3 →](03-word-line-architecture-rc.md)
