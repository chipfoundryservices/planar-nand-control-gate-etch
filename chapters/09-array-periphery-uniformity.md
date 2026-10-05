# Chapter 9: Array/Periphery Etch Uniformity: Pattern Density and Dual-Pitch Recipe Design

## Executive Summary

Every process design decision developed in Chapters 5 through 8 — hard mask selection, silicide etch chemistry, soft-landing selectivity, bias power — must perform acceptably not just across a single pattern density, but across the full range of pattern densities present on a real production wafer: a densely packed memory array and comparatively isolated peripheral logic gates, patterned by the same control gate etch sequence. This chapter develops why these two regimes etch differently under nominally identical plasma conditions, what recipe design strategies address the resulting non-uniformity, and why this book treats array/periphery duality as a first-order constraint threaded through Part II rather than a localized topic confined to this one chapter.

---

## Part 1: Why Array and Periphery Etch Differently

### 1.1 Reactant Depletion and Byproduct Removal

Plasma etch rate depends on local reactant (radical and ion) concentration at the wafer surface and on the rate at which volatile byproducts are removed from the local etch front. In densely patterned regions (the memory array, with closely spaced word lines), both effects are locally constrained: reactants are consumed by a larger total exposed etch-front area per unit wafer area, and byproducts must diffuse out through narrower, more restricted spaces between features before being swept away by bulk gas flow. In isolated or sparsely patterned regions (peripheral logic), reactant supply and byproduct removal both proceed with less local restriction, generally yielding a different (often higher) local etch rate under otherwise identical process conditions.

### 1.2 Microloading, Formally Introduced

This phenomenon — etch rate varying with local pattern density under globally identical process conditions — is termed microloading, and is developed in full physical and quantitative detail in Chapter 12, including its specific interaction with aspect ratio dependent etching (ARDE) effects in the control gate context. This chapter introduces microloading only to the extent needed to motivate recipe design strategy; Chapter 12 is the authoritative treatment of the underlying physics.

### 1.3 Why Control Gate Etch Is Particularly Exposed to This Effect

Unlike some etch modules confined entirely to one pattern-density regime, control gate etch — because the same film stack serves as both memory array word lines and peripheral logic gate conductors (Chapter 1) — is patterned in a single process sequence that must span the full pattern density range present on the die. This is a stronger version of the array/periphery duality challenge than many single-purpose logic etch processes face, because peripheral control gate features (logic gate conductors) are not merely "less dense" versions of the same structure as array word lines — they can differ in gate length, spacing, and local topography in ways that compound pattern-density effects with genuine geometric differences.

---

## Part 2: Recipe Design Strategies

### 2.1 Chemistry and Power Tuning for Dual-Regime Robustness

Because microloading sensitivity differs by chemistry (Chapter 6 noted this in passing for the silicide cap etch's fluorine-fraction trade-off; Chapter 12 develops it quantitatively for the full stack), recipe development for control gate etch explicitly evaluates candidate chemistries not only for their single-regime (e.g., array-only) performance, but for the *difference* in etch rate and profile outcome between array and periphery regimes under the same chemistry and power settings. A chemistry that performs excellently in isolation in the array, but produces an unacceptably large array/periphery etch rate differential, is not a viable production candidate even if its array-only metrics look superior to an alternative.

### 2.2 Overetch Budget Implications

The soft-landing overetch budget (Chapter 7) must be sized to accommodate the *slowest*-clearing regime across the full array/periphery pattern density range — if periphery clears polysilicon measurably later than array (or vice versa, depending on which direction microloading runs for the specific chemistry in use), the overetch time budget must extend to cover that slower-clearing regime, which directly increases ONO exposure time in the regime that cleared first, reinforcing the selectivity-overetch coupling (Chapter 7, Part 3) across an additional dimension (pattern density) beyond simple across-wafer non-uniformity.

### 2.3 Pattern-Density-Aware Mask Design

Some microloading mitigation occurs upstream of the etch process itself, at the mask design level: dummy fill structures (non-functional patterned features added specifically to make local pattern density more uniform across array and periphery regions) are a standard integration technique to reduce the *magnitude* of the pattern-density difference the etch process must otherwise tolerate. This book treats dummy fill strategy as an integration-level mitigation that reduces, but does not eliminate, the etch recipe design burden developed in this chapter — production control gate etch recipes are designed assuming dummy fill is already in place, not as a substitute for etch-level robustness.

---

## Part 3: Endpoint and Process Control Implications

### 3.1 Why a Single Endpoint Signal May Not Represent the Whole Wafer

Endpoint detection (developed fully in Chapter 14) typically derives its signal from an optically or electrically averaged measurement across some sampled region of the wafer, or from a specific monitored location. If array and periphery regions clear at measurably different times, a single global endpoint signal, averaged across both regimes, risks triggering the main-etch-to-soft-landing transition (or the final overetch termination) at a time that is well-matched to neither regime individually — acceptable for one, suboptimal for the other. Chapter 14 develops specific endpoint strategies (including monitoring approaches that weight or separately track array and periphery signal contributions) that address this concern directly.

### 3.2 Statistical Process Control Across Both Regimes

Production process control plans for control gate etch sample metrology (CD, profile, and where feasible, electrical test proxies for sheet resistance and bridging) from both array and periphery regions specifically, rather than treating one regime as fully representative of the other. This is a direct consequence of this chapter's central argument: because the two regimes etch differently under the same process conditions, process health monitoring that samples only one regime can miss drift that is occurring in, or specific to, the other.

---

## Chapter Summary

- Array and peripheral logic regions etch at different rates under identical process conditions, due to reactant depletion and byproduct removal differences driven by local pattern density (microloading, developed fully in Chapter 12)
- Control gate etch is particularly exposed to this effect because the same film stack and etch sequence must pattern both regimes, which can also differ in genuine geometry (not just density)
- Recipe development must evaluate chemistry and power settings for array/periphery differential, not just single-regime performance, and overetch budgets must accommodate the slower-clearing regime
- Dummy fill is an integration-level mitigation that reduces, but does not eliminate, the etch recipe design burden this chapter addresses
- Endpoint detection and statistical process control both require explicit attention to both regimes, since a single averaged or single-regime signal can misrepresent overall wafer process health

## Study Questions

1. Explain, in terms of reactant depletion and byproduct removal, why densely patterned array regions tend to etch differently from isolated peripheral regions under identical plasma conditions.
2. Why is control gate etch described as "particularly exposed" to array/periphery pattern density effects compared to some other, single-purpose etch modules?
3. How does an array/periphery etch rate differential interact with, and potentially worsen, the selectivity-overetch coupling established in Chapter 7?
4. Why is dummy fill described as reducing, rather than eliminating, the etch recipe design burden this chapter addresses?

---

[← Chapter 8](08-rf-bias-ono-interface.md) · [Index](../INDEX.md) · [Next: Chapter 10 →](10-cd-control-gate-length.md)
