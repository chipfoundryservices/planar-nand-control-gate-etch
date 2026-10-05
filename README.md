# Planar NAND Control Gate Etch

## Silicide/Polysilicon Word Line Plasma Etch, ONO Soft-Landing Process Control, and the Resistance-Scaling Limits of the Planar NAND Control Gate

**ChipFoundryServices Technical Series**

---

## Overview

*Planar NAND Control Gate Etch* is a focused technical treatment of the plasma etch processes that define the control gate (word line) in planar (two-dimensional) NAND flash memory. Where the companion volume *Planar NAND Floating Gate Etch* treats the full five-layer stack etch — silicide cap through tunnel oxide — as a single continuous process governed by the tunnel oxide at its base, this book isolates the top half of that same stack and asks a different question: what does it take to pattern a low-resistance, electrically uniform word line conductor that lands cleanly on the ONO interpoly dielectric without ever touching it?

That question turns out to have its own physics, its own failure modes, and its own scaling history, distinct from — though tightly coupled to — the floating gate etch beneath it:

- **Word Line Electrical Integrity as the Etch Target:** Control gate etch is judged first by gate length (CD) uniformity and sheet resistance, not retention — the same stack, read from the top down rather than the bottom up
- **Silicide/Polycide Conductor Engineering:** WSix and related polycide caps exist to solve a resistance-scaling problem that has nothing to do with charge storage, and that problem gets harder, not easier, as word line pitch shrinks
- **ONO as a Landing Zone, Not a Floor:** The control gate etch must stop *on top of* ONO without punching through it — a soft-landing problem that is the mirror image of the floating gate etch's tunnel-oxide stopping problem treated in the companion volume
- **Array/Periphery Duality:** Unlike the floating gate, the control gate polysilicon is also the gate conductor for peripheral logic transistors on the same die, patterned in the same etch step across radically different pattern densities
- **Resistance as the Scaling Casualty:** As word line pitch scaled down, control gate sheet resistance — not etch profile alone — became an independent limiter of array RC delay and read/program speed, driving the polycide-to-metal-cap transition this book traces

---

## Audience

This book is designed for:
- **Process Engineers** developing or troubleshooting control gate (word line) etch recipes
- **Integration Engineers** managing the interaction between control gate etch, ONO landing, and downstream floating gate processing
- **Device/Circuit Engineers** tracing word line RC delay and read/program speed limits back to etch and film stack root causes
- **Equipment Engineers** designing or specifying chambers for dual-pitch (array/periphery), multi-material gate stack etch
- **Memory Architects** seeking the physical history of word line resistance scaling in planar NAND
- **Students and Researchers** studying gate conductor engineering across the logic/memory boundary

---

## Table of Contents

### Front Matter
- **Preface:** The Control Gate as a Conductor Problem Wearing a Memory Device's Clothes

### Part I: Control Gate Fundamentals (Chapters 1–4)
1. The Control Gate's Role in Planar NAND & Why It Earns Its Own Volume
2. Control Gate Stack Materials: Polysilicon, Polycide, Silicide Caps, and Word Line Conductors
3. Word Line Architecture: Sheet Resistance, RC Delay, and the Case for Silicide/Metal Caps
4. Electrical Requirements: Gate Length Control, Vt Uniformity, and Coupling Ratio Sensitivity to Control Gate Profile

### Part II: Control Gate Etch Process Design (Chapters 5–9)
5. Hard Mask Strategy for Control Gate Patterning
6. Silicide/Polycide Cap Etch Chemistry: WSix and Refractory Metal Silicide Systems
7. Control Gate Polysilicon Main Etch & Soft-Landing on ONO
8. RF Bias and Ion Energy Management Near the ONO Interface
9. Array/Periphery Etch Uniformity: Pattern Density and Dual-Pitch Recipe Design

### Part III: Process Phenomena & Defect Control (Chapters 10–14)
10. Critical Dimension Control & Gate Length Uniformity at Scaled Word Line Pitch
11. Polysilicon/Silicide Stringers, Footing, and Gate-to-Gate Bridging at the Control Gate Level
12. Microloading & ARDE Effects Between Array and Periphery Control Gate Features
13. ONO Interface Damage: Overetch, Punch-Through Risk, and Coupling Ratio Degradation
14. Endpoint Detection for Multi-Layer Silicide/Polysilicon/ONO Transitions

### Part IV: Production Integration & Resistance Scaling (Chapters 15–16)
15. Word Line Resistance Scaling: From Polycide to Tungsten and the Limits of the Planar Control Gate
16. Post-Etch Clean, Inspection, and Yield Learning for Control Gate Arrays

---

## File Organization

```
planar-nand-control-gate-etch/
├── README.md                          (this file)
├── PREFACE.md                         (Foundational Philosophy & Context)
├── INDEX.md                           (Chapter Index & Navigation)
├── .gitignore
└── chapters/
    ├── 01-control-gate-role.md
    ├── 02-stack-materials-conductors.md
    ├── 03-word-line-architecture-rc.md
    ├── 04-electrical-requirements-coupling.md
    ├── 05-hard-mask-strategy.md
    ├── 06-silicide-polycide-etch-chemistry.md
    ├── 07-polysilicon-main-etch-ono-landing.md
    ├── 08-rf-bias-ono-interface.md
    ├── 09-array-periphery-uniformity.md
    ├── 10-cd-control-gate-length.md
    ├── 11-stringers-footing-bridging.md
    ├── 12-microloading-arde-array-periphery.md
    ├── 13-ono-interface-damage.md
    ├── 14-endpoint-detection-multilayer.md
    ├── 15-word-line-resistance-scaling.md
    └── 16-post-etch-clean-yield.md
```

This book is scoped intentionally to *chapters only* — no appendices or asset directories are declared unless and until they are actually populated, so the table of contents above always matches what is committed to the repository.

---

## Key Technical Themes

### 1. **The Control Gate Is Judged From the Top Down**
Where the floating gate etch is ultimately judged by what happens at the tunnel oxide, the control gate etch is judged by what happens at the word line driver and the peripheral decode circuitry: gate length, sheet resistance, and RC delay. This book treats the control gate as a conductor-engineering problem first, one that happens to sit on top of a memory stack.

### 2. **Silicide Exists to Fight Physics Lithography Already Won**
Scaling word line pitch shrinks cross-sectional conductor area faster than it shrinks word line length, so sheet resistance rises even as the transistor itself scales favorably. Silicide and polycide caps are a direct, material-level response to this resistance-scaling problem — this book treats them as such, rather than as an incidental process detail.

### 3. **ONO Is a Landing Zone, Not a Floor**
The companion floating gate volume treats tunnel oxide as the etch stop that must never be damaged. This book treats ONO the same way from the opposite side: the control gate etch must land on ONO, stop there with minimal overetch, and leave the interpoly dielectric's barrier properties — and therefore the coupling ratio it sets — intact.

### 4. **One Etch, Two Pattern Densities**
Control gate polysilicon is not exclusive to the memory array. The same film stack, patterned in largely the same etch step, forms gate conductors for peripheral logic transistors — decoders, charge pumps, sense amplifiers — at pattern densities and feature geometries very different from the array. This book treats array/periphery duality as a first-order recipe design constraint, not an edge case.

### 5. **Resistance Scaling Has Its Own Endpoint**
Transistor-level scaling (Chapters 10–13) can, in principle, continue past the point where word line resistance becomes the binding constraint on array speed. Chapter 15 traces how control gate conductor engineering — not transistor electrical scaling — became an independent limiter in its own right, and how the industry's response (first polycide, later full metal word lines in the 3D NAND successor architecture) reflects that.

---

## Constraints & Scope

### In Scope
- Planar (2D) NAND control gate / word line conductors: polysilicon, polycide (WSix and related silicides), and silicide-capped stacks
- The control gate/word line etch step specifically — silicide or metal cap plus control gate polysilicon, down to and landing on the ONO interpoly dielectric
- Array and peripheral logic gate conductor patterning performed in the same etch module
- Technology nodes from >1µm generations through sub-20nm planar NAND (pre-3D NAND transition)
- Capacitively and inductively coupled plasma etch systems used for control gate definition

### Out of Scope
- Floating gate polysilicon etch and tunnel oxide selectivity (covered in depth in the companion volume, *Planar NAND Floating Gate Etch*)
- ONO interpoly dielectric breakthrough etch chemistry (covered in the companion volume's Chapter 7)
- Charge storage physics, coupling ratio derivation, and retention/endurance mechanisms (covered in the companion volume's Chapter 4; referenced here only as the electrical context control gate design must respect)
- 3D NAND word line (replacement metal gate / tungsten fill) processes (covered in sibling 3D NAND volumes)
- Generic single-material logic polysilicon gate etch outside the planar NAND control gate context (covered in the polysilicon gate etch volume of this series)
- Self-aligned STI integration (covered in the companion volume's Chapter 3, since STI self-alignment couples to the floating gate etch, not the control gate etch)

---

## Relationship to Sibling Volumes

This book shares a technical series with other ChipFoundryServices etch volumes. In particular:
- ***Planar NAND Floating Gate Etch*** is this book's direct companion volume: it treats the full stack etch (silicide through tunnel oxide) as a single continuous process judged by tunnel oxide integrity and charge retention. This book re-examines the top half of that same stack — silicide cap and control gate polysilicon — judged instead by word line conductivity and ONO landing quality. The two books deliberately do not duplicate each other's primary analysis; each defers to the other for topics outside its stated scope.
- **Polysilicon gate etch (logic devices):** covers single-material polysilicon gate definition for logic in isolation; this book extends that foundation to the silicide-capped, dual-pattern-density control gate context specific to planar NAND
- **3D NAND process volumes** (slit etch, memory hole etch, high-aspect-ratio ONO stack etch): cover the vertical successor architecture, in which the planar control gate's resistance-scaling problem is resolved by a fundamentally different conductor strategy (metal word line fill); Chapter 15 is the explicit bridge to that discussion
- **Shallow trench isolation etch:** covers STI as a general-purpose isolation module; this book does not address STI, since STI self-alignment in planar NAND couples to the floating gate etch, not the control gate etch

This volume assumes the reader has access to, or has read, *Planar NAND Floating Gate Etch* for full stack context; it is written to stand on its own for readers whose primary interest is the control gate/word line conductor problem specifically, with explicit cross-references provided wherever the two books' subject matter touches.

---

## Development Status

**Status:** Complete (16 of 16 chapters)

**Version:** 1.0

---

## Attribution & License

This book is authored by **ChipFoundryServices** and distributed under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** license.

**Academic citations welcome.** Please cite as:

> ChipFoundryServices. (2026). *Planar NAND Control Gate Etch — Silicide/Polysilicon Word Line Plasma Etch, ONO Soft-Landing Process Control, and the Resistance-Scaling Limits of the Planar NAND Control Gate*. GitHub. https://github.com/chipfoundryservices/planar-nand-control-gate-etch

---

[Begin Reading →](PREFACE.md)
