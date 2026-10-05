# Planar NAND Control Gate Etch — Chapter Index

## Navigation & Quick Reference

---

## Front Matter

| Section | Status | Overview |
|---------|--------|----------|
| [README.md](README.md) | ✓ | Book overview, audience, scope, and file organization |
| [PREFACE.md](PREFACE.md) | ✓ | Why control gate etch is a conductor problem first, intellectual framework |

---

## Part I: Control Gate Fundamentals

### The Word Line, Its Materials, and Its Electrical Role

| Chapter | File | Status | Key Topics |
|---------|------|--------|-----------|
| **1** | [01-control-gate-role.md](chapters/01-control-gate-role.md) | ✓ | Control gate's role as word line conductor vs. floating gate's role as charge storage node, why the two etches are judged by different failure modes, industrial context |
| **2** | [02-stack-materials-conductors.md](chapters/02-stack-materials-conductors.md) | ✓ | Control gate polysilicon, polycide (WSix) caps, refractory metal silicides, dopant strategy, grain structure — material properties and why each exists |
| **3** | [03-word-line-architecture-rc.md](chapters/03-word-line-architecture-rc.md) | ✓ | Word line sheet resistance, RC delay model, array read/program timing sensitivity, the case for silicide/metal caps over bare polysilicon |
| **4** | [04-electrical-requirements-coupling.md](chapters/04-electrical-requirements-coupling.md) | ✓ | Gate length (CD) control requirements, threshold voltage uniformity, coupling ratio sensitivity to control gate profile and ONO landing quality |

---

## Part II: Control Gate Etch Process Design

### Engineering the Silicide/Polysilicon Word Line Etch

| Chapter | File | Status | Key Topics |
|---------|------|--------|-----------|
| **5** | [05-hard-mask-strategy.md](chapters/05-hard-mask-strategy.md) | ✓ | Hard mask material selection for silicide-capped stacks, mask selectivity across cap and polysilicon, array/periphery mask considerations |
| **6** | [06-silicide-polycide-etch-chemistry.md](chapters/06-silicide-polycide-etch-chemistry.md) | ✓ | WSix and refractory metal silicide etch chemistry, fluorine/chlorine-based systems, residue-free cap removal, transition to polysilicon |
| **7** | [07-polysilicon-main-etch-ono-landing.md](chapters/07-polysilicon-main-etch-ono-landing.md) | ✓ | Control gate polysilicon main etch, soft-landing transition onto ONO, selectivity targets, overetch budget |
| **8** | [08-rf-bias-ono-interface.md](chapters/08-rf-bias-ono-interface.md) | ✓ | RF bias power strategy near the ONO interface, ion energy management, profile control through the soft-landing step |
| **9** | [09-array-periphery-uniformity.md](chapters/09-array-periphery-uniformity.md) | ✓ | Array vs. peripheral logic pattern density, dual-pitch recipe design, etch rate matching across the die |

---

## Part III: Process Phenomena & Defect Control

### Physics of Control Gate Failure Modes and Their Mitigation

| Chapter | File | Status | Key Topics |
|---------|------|--------|-----------|
| **10** | [10-cd-control-gate-length.md](chapters/10-cd-control-gate-length.md) | ✓ | Gate length (CD) control through the silicide/polysilicon stack, line edge/width roughness, metrology approaches specific to word lines |
| **11** | [11-stringers-footing-bridging.md](chapters/11-stringers-footing-bridging.md) | ✓ | Polysilicon/silicide stringer formation, gate footing, word-line-to-word-line bridging, root causes and mitigation |
| **12** | [12-microloading-arde-array-periphery.md](chapters/12-microloading-arde-array-periphery.md) | ✓ | Microloading between dense array and isolated peripheral gates, aspect ratio dependent etch effects, compensation strategies |
| **13** | [13-ono-interface-damage.md](chapters/13-ono-interface-damage.md) | ✓ | Overetch and punch-through risk at the ONO interface, coupling ratio degradation mechanisms, correlating etch conditions to electrical shift |
| **14** | [14-endpoint-detection-multilayer.md](chapters/14-endpoint-detection-multilayer.md) | ✓ | Optical emission spectroscopy across silicide/polysilicon/ONO transitions, endpoint signal design, soft-landing endpoint strategies |

---

## Part IV: Production Integration & Resistance Scaling

### From Manufacturing Reality to Conductor Architecture Limits

| Chapter | File | Status | Key Topics |
|---------|------|--------|-----------|
| **15** | [15-word-line-resistance-scaling.md](chapters/15-word-line-resistance-scaling.md) | ✓ | Word line sheet resistance scaling history, polycide-to-metal-cap transition, limits reached at advanced planar nodes, the bridge to 3D NAND metal word lines |
| **16** | [16-post-etch-clean-yield.md](chapters/16-post-etch-clean-yield.md) | ✓ | Post-etch clean chemistry for silicide/polysilicon residue, inspection strategies for control gate defects, yield learning loop and feedback to recipe development |

---

## Status Legend

| Symbol | Meaning |
|--------|---------|
| ✓ | Complete and published |
| 🔨 | In development |
| 📋 | Outline ready, writing in progress |
| 🚩 | Not yet started |

---

## Reading Recommendations

### For Process Engineers
**Optimal path:** Preface → Part I (Ch 1–4) → Part II (Ch 5–9) → Part III (Ch 10–14)

This path builds the full etch-sequence logic before addressing failure modes, matching how a process engineer would actually develop a recipe.

### For Circuit & Device Engineers
**Optimal path:** Ch 1, 3 → Ch 4 → Ch 13 → Ch 15

This path connects etch and material decisions most directly to word line RC delay, coupling ratio, and array timing outcomes.

### For Integration Engineers
**Optimal path:** Preface → Ch 1, 2 → Ch 9 → Part III (Ch 10–14)

This path emphasizes the array/periphery duality and its downstream defect and uniformity consequences.

### For Readers Focused on Resistance Scaling and the 3D NAND Transition
**Optimal path:** Ch 1 → Ch 3 → Ch 10–12 → Ch 15

This path establishes what scaling broke, electrically and physically, before explaining how the industry's conductor strategy changed in response.

### Complete Reading (Recommended for Deep Understanding)
**Front to back:** Read in order, Part I → Part II → Part III → Part IV.

This provides the most rigorous foundation, since later chapters assume the stack-by-stack and failure-mechanism logic built earlier.

---

## Relationship to Sibling Volumes in This Series

- ***Planar NAND Floating Gate Etch*** is this book's direct companion volume: it treats the full stack etch (silicide through tunnel oxide) judged by tunnel oxide integrity and charge retention. This book re-examines the same stack's top half — silicide cap and control gate polysilicon — judged by word line conductivity and ONO landing quality. Each book defers to the other for topics outside its stated scope.
- **Polysilicon gate etch (logic devices):** single-material gate etch fundamentals that this book extends into the silicide-capped, dual-pattern-density control gate context
- **3D NAND process volumes** (slit etch, memory hole etch, high-aspect-ratio ONO stack etch): the vertical successor architecture, where metal word line fill resolves the resistance-scaling problem this book's Chapter 15 traces
- **Shallow trench isolation etch:** general-purpose STI processing; not addressed in this book, since STI self-alignment couples to the floating gate etch, not the control gate etch

---

## How to Use This Index

1. **Start here** if you're new to the book — pick your reading path based on your role
2. **Reference this** while reading chapters to understand where each chapter fits in the larger narrative
3. **Quick lookup** when you need specific topics (use the Key Topics column)
4. **Status tracking** to see which chapters are complete

---

**Development Phase:** Complete (16 of 16 chapters)
