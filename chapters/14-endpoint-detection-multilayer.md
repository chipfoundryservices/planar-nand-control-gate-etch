# Chapter 14: Endpoint Detection for Multi-Layer Silicide/Polysilicon/ONO Transitions

## Executive Summary

Every process transition this book has developed — silicide-to-polysilicon chemistry change (Chapter 6), main-etch-to-soft-landing power and chemistry change (Chapters 7–8), and the final soft-landing termination point — depends on reliably knowing *when* that transition should occur. This chapter develops the endpoint detection methods used to make that determination: optical emission spectroscopy (OES) as the dominant technique, the specific spectral signatures each material transition produces, and the soft-landing-specific endpoint strategies that must detect a transition occurring in some wafer regions while deliberately continuing to etch others, consistent with the across-wafer non-uniformity picture developed in Chapter 12.

---

## Part 1: Optical Emission Spectroscopy Fundamentals

### 1.1 The Basic Principle

Plasma etch byproducts, and residual reactant species, emit characteristic optical wavelengths as excited atomic and molecular species in the plasma relax to lower energy states. Optical emission spectroscopy (OES) monitors specific wavelengths (or a broader spectral range) throughout the etch process; because byproduct composition changes as the etch front transitions from one material to another (e.g., from tungsten-silicon byproducts to pure silicon byproducts as the silicide cap clears), characteristic intensity changes at wavelengths associated with the departing or arriving material's byproducts signal that a material transition is occurring in real time.

### 1.2 Material-Specific Signatures Relevant to This Stack

| Transition | Monitored Species (Representative) | Signal Behavior at Transition |
|------------|---------------------------------------|-------------------------------|
| **Silicide cap clearing (to polysilicon)** | W-containing byproduct emission (e.g., WF or WCl-associated wavelengths, chemistry-dependent) | Signal intensity falls as tungsten-containing byproduct generation ceases |
| **Polysilicon clearing (to ONO)** | Si-containing byproduct emission (e.g., SiCl or SiF-associated wavelengths) | Signal intensity falls as silicon byproduct generation ceases and exposed area transitions to oxide/nitride |
| **ONO exposure (soft-landing confirmation)** | Oxide- or nitrogen-associated byproduct emission, depending on chemistry | Signal rise, confirming the majority of monitored wafer area has reached ONO |

### 1.3 Why Signal Interpretation Is a Statistical, Not Binary, Exercise

Because OES signal is collected from some spatially averaged or sampled region of the plasma (not a per-die or per-feature measurement), and because, per Chapter 12, different pattern-density regions clear at different times, the observed signal transition is itself a weighted average of many local transition events occurring at slightly different times. Endpoint algorithms therefore typically define a transition trigger based on a signal derivative threshold (rate of change exceeding some criterion) or a percentage-of-maximum-signal-change criterion, rather than waiting for the signal to reach a fully stable new plateau — a design choice that trades some risk of early or late triggering against the practical need to make a timely process decision from inherently averaged, noisy data.

---

## Part 2: Endpoint Strategy for Each Transition in This Book's Sequence

### 2.1 Silicide-to-Polysilicon Transition Endpoint

This transition's endpoint signal (Part 1.2, row 1) directly informs the chemistry-switch timing risk discussed in Chapter 6, Part 2: triggering the switch too early (while W-signal is still present but declining) risks leaving tungsten-rich residue, while triggering too late risks the profile discontinuity Chapter 6 describes. Production recipes typically use a derivative-based trigger at a calibrated point on the declining W-signal curve, validated against cross-sectional metrology (Chapter 10, Part 3.2) during process qualification to confirm the chosen trigger point does not systematically favor one risk over the other.

### 2.2 Main-Etch-to-Soft-Landing Transition Endpoint

This transition (Chapters 7–8) uses the Si-signal decline (Part 1.2, row 2) as its primary trigger, but with an important strategic difference from the silicide transition: because the soft-landing step's entire purpose is accommodating the *remaining* non-uniformity after this trigger point, the trigger here is intentionally set conservatively early — while a meaningful fraction of the wafer still has measurable remaining polysilicon — to ensure the lower-power, higher-selectivity soft-landing chemistry is in effect before the fastest-clearing regions reach ONO, rather than attempting to time a single instant that is simultaneously correct for the fastest- and slowest-clearing regions, which Chapter 12 establishes is not achievable for a single global signal.

### 2.3 Soft-Landing Termination Endpoint

The final termination point (ending the etch entirely) combines the ONO-exposure signal rise (Part 1.2, row 3) with the fixed, pre-calibrated overetch time budget established in Chapter 7, Part 3.1: the ONO-signal rise confirms that the majority of the wafer has reached the landing interface, and the process then continues for the calibrated overetch duration (rather than terminating immediately at signal rise) to ensure the slowest-clearing regions — identified in Chapter 12 as specifically the dense array regions under most chemistry choices — also fully clear before the process ends.

---

## Part 3: Limitations and Complementary Approaches

### 3.1 Why Array/Periphery Signal Weighting Matters

Chapter 9 noted that a single global endpoint signal may represent array and periphery regions unequally, depending on their relative contribution to the total monitored plasma volume's optical signal (itself related to their relative exposed etch-front area, not necessarily their relative die area). Advanced endpoint systems can address this partially through spatially resolved optical monitoring (collecting signal from multiple, physically distinct viewports or using imaging-based rather than single-point collection), allowing array-specific and periphery-specific signal trends to be tracked separately rather than combined into one ambiguous average — directly mitigating the concern raised in Chapter 9, Part 3.1.

### 3.2 Electrical and Capacitive Endpoint Supplements

Some production tools supplement OES with RF impedance or electrical characteristic monitoring (changes in plasma electrical properties as the exposed material composition changes affect achievable impedance match conditions in ways that can provide an independent, non-optical transition signal), providing cross-validation against OES-based triggers, particularly valuable in process regimes where optical signal-to-noise is marginal (for example, at very advanced, low-pattern-density-area nodes where total exposed etch-front area, and therefore total byproduct generation rate, is itself reduced).

---

## Chapter Summary

- Optical emission spectroscopy monitors characteristic byproduct wavelengths to detect material transitions in real time, with each transition in this book's etch sequence (silicide/polysilicon, polysilicon/ONO) having a distinct representative signature
- Signal interpretation is inherently a statistical exercise over spatially averaged, noisy data, not a binary per-feature measurement, requiring derivative- or percentage-based trigger criteria rather than waiting for full signal stabilization
- Each transition in this book's process sequence uses a distinct endpoint strategy tuned to that transition's specific risk profile: calibrated-point triggering for silicide/polysilicon, intentionally conservative early triggering for main-etch/soft-landing, and signal-rise-plus-fixed-overetch for final termination
- Spatially resolved optical monitoring and electrical/RF impedance supplements address the array/periphery signal-weighting ambiguity raised in Chapter 9 and provide cross-validation where optical signal-to-noise is marginal

## Study Questions

1. Why must endpoint signal interpretation use a derivative- or percentage-based trigger criterion rather than waiting for the signal to reach a stable new plateau?
2. Explain why the main-etch-to-soft-landing transition is deliberately triggered "conservatively early," in contrast to the silicide/polysilicon transition's calibrated-point approach.
3. Why does the final soft-landing termination combine a signal-rise trigger with a separate, fixed overetch time budget, rather than using either criterion alone?
4. How does spatially resolved optical monitoring address the array/periphery endpoint ambiguity raised in Chapter 9, and why might imaging-based collection be preferable to a single-point detector for this purpose?

---

[← Chapter 13](13-ono-interface-damage.md) · [Index](../INDEX.md) · [Next: Chapter 15 →](15-word-line-resistance-scaling.md)
