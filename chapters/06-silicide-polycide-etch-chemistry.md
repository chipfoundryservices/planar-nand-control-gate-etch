# Chapter 6: Silicide/Polycide Cap Etch Chemistry: WSix and Refractory Metal Silicide Systems

## Executive Summary

Etching tungsten silicide cleanly — without leaving conductive residue, without attacking the polysilicon beneath it prematurely, and without producing byproducts that redeposit elsewhere in the chamber — requires a different chemistry emphasis than polysilicon etch alone, because it must simultaneously volatilize both a refractory metal (tungsten) and silicon from the same film. This chapter develops fluorine- and chlorine-based silicide etch chemistry, explains why fluorine plays a role in control gate cap etch that has no direct analogue in the companion volume's floating gate polysilicon etch chemistry, and treats the silicide/polysilicon transition as the deliberate, managed chemistry-switch event that Chapter 2 previewed.

---

## Part 1: Why Silicide Etch Needs a Different Chemistry Emphasis

### 1.1 The Two-Element Volatilization Problem

Tungsten silicide (WSix) etch must produce volatile byproducts from both its constituent elements: tungsten and silicon. Silicon forms volatile halides readily in standard chlorine- or bromine-based chemistry (SiCl₄, SiBr₄, consistent with polysilicon etch chemistry). Tungsten's halide volatility is less favorable in chlorine/bromine chemistry alone — tungsten chlorides and bromides have lower vapor pressure at typical process temperatures than their silicon counterparts, creating a risk that silicon etches preferentially, leaving a tungsten-enriched, poorly volatile residue layer behind.

### 1.2 The Role of Fluorine

Fluorine-based chemistry (typically introduced via SF₆, NF₃, or CF₄ as an additive to a primarily chlorine-based process) addresses this asymmetry directly: tungsten fluorides (notably WF₆) have substantially higher vapor pressure than tungsten chlorides or bromides, making fluorine addition an effective tool for ensuring tungsten volatilization keeps pace with silicon volatilization during cap etch. This is a chemistry consideration specific to the silicide cap step and does not carry over to the polysilicon main etch (Chapter 7), where fluorine's higher spontaneous (non-ion-assisted) silicon etch rate would work against the anisotropy and selectivity objectives that step requires — a point developed further in Part 3 of this chapter.

### 1.3 Representative Chemistry Composition

| Gas | Role in Silicide Cap Etch |
|-----|------------------------------|
| **Cl₂** | Primary silicon-component etchant; also contributes to tungsten etch via WClₓ byproducts, though less volatile than fluoride equivalents |
| **SF₆ or NF₃ (minority addition)** | Enhances tungsten volatilization via WF₆ formation; balances etch rate between Si and W components of the silicide |
| **O₂ or N₂ (minority addition)** | Sidewall passivation, moderating fluorine's isotropic tendency and preserving profile control |
| **Ar (dilution)** | Ion flux tuning, dilution of reactive species concentration |

Production recipes balance the fluorine fraction carefully: too little, and tungsten-rich residue risk increases; too much, and the chemistry's inherently more isotropic, higher spontaneous etch rate behavior (fluorine radicals react with silicon-containing materials with less selectivity to ion bombardment than chlorine or bromine radicals) degrades sidewall profile and risks undercutting the hard mask.

---

## Part 2: Transition Management at the Silicide/Polysilicon Interface

### 2.1 Why a Deliberate Transition Is Required

The fluorine-containing chemistry optimized for silicide cap removal is not the correct chemistry for the polysilicon main etch beneath it — it etches polysilicon with less anisotropy and, over the comparatively large polysilicon thickness (60–100nm, versus a 50–100nm cap that is typically thinner relative to the aggressive etch rate a cap-optimized chemistry delivers), would produce unacceptable profile degradation if left unchanged for the main etch. Production recipes therefore incorporate a deliberate chemistry step change at, or just before, the silicide/polysilicon interface, timed via endpoint detection (Chapter 14) or pre-characterized time-based transition.

### 2.2 Residue Risk at the Transition

If the transition occurs too early (while silicide remains), subsequent polysilicon-optimized chemistry — not tuned for tungsten volatilization — can leave a thin, poorly volatile tungsten-rich residue layer at the interface. This residue is electrically significant even at thicknesses too thin to be reliably caught by inline inspection: a continuous or near-continuous residual conductive film at the base of the silicide cap can create unintended lateral conduction paths between adjacent word lines, a defect mechanism Chapter 11 develops as a specific class of bridging defect distinct from polysilicon stringers.

### 2.3 Residue Risk From a Transition That Occurs Too Late

Conversely, a transition that occurs after etch has already begun removing polysilicon with cap-optimized (fluorine-containing) chemistry risks the profile degradation described in Part 2.1 — excess lateral etch at the top of the polysilicon film, producing a profile discontinuity (a local widening or "necking" at the silicide/polysilicon boundary) that is difficult to correct in the main etch step that follows, and that becomes a measurable contributor to line edge roughness statistics (Chapter 10) specifically localized to that one interface in the stack.

---

## Part 3: Selectivity Objectives and Hard Mask Interaction

### 3.1 Selectivity to Hard Mask

The silicide cap etch chemistry must also maintain adequate selectivity to the hard mask material established in Chapter 5. Fluorine-containing chemistry's generally higher reactivity toward silicon-containing materials (including, depending on mask choice, oxide or nitride hard masks) means fluorine fraction must be balanced not only against polysilicon profile concerns (Part 2) but against hard mask erosion concerns — an argument that reinforces Chapter 5's observation that amorphous carbon hard masks, with chemistry largely orthogonal to both chlorine/bromine and fluorine-based halogen chemistry, provide the most comfortable selectivity margin at advanced pitch, where both the silicide cap etch and the polysilicon main etch must be completed without excessive mask consumption.

### 3.2 Why This Step's Process Window Is Comparatively Narrow

Relative to the polysilicon main etch (Chapter 7), the silicide cap etch operates in a narrower practical process window: it must balance tungsten and silicon volatilization (Part 1), transition cleanly to polysilicon-optimized chemistry at the right moment (Part 2), and preserve hard mask integrity under a chemistry more aggressive toward oxide/nitride than the main etch chemistry that follows (Part 3.1). This narrow window is a direct, specific consequence of the decision (Chapter 2) to cap polysilicon with a refractory metal silicide for resistance reasons — the resistance benefit purchased in Chapter 3 is paid for, in part, by this chapter's comparatively demanding chemistry engineering requirement.

---

## Chapter Summary

- Tungsten silicide etch must volatilize both tungsten and silicon; fluorine-containing chemistry additions (SF₆, NF₃) are used specifically to improve tungsten volatilization via WF₆ formation, addressing an asymmetry that pure chlorine/bromine chemistry does not resolve well
- A deliberate chemistry transition at the silicide/polysilicon interface is required because cap-optimized (fluorine-containing) chemistry is not suitable, unmodified, for the polysilicon main etch
- Transitions that occur too early risk tungsten-rich residue (a bridging defect precursor); transitions that occur too late risk profile discontinuities at the interface
- Hard mask selectivity considerations constrain achievable fluorine fraction, reinforcing amorphous carbon's advantage at advanced pitch (Chapter 5)
- The silicide cap etch's narrower process window, relative to the polysilicon main etch, is a direct consequence of the resistance-driven decision to use a silicide cap at all (Chapters 2–3)

## Study Questions

1. Why does tungsten require a different halogen chemistry emphasis than silicon to achieve comparable volatilization during silicide cap etch?
2. Explain the electrical consequence of a chemistry transition that occurs "too early" at the silicide/polysilicon interface, and why it might not be reliably caught by inline inspection.
3. Why does fluorine-containing chemistry create selectivity tension with both the underlying polysilicon profile and the hard mask simultaneously?
4. In what specific sense is this chapter's narrow process window "the price paid" for the resistance benefit established in Chapter 3?

---

[← Chapter 5](05-hard-mask-strategy.md) · [Index](../INDEX.md) · [Next: Chapter 7 →](07-polysilicon-main-etch-ono-landing.md)
