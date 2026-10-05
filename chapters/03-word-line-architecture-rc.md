# Chapter 3: Word Line Architecture: Sheet Resistance, RC Delay, and the Case for Silicide/Metal Caps

## Executive Summary

This chapter makes the quantitative case, previewed in Chapters 1 and 2, that word line resistance is a first-order design constraint independent of transistor-level scaling. We develop the RC delay model for a word line driven from one edge of the array, show how sheet resistance and parasitic capacitance combine to set a propagation delay that must remain small relative to the array's read/program timing budget, and quantify the resistance reduction silicide/polycide caps must deliver to keep that delay acceptable as word line pitch scales. This chapter is the electrical foundation Chapter 15 returns to when tracing how the planar control gate's conductor strategy evolved — and eventually ran out of room to evolve further within the planar architecture.

---

## Part 1: The Word Line as a Distributed RC Line

### 1.1 Physical Picture

A word line in a planar NAND array is driven at one edge (or, in some architectures, from both edges) by a word line driver circuit, and must reach its target voltage at every cell along its length — potentially many thousands of cells, spanning hundreds of micrometers to low millimeters of physical distance, depending on array architecture. Electrically, this is a distributed resistor-capacitor (RC) transmission line: resistance distributed along the conductor's length (set by sheet resistance and line geometry), and capacitance distributed to the substrate below, to adjacent word lines on either side, and to bit lines crossing above.

### 1.2 The Elmore Delay Approximation

For a distributed RC line driven from one end, a standard first-order estimate of the propagation delay to the far end is the Elmore delay:

$$\tau \approx 0.5 \cdot R_{total} \cdot C_{total}$$

where $R_{total}$ is the total end-to-end word line resistance and $C_{total}$ is the total capacitance along its length. Both terms scale with word line length, so total delay scales with the *square* of word line length for fixed per-unit-length R and C — a relationship that makes word line length (set by array architecture, specifically the number of cells per block) a powerful lever on delay, but one that is typically fixed by array organization decisions made well upstream of etch process development. The etch and materials engineer's lever is $R$ per unit length (sheet resistance), developed in this chapter, and to a lesser extent $C$ per unit length (gate stack geometry's contribution to parasitic capacitance), noted briefly in Part 3.

### 1.3 Sheet Resistance and Total Line Resistance

For a word line of length $L$ and width $W$ formed from a conductor with sheet resistance $R_s$ (in ohms per square), total end-to-end resistance is:

$$R_{total} = R_s \cdot \frac{L}{W}$$

Because $W$ (word line width, closely tied to the gate length / CD values Chapter 4 and Chapter 10 develop) shrinks with each technology generation while $L$ (word line length, set by array organization) shrinks much more slowly if at all, the ratio $L/W$ — the number of "squares" in the line — grows significantly from generation to generation. This is the quantitative root of the resistance-scaling problem introduced in Chapter 1: **even if sheet resistance $R_s$ were held perfectly constant, total line resistance would still rise as width scales down faster than length.**

---

## Part 2: Quantifying the Silicide Benefit

### 2.1 Illustrative Numbers

| Conductor | Sheet Resistance $R_s$ (Ω/sq) | Relative Resistance (bare poly = 1×) |
|-----------|-------------------------------|----------------------------------------|
| **Bare n+ polysilicon** | 200–500 | 1× (baseline) |
| **Polycide (WSix cap)** | 20–50 | ~5–10× lower |
| **Tungsten word line (3D NAND successor architecture, for context)** | 1–5 | ~100× lower (outside this book's planar scope; see Chapter 15) |

These figures are illustrative teaching values rather than qualified production specifications (see Preface), but the ratios are representative of the order-of-magnitude benefit each conductor strategy delivers and are consistent with the published literature on polycide and metal gate conductor engineering.

### 2.2 Why "5–10× Lower" Was Necessary, Not Merely Desirable

Combining the Elmore delay relationship with the $L/W$ scaling argument above: as word line width scales down by roughly 2× per technology generation (a simplified but representative scaling assumption), $L/W$ and therefore $R_{total}$ roughly doubles if sheet resistance is held constant. Left unaddressed across several generations of scaling, this compounding resistance increase would have driven word line RC delay to values incompatible with target read/program access times — not a gradual degradation, but a threshold effect once delay becomes comparable to the timing budget allocated to word line settling. The polycide cap's 5–10× sheet resistance reduction, introduced at a specific technology generation (Chapter 1, Section 3.1), bought back multiple generations of further width scaling before the same threshold was approached again — which is exactly the resistance-scaling story Chapter 15 resumes and completes.

### 2.3 The Overetch/Residue Penalty on Realized Resistance

The sheet resistance values above describe the *as-deposited* silicide film. Etch process quality directly affects *realized* word line resistance in two distinct ways, both developed further in Part III of this book:
1. **Incomplete silicide removal between adjacent word lines** (Chapter 11) does not merely risk electrical bridging — even sub-catastrophic residue increases effective capacitive coupling between adjacent lines, degrading the $C$ term in the delay equation
2. **Silicide sidewall damage or lateral etch during the cap removal step** can locally thin the remaining silicide cross-section on the lines that are supposed to remain, raising $R_s$ above its as-deposited value specifically at the etched line's edges — a second-order effect, but one that becomes proportionally larger as line width shrinks and edge effects represent a larger fraction of total cross-section

---

## Part 3: Capacitance Contributions and Gate Stack Geometry

### 3.1 Capacitance Components

Word line capacitance per unit length has several contributors: gate-to-channel capacitance (the "useful" capacitance that couples to the floating gate stack beneath, discussed in Chapter 4), gate-to-substrate parasitic capacitance outside the active transistor area, line-to-line capacitance to adjacent word lines, and line-to-bit-line capacitance where bit lines cross above the word line layer. Of these, line-to-line capacitance is most directly sensitive to etch profile: a non-vertical sidewall angle (profile defects discussed in Chapters 9–11) increases the effective area of close approach between adjacent lines, raising this capacitance term beyond its ideal vertical-sidewall value.

### 3.2 Why This Book Treats Capacitance as Secondary to Resistance

While profile-driven capacitance effects are real and etch-sensitive, they are second-order relative to the resistance effects developed in Parts 1–2: sheet resistance differences between conductor strategies (bare poly vs. polycide vs. metal) span one to two orders of magnitude, while profile-driven capacitance variations from realistic etch process windows are typically a modest percentage effect. This book therefore treats word line resistance as the primary RC delay lever that etch and materials decisions control, with capacitance effects noted where etch profile quality interacts with them (Chapters 9–11) but not developed as an independent chapter-length topic.

---

## Chapter Summary

- The word line is a distributed RC transmission line; Elmore delay scales with the product of total resistance and total capacitance, and with the square of word line length for fixed per-unit-length values
- Total line resistance equals sheet resistance times the number of "squares" ($L/W$), which grows as word line width scales down faster than word line length
- Polycide (silicide-capped) conductors deliver a 5–10× sheet resistance reduction relative to bare polysilicon, a reduction that was necessary, not merely beneficial, to avoid an RC delay scaling cliff
- Etch process quality affects *realized* resistance independent of as-deposited film properties, through incomplete silicide removal (parasitic capacitive coupling) and sidewall silicide thinning (locally elevated resistance)
- Capacitance contributions are real and etch-sensitive but are treated as second-order relative to resistance effects in this book's scaling argument, which Chapter 15 completes

## Study Questions

1. Using the Elmore delay relationship, explain why word line length (an array architecture decision) and word line width (a lithography/etch decision) do not contribute symmetrically to delay scaling.
2. Why does total word line resistance rise with scaling even under the simplifying assumption that sheet resistance itself is held perfectly constant?
3. Explain why the polycide cap's resistance benefit is better described as "necessary" rather than "merely desirable" at the technology generation where it was introduced.
4. Describe two distinct mechanisms by which etch process quality can cause realized word line resistance to differ from the as-deposited silicide film's nominal sheet resistance.

---

[← Chapter 2](02-stack-materials-conductors.md) · [Index](../INDEX.md) · [Next: Chapter 4 →](04-electrical-requirements-coupling.md)
