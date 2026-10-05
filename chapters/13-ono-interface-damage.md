# Chapter 13: ONO Interface Damage: Overetch, Punch-Through Risk, and Coupling Ratio Degradation

## Executive Summary

This chapter analyzes, in full, what happens when the soft-landing step's protections (Chapters 7–8) are imperfect — as they always are to some finite degree in a production process subject to real non-uniformity (Chapter 12). We develop a damage taxonomy (thinning, localized punch-through, and sub-threshold trap generation), connect each damage mode quantitatively to the coupling ratio and electrical consequences previewed in Chapter 4, and establish the overetch/selectivity/non-uniformity relationship as a single coupled system that production process control must manage holistically rather than through any single parameter in isolation.

---

## Part 1: A Taxonomy of ONO Interface Damage

### 1.1 Uniform Thinning

The mildest damage mode: overetch during soft-landing removes a small, roughly uniform thickness of ONO across the wafer (or across a given pattern-density regime, per Chapter 12's analysis), reducing ONO's physical thickness without creating localized defects. This mode's electrical consequence — a coupling ratio shift, via increased control-gate-to-floating-gate capacitance for reduced dielectric thickness — was previewed quantitatively in Chapter 4, Part 2.3, and is the "expected," budgeted consequence of a well-controlled soft-landing step operating within its designed overetch allowance.

### 1.2 Localized Punch-Through

A more severe mode: non-uniformity (across-wafer, or microloading/ARDE-driven per Chapter 12) causes some local regions to experience significantly more overetch exposure than the wafer average, to the point that local ONO thickness is reduced well beyond the "expected" uniform-thinning budget — in the most severe case, to local complete removal ("punch-through") exposing the floating gate polysilicon beneath. Punch-through is qualitatively different from uniform thinning: it is not a shift in an electrical distribution's mean, but a localized, often binary failure (a cell or group of cells with catastrophically altered, rather than merely shifted, coupling ratio and likely direct electrical leakage between control gate and floating gate).

### 1.3 Sub-Threshold Trap Generation

The most subtle damage mode, connecting directly to the ion energy physics developed in Chapter 8: even without measurable physical thickness loss, ion bombardment at energies below the gross-removal threshold but above a lower trap-generation threshold can create defect states (dangling bonds, trapped charge sites) within the ONO dielectric or at its interfaces, without punching through or even substantially thinning the film. These defect states do not necessarily shift coupling ratio measurably at wafer-level electrical test, but can degrade the dielectric's long-term charge retention and leakage characteristics — a failure mode whose electrical signature is delayed and retrospective in a manner directly analogous to the tunnel oxide damage story the companion volume develops for the bottom of the stack (its Chapter 13).

---

## Part 2: Quantitative Coupling Ratio Degradation

### 2.1 Revisiting the Capacitive Divider

As introduced in Chapter 4, coupling ratio depends on the ratio of control-gate-to-floating-gate capacitance ($C_{CG}$) to total floating gate node capacitance. For a parallel-plate approximation, $C_{CG} \propto \varepsilon_{ONO}/t_{ONO}$, where $t_{ONO}$ is ONO physical (or effective oxide) thickness. Uniform thinning that reduces $t_{ONO}$ by some fraction $\Delta t/t$ increases $C_{CG}$ by approximately the same fractional amount for small perturbations, directly raising coupling ratio by a correlated, predictable fraction — the basis for treating uniform thinning as a budgeted, manageable process variable rather than a binary defect.

### 2.2 Why Punch-Through Breaks This Linear Approximation

The capacitive-divider relationship in Part 2.1 assumes a continuous dielectric of some finite, if reduced, thickness. Punch-through removes this assumption entirely for affected cells: with no remaining ONO dielectric locally, the "capacitance" at the affected location is no longer a well-behaved large value following from a thin but finite dielectric — it approaches a direct conductive short between control gate and floating gate, collapsing the floating gate's isolation (recall from the companion volume, Chapter 1, that the floating gate's entire function depends on being a fully isolated conductor) and producing a cell that cannot reliably store charge at all, rather than a cell with merely shifted Vt or coupling ratio.

### 2.3 Mapping Damage Mode to Required Process Response

| Damage Mode | Electrical Signature | Required Process Response |
|-------------|------------------------|-------------------------------|
| Uniform thinning | Small, wafer-wide coupling ratio shift, predictable from overetch time | Budget management: keep within the designed allowance (Chapter 7, Part 3.1) |
| Localized punch-through | Catastrophic, spatially localized cell failure | Root-cause non-uniformity source (Chapter 12) and reduce overetch time/improve selectivity margin |
| Sub-threshold trap generation | Delayed retention/endurance signal, not visible at wafer sort | Ion energy reduction at the margin (Chapter 8), validated through accelerated reliability testing, not electrical test alone |

This table is the chapter's central practical contribution: three damage modes that might otherwise be lumped together as "ONO damage" actually require three distinct process diagnostic and corrective approaches, and conflating them risks applying the wrong fix (for example, tightening overetch time budget in response to a trap-generation signal that is actually an ion-energy problem, not an overetch-duration problem).

---

## Part 3: Detection Strategy Implications

### 3.1 Why Electrical Test Alone Is Insufficient

Wafer-level electrical test reliably detects uniform thinning (via coupling ratio measurement across a representative cell population) and gross punch-through (via direct leakage or functional failure at affected locations), but, consistent with Part 1.3, does not reliably detect sub-threshold trap generation, which requires accelerated stress testing (elevated temperature/voltage retention bake, cycling endurance testing) to reveal — testing that, by its nature, occurs on a sampled, delayed basis rather than as part of routine wafer sort.

### 3.2 Connection to the Yield Learning Loop

This detection asymmetry is precisely why Chapter 16 treats statistical process control of etch-stage and immediate post-etch metrics as the primary leading indicator for trap-generation-type damage, rather than relying on retention/endurance qualification data, which arrives too late in the production timeline to prevent a large volume of potentially affected product from being manufactured before a problem is identified.

---

## Chapter Summary

- ONO interface damage spans three distinct modes — uniform thinning, localized punch-through, and sub-threshold trap generation — with different severities, different electrical signatures, and different required process responses
- Uniform thinning follows a predictable, roughly linear coupling-ratio-shift relationship with overetch time, making it a manageable, budgeted process variable
- Punch-through breaks this linear relationship entirely, collapsing floating gate isolation and producing catastrophic, spatially localized cell failure rather than a shifted electrical distribution
- Sub-threshold trap generation is the most subtle mode, connecting directly to ion energy choices (Chapter 8), and is not reliably detected by routine wafer-level electrical test, requiring accelerated reliability testing instead
- This damage-mode taxonomy directly informs the yield learning and statistical process control strategy developed in Chapter 16

## Study Questions

1. Explain why uniform ONO thinning is described as a "budgeted" process variable, while punch-through is described as a qualitatively different, binary failure mode.
2. Using the parallel-plate capacitive divider relationship, explain why punch-through "breaks" the linear approximation that uniform thinning follows.
3. Why can sub-threshold trap generation occur without a measurable coupling ratio shift at wafer-level electrical test, and what kind of testing is required to detect it?
4. Why does conflating these three damage modes risk applying an incorrect process correction, and give a specific example of a mismatched fix.

---

[← Chapter 12](12-microloading-arde-array-periphery.md) · [Index](../INDEX.md) · [Next: Chapter 14 →](14-endpoint-detection-multilayer.md)
