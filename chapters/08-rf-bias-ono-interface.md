# Chapter 8: RF Bias and Ion Energy Management Near the ONO Interface

## Executive Summary

Chapter 7 established that the soft-landing step uses lower RF bias power than the main etch, and attributed this to selectivity and ONO protection. This chapter develops the ion energy physics behind that design choice in detail: how RF bias power sets ion energy at the wafer surface, how ion energy governs both etch mechanism (chemical vs. ion-assisted) and sputtering damage risk, and why the specific energy range chosen for soft-landing represents a deliberate balance between maintaining adequate anisotropy and avoiding ONO damage mechanisms that Chapter 13 catalogs in full. This chapter also addresses profile control implications of reduced bias power, since lowering ion energy for ONO protection is not a free parameter change — it interacts with the same profile objectives Chapter 7 established for the main etch.

---

## Part 1: RF Bias Power and Ion Energy

### 1.1 The Sheath Acceleration Mechanism

In a capacitively or inductively coupled plasma etch system, RF bias power applied to the wafer electrode (or, in some chamber architectures, a separate bias supply independent of the plasma-generating source) controls the DC self-bias voltage that develops across the plasma sheath adjacent to the wafer. Ions crossing this sheath are accelerated toward the wafer surface, arriving with kinetic energy approximately proportional to the sheath voltage — meaning RF bias power is, to first order, a direct control knob on the energy with which ions strike the wafer surface, independent of ion flux (which is set primarily by source power in systems with separate source and bias power supplies).

### 1.2 Why Ion Energy Matters Independent of Ion Flux

Two etch control variables — ion flux (how many ions arrive per unit time) and ion energy (how much kinetic energy each ion carries) — affect etch outcomes through different mechanisms. Flux primarily affects etch rate (more ions, more ion-assisted reaction events per unit time, roughly proportional etch rate increase). Energy affects both etch rate (above a chemistry-dependent threshold, higher-energy ions more effectively enhance the chemical reaction rate at the point of impact) and, critically for this chapter, the risk of direct physical damage mechanisms — sputtering, lattice displacement, and charge trapping — that become significant only above certain energy thresholds specific to the material being bombarded.

---

## Part 2: Why Lower Bias Power Specifically Protects ONO

### 2.1 Damage Threshold Behavior

ONO, as a thin dielectric stack (10–15nm oxide equivalent), is susceptible to ion-induced damage mechanisms — bond breaking, trap state generation, and in sufficiently energetic cases, physical sputtering of the dielectric material itself — that exhibit threshold-like behavior with respect to ion energy: below some chemistry- and material-dependent energy, damage accumulation is slow enough to be manageable within the soft-landing step's limited overetch time budget (Chapter 7); above that threshold, damage accumulates fast enough to produce measurable electrical consequences (Chapter 13) within the same overetch window.

### 2.2 Why This Threshold Argument Justifies a Distinct (Not Merely Reduced) Power Setting

This is why the soft-landing step's RF bias power is best understood not as "somewhat lower than main etch" but as deliberately targeted to sit below the ONO damage threshold with margin, even though this sacrifices some etch rate and, potentially, some polysilicon etch anisotropy relative to main-etch conditions. The soft-landing step's selectivity target (Chapter 7, Part 3) and its bias power target are therefore not independent process parameters — they are jointly tuned, because selectivity itself (polysilicon etch rate relative to ONO etch/damage rate) is partly a consequence of operating below the energy threshold where ONO becomes significantly more vulnerable.

### 2.3 The Energy/Anisotropy Trade-off at Reduced Bias Power

Lower ion energy, by reducing the strength of the directional, ion-assisted etch mechanism relative to the (comparatively isotropic) spontaneous chemical etch component (a mechanism balance introduced for control gate etch chemistry generally in Chapter 6, Part 1.2, following the companion volume's treatment of the same physics for floating gate etch), risks some loss of anisotropy during the soft-landing step specifically. Production recipes manage this trade-off by relying on sidewall passivation (oxygen or nitrogen-containing chemistry additions, as in main etch chemistry) to suppress lateral chemical attack even as ion-assisted directional etch strength is intentionally reduced — meaning the soft-landing step depends more heavily on passivation-based anisotropy control, relatively speaking, than the main etch step does.

---

## Part 3: Profile Control Through the Transition

### 3.1 Avoiding a Visible Profile Discontinuity

Because main etch and soft-landing operate at different bias power (and therefore different ion energy and anisotropy balance), an abrupt, poorly matched transition between the two steps can produce a visible profile discontinuity at the transition depth — analogous to, though generally less severe than, the silicide/polysilicon transition discontinuity risk discussed in Chapter 6. Production recipes address this with a power ramp (a gradual reduction in bias power over a short transition period, rather than an instantaneous step change) timed to coincide with the endpoint-triggered or time-triggered transition point, smoothing the anisotropy balance change across a short etch depth rather than concentrating it at a single interface.

### 3.2 Interaction With Array/Periphery Pattern Density

Ion flux uniformity across a wafer — and, to a lesser extent, local ion energy, through sheath thickness variations driven by local topography and pattern density — is itself sensitive to the pattern-density effects Chapter 9 and Chapter 12 develop at the chemistry and etch-rate level. This chapter's bias power strategy must therefore be robust not just to across-wafer process uniformity in the abstract, but specifically to the array/periphery pattern density duality that recurs as an organizing concern throughout Part II and Part III of this book.

---

## Chapter Summary

- RF bias power controls DC self-bias voltage and therefore ion energy at the wafer surface, a variable distinct from ion flux and with distinct etch-mechanism and damage consequences
- ONO damage mechanisms exhibit threshold-like behavior with respect to ion energy; the soft-landing step's bias power is deliberately targeted below this threshold with margin, not merely "somewhat reduced" from main etch conditions
- Selectivity and bias power are jointly tuned parameters, not independent ones, because selectivity itself depends partly on operating below the ONO damage energy threshold
- Reduced ion energy risks some anisotropy loss, managed through increased reliance on sidewall passivation chemistry during the soft-landing step specifically
- A gradual bias power ramp at the main-etch/soft-landing transition avoids a visible profile discontinuity, analogous to the chemistry transition risk discussed in Chapter 6

## Study Questions

1. Explain the physical mechanism by which RF bias power controls ion energy at the wafer surface, and why this is distinct from ion flux.
2. Why is it more accurate to describe the soft-landing step's bias power as "targeted below a damage threshold with margin" rather than simply "lower than main etch"?
3. Why are soft-landing selectivity and soft-landing bias power described in this chapter as jointly tuned rather than independent process parameters?
4. What specific chemistry-based mechanism compensates for the anisotropy loss risked by operating the soft-landing step at reduced ion energy?

---

[← Chapter 7](07-polysilicon-main-etch-ono-landing.md) · [Index](../INDEX.md) · [Next: Chapter 9 →](09-array-periphery-uniformity.md)
