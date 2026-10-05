# Chapter 7: Control Gate Polysilicon Main Etch & Soft-Landing on ONO

## Executive Summary

This chapter addresses the step this book's Preface identifies as the mirror image of the companion volume's tunnel-oxide stopping problem: etching control gate polysilicon to completion, uniformly across a full wafer, while landing cleanly on top of the ONO interpoly dielectric without meaningfully damaging or punching through it. We develop the main-etch/soft-landing two-step recipe structure, the selectivity targets that govern the soft-landing step specifically, and the overetch budget logic that balances complete polysilicon clearing against ONO preservation. This chapter's soft-landing treatment is deliberately the control-gate-side counterpart to — not a repetition of — the companion volume's tunnel oxide landing discussion; Chapter 13 of this book develops the damage mechanisms this step must avoid.

---

## Part 1: Main Etch Objectives

### 1.1 Profile Priority During Bulk Removal

With the silicide cap already removed and the chemistry transitioned (Chapter 6), the control gate polysilicon main etch's first objective is straightforward: remove the bulk of the 60–100nm polysilicon thickness as quickly and as anisotropically as possible, using a chlorine- and/or bromine-based chemistry (consistent with the general halogen etch framework introduced for floating gate polysilicon in the companion volume, adapted here for control gate-specific profile and selectivity targets). Because this step does not yet need to protect a nearby dielectric interface, it can run at higher power and etch rate than the soft-landing step that follows, prioritizing throughput and bulk profile quality over the fine selectivity control the final nanometers of polysilicon will require.

### 1.2 Why This Step Carries Outsized Profile Responsibility

As the thickest single polysilicon layer in the stack, any sidewall angle error, bowing, or micro-roughness introduced during main etch is inherited by the soft-landing step beneath it, which has progressively less remaining film thickness — and therefore less remaining opportunity — to correct an upstream profile error before reaching ONO. This is the same profile-inheritance logic the companion volume applies to its own control gate main etch discussion (its Chapter 6), restated here because it is this book's own main etch, not an upstream step belonging to a different etch, that must get this right.

---

## Part 2: The Soft-Landing Transition

### 2.1 Why a Second, Distinct Step Is Required

Polysilicon's etch rate and selectivity behavior change qualitatively as the ONO interface is approached, for a specific, well-understood reason: as remaining polysilicon thickness within any given local area approaches zero, local process non-uniformity (across-wafer etch rate variation, pattern-density-driven microloading discussed in Chapter 12) means different regions of the wafer reach the ONO interface at different times within the same overall etch step. A single-step, main-etch-chemistry process run to nominal completion would, in the regions that clear polysilicon earliest, continue etching ONO with a chemistry and power level tuned for polysilicon removal rather than ONO preservation — precisely the failure mode a soft-landing step is designed to prevent.

### 2.2 Soft-Landing Chemistry and Power Adjustments

| Parameter | Main Etch | Soft-Landing Step |
|-----------|-----------|----------------------|
| **RF bias power** | Higher (prioritizes etch rate) | Lower (reduces ion energy, protecting ONO on early-clearing regions) |
| **Chemistry selectivity to oxide/ONO** | Moderate (not yet critical) | High (specifically tuned polysilicon:ONO selectivity, often 20:1 or higher as a target ratio) |
| **Endpoint strategy** | Time-based or coarse optical signal | Fine-grained endpoint detection (Chapter 14), often combined with a fixed overetch time budget |

The transition from main etch to soft-landing is typically triggered by endpoint detection signaling that the majority of the wafer has reached, or is approaching, the polysilicon/ONO interface (Chapter 14 develops this signal in detail), after which the process switches to lower-power, higher-selectivity chemistry for a fixed remaining time budget calibrated to clear the slowest-etching regions of the wafer with acceptable ONO consumption in the fastest-etching regions.

### 2.3 The Overetch Budget as a Designed Compromise

Because across-wafer and pattern-density-driven etch rate non-uniformity (Chapter 12) is never fully eliminated, some overetch time — continued plasma exposure after the nominal polysilicon clear point in the fastest-etching regions — is unavoidable if the slowest-etching regions are to be reliably cleared. The soft-landing step's selectivity and power targets exist specifically to make a given overetch time budget tolerable: a highly selective, low-power soft-landing chemistry can sustain a longer overetch time with acceptable ONO consumption than main-etch chemistry could, which is why the soft-landing step is best understood not as "a brief final step" but as the process module that makes the entire wafer's non-uniformity tolerable at all.

---

## Part 3: Selectivity Targets in Context

### 3.1 Why 20:1 (or Higher) Is a Representative Target, Not an Arbitrary One

A representative soft-landing selectivity target of 20:1 or higher (polysilicon etch rate relative to ONO etch rate) is sized specifically against the overetch time budget it must support: if across-wafer non-uniformity requires, illustratively, an overetch time equivalent to 20% of total polysilicon main etch time to ensure full clearing everywhere, a 20:1 selectivity limits ONO consumption during that overetch window to roughly 1% of the main-etch-equivalent material removal rate applied to ONO — a loss budget that, translated into physical ONO thickness (10–15nm oxide equivalent, Chapter 2), is intended to remain small relative to the thickness tolerance Chapter 13's coupling-ratio-shift analysis treats as acceptable.

### 3.2 Why Selectivity Alone Does Not Fully Solve the Problem

High polysilicon:ONO selectivity reduces, but does not eliminate, ONO consumption during overetch — some finite material removal rate against ONO remains even at favorable selectivity ratios, and that remaining removal rate, combined with real (non-zero) across-wafer non-uniformity, is precisely the physical mechanism Chapter 13 analyzes as a source of spatially-correlated coupling ratio shift. This chapter establishes the process design response (selectivity-tuned soft-landing chemistry); Chapter 13 analyzes what happens when that response is imperfect, as it always is to some degree in a production process.

---

## Chapter Summary

- Control gate polysilicon main etch prioritizes throughput and bulk profile at higher power, carrying outsized responsibility for overall stack profile quality as the thickest single polysilicon layer
- A distinct soft-landing step, with lower power and higher polysilicon:ONO selectivity, is required because across-wafer non-uniformity means different regions reach the ONO interface at different times within a single nominal etch step
- The overetch budget is a designed compromise: some continued etch exposure in early-clearing regions is unavoidable, and soft-landing chemistry exists specifically to make that unavoidable overetch tolerable
- Representative selectivity targets (20:1 or higher) are sized against the overetch time budget non-uniformity requires, translating directly into an expected ONO consumption loss budget
- Selectivity reduces but does not eliminate ONO consumption during overetch — the residual effect is the subject of Chapter 13's coupling-ratio-shift analysis

## Study Questions

1. Why does the control gate polysilicon main etch carry "outsized profile responsibility" relative to its position in the overall stack sequence?
2. Explain, in your own words, why a single-step etch process (without a distinct soft-landing transition) would inevitably over-etch ONO in some regions of a non-uniform wafer.
3. How is a representative soft-landing selectivity target (e.g., 20:1) derived from an assumed overetch time budget, and what does this imply about the relationship between non-uniformity and required selectivity?
4. Why does this chapter describe selectivity as reducing, rather than eliminating, the ONO consumption problem — and what chapter addresses the consequences of that residual effect?

---

[← Chapter 6](06-silicide-polycide-etch-chemistry.md) · [Index](../INDEX.md) · [Next: Chapter 8 →](08-rf-bias-ono-interface.md)
