# Chapter 11: Polysilicon/Silicide Stringers, Footing, and Gate-to-Gate Bridging at the Control Gate Level

## Executive Summary

This chapter catalogs the three defect mechanisms most specific to control gate etch's multi-material, dual-pattern-density nature: stringers (unwanted residual conductive material left at topography steps), footing (incomplete etch at the base of a gate sidewall), and gate-to-gate bridging (an unintended conductive path between adjacent word lines, whether from stringers, incomplete silicide removal, or profile defects). Each defect is examined for its physical formation mechanism, its connection to process decisions made in Part II, and its electrical signature — since, as Chapter 1 argued, control gate defects are often detected through their effect on word line resistance or Vt distribution rather than through direct visual inspection alone.

---

## Part 1: Stringers

### 1.1 Formation Mechanism

Stringers form at topography steps — locations where the underlying surface has a height discontinuity, such as the edge of an active area, an STI boundary, or a step in the hard mask pattern — because conformal film deposition (both the control gate polysilicon and, where applicable, the silicide cap) deposits extra material thickness at the base of such steps (a sidewall deposition effect inherent to conformal CVD processes), and standard top-down anisotropic etch, calibrated to clear the nominal (flat-field) film thickness, does not fully clear this locally thicker material at the step base, leaving a residual "stringer" of conductive material.

### 1.2 Why Stringers Are Specifically Dangerous at the Control Gate Level

A polysilicon or silicide stringer, if electrically continuous and positioned between features that must remain electrically isolated (e.g., between adjacent word lines, or between a word line and an adjacent peripheral structure), creates an unintended conductive path — a direct short or a high-resistance leakage path, depending on stringer continuity and cross-section. Because control gate stringers form from the same conductive materials (silicide, heavily doped polysilicon) that the word line itself depends on for its primary electrical function, a stringer defect is not merely a residue/cleanliness issue — it is a direct, often high-confidence predictor of an electrical short or leakage defect.

### 1.3 Mitigation Strategies

Stringer mitigation typically combines process-level and design-level approaches: increased overetch time specifically targeted at step-edge locations (balanced against the ONO damage concerns of Chapter 13 where steps occur near the array, requiring careful co-optimization), optimized etch chemistry with stronger lateral (though still controlled) etch component specifically to clear step-base material, and, at the design/integration level, topography minimization (planarization steps upstream of control gate deposition) that reduces the step height stringers form at in the first place.

---

## Part 2: Footing

### 2.1 Formation Mechanism

Footing is the opposite profile defect from an idealized vertical sidewall at the base of a gate: rather than a stringer (residual material beyond the intended sidewall), footing is a local widening of the gate's intended profile specifically at its base, typically caused by a combination of ion scattering off the underlying surface (ions reflecting at shallow angles off the ONO or substrate surface and striking the lower sidewall from an oblique angle) and reduced local etch rate at the base due to incomplete byproduct removal in the increasingly confined space as the etch approaches the bottom of the film.

### 2.2 Why Footing Specifically Threatens the Soft-Landing Step

Because footing occurs preferentially at the base of the etched profile, it is specifically a soft-landing-step phenomenon (Chapter 7), occurring exactly where reduced bias power and modified chemistry (Chapter 8) are already creating a more passivation-dependent, less strongly ion-directed etch regime. This means footing risk and the soft-landing step's intentional anisotropy trade-off (Chapter 8, Part 2.3) are mechanistically linked: a soft-landing chemistry/power combination that relies too heavily on passivation without adequate directional etch component can produce footing as an unintended side effect of the very modification made to protect ONO.

### 2.3 Electrical Consequence

Footing locally increases effective gate length at the gate base, which — because the base of the gate is the region closest to the ONO interface and therefore most directly relevant to coupling ratio (Chapter 4, Part 2.2) — can produce a localized coupling ratio and effective channel length anomaly distinct from, and in addition to, the top-CD-based Vt effects discussed in Chapter 10.

---

## Part 3: Gate-to-Gate Bridging

### 3.1 Bridging as a Composite Defect Category

Unlike stringers and footing, which are specific physical formation mechanisms, "bridging" in this book's usage refers to the electrical outcome — an unintended conductive path between adjacent gates — which can result from several distinct root causes already discussed in this and prior chapters: an uncleared stringer (Part 1), incomplete silicide removal at the silicide/polysilicon transition (Chapter 6, Part 2.2), or severe footing/bowing that causes adjacent gate sidewalls to make physical and electrical contact.

### 3.2 Why Root Cause Differentiation Matters

Because bridging's electrical signature (resistance between adjacent word lines falling below an acceptable isolation threshold) is similar regardless of root cause, but the appropriate process correction differs substantially by root cause (stringer mitigation vs. silicide transition timing adjustment vs. soft-landing chemistry rebalancing), production failure analysis for a bridging excursion requires physical (typically cross-sectional, per Chapter 10 Part 3.2) root-cause confirmation before a corrective action is selected — an electrical signature alone is necessary but not sufficient for recipe correction.

### 3.3 Array Pitch Dependence

Consistent with the companion volume's treatment of the analogous floating-gate-level defect, bridging risk at the control gate level is strongly word-line-pitch dependent: a given absolute stringer size or footing magnitude that was electrically irrelevant at relaxed pitch (sufficient gap remaining between adjacent, imperfectly profiled gates) becomes an increasingly probable short as pitch scales down and the nominal gap between adjacent gates shrinks toward the same physical scale as the defect itself. This pitch-dependence is a specific instance of this book's broader scaling argument (Chapter 1, Part 3; developed fully in Chapter 15): defects do not need to get larger to become yield-limiting — shrinking margin accomplishes the same result.

---

## Chapter Summary

- Stringers form from conformal deposition at topography steps and are specifically dangerous at the control gate level because they are composed of the same conductive materials the word line depends on, making them high-confidence predictors of electrical shorts
- Footing, a base-widening profile defect from ion scattering and byproduct removal limitations, is mechanistically linked to the soft-landing step's intentional reduction in ion-directed etch strength (Chapter 8), and produces coupling-ratio-relevant effects because it occurs closest to the ONO interface
- Gate-to-gate bridging is a composite electrical outcome with several distinct possible root causes, requiring physical root-cause confirmation before an appropriate process correction can be selected
- Bridging risk from a fixed-size defect increases as word line pitch scales down, a specific instance of this book's recurring argument that shrinking process margin, not necessarily growing defects, drives yield impact at advanced nodes

## Study Questions

1. Why does conformal film deposition inherently create stringer risk at topography steps, and why is increased overetch an imperfect (trade-off-laden) solution?
2. Explain the mechanistic link between the soft-landing step's reduced ion energy (Chapter 8) and footing risk specifically at the base of the control gate profile.
3. Why is an electrical bridging signature alone insufficient to select an appropriate process correction, and what metrology approach from Chapter 10 resolves this ambiguity?
4. Explain, using the stringer/bridging relationship as a specific example, why "the defect doesn't need to get bigger to become yield-limiting" as word line pitch scales down.

---

[← Chapter 10](10-cd-control-gate-length.md) · [Index](../INDEX.md) · [Next: Chapter 12 →](12-microloading-arde-array-periphery.md)
