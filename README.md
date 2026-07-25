# CSE-471: Activity & Sequence Diagram Study Guide 📚

> **Goal**: Not just the answers — learn the *thinking process* so you can solve any diagram problem yourself.

---

## 📖 How to Use This Guide

1. **Start with the Masterclass** for whichever diagram type you're studying
2. **Read the 5-Step Method** — this is your solving framework
3. **Try each problem YOURSELF first** before reading the walkthrough
4. **Use the Self-Check questions** at the end of each file to verify your work

> **💡 Viewing Mermaid Diagrams**: These files use [Mermaid](https://mermaid.js.org/) syntax for diagrams. They render automatically in:
> - **VS Code** (with Markdown Preview Mermaid extension)
> - **GitHub** (native support)
> - **Obsidian** (native support)
> - **[Mermaid Live Editor](https://mermaid.live)** (paste the code block)

---

## 🎓 Foundations (Read These First!)

| File | What You'll Learn |
|:-----|:-----------------|
| [00 — Activity Diagram Masterclass](./00_Activity_Diagram_Masterclass.md) | Notation cheat sheet, 5-step method, worked coffee shop example |
| [00 — Sequence Diagram Masterclass](./00_Sequence_Diagram_Masterclass.md) | Notation cheat sheet, 5-step method, worked login example |

---

## 📝 Activity Diagram Problems (6 Problems)

| # | File | Scenario | Key Concepts |
|:-:|:-----|:---------|:-------------|
| 1 | [SAF Authorization](./01_Activity_SAF_Authorization.md) | University funding approval | Nested decisions, rejection paths, 30-day timeout |
| 2 | [Pentagon Security](./02_Activity_Pentagon_Security.md) | Multi-factor authentication | **Fork/Join** (parallel flows), swimlanes |
| 3 | [NFT Marketplace](./03_Activity_NFT_Marketplace.md) | Blockchain minting process | Decisions + parallelism combined |
| 4 | [TeaLeaves Order](./04_Activity_TeaLeaves_Order.md) | Production order management | Merge nodes, fork at the end |
| 5 | [GroceryDash](./05_Activity_GroceryDash.md) | Online grocery delivery | Loops, multi-approval, most complex |
| 6 | [Sarah the Editor](./06_Activity_Sarah_Editor.md) | Book publishing workflow | Multi-actor swimlanes, handoff patterns |

### Recommended Order (by difficulty):
```
4 (TeaLeaves) → 1 (SAF) → 6 (Sarah) → 2 (Pentagon) → 3 (NFT) → 5 (GroceryDash)
   Easy            Medium      Medium      Medium+        Hard        Hardest
```

---

## 📝 Sequence Diagram Problems (6 Problems)

| # | File | Scenario | Key Concepts |
|:-:|:-----|:---------|:-------------|
| 1 | [ABEC Food Ordering](./07_Sequence_ABEC_Food_Ordering.md) | University food system | Loop fragments, search-fetch pattern |
| 2 | [Smart Home](./08_Sequence_Smart_Home.md) | Home automation & security | **Nested alt** fragments |
| 3 | [OTP Authentication](./09_Sequence_OTP_Authentication.md) | Mobile OTP security protocol | Self-messages, internal processing |
| 4 | [Online Exam](./10_Sequence_Online_Exam.md) | Timed MCQ test system | Create/destroy, loops + alts + opts |
| 5 | [Ecommerce](./11_Sequence_Ecommerce.md) | Online shopping | Stock checking, alt patterns |
| 6 | [Hoichoi Streaming](./12_Sequence_Hoichoi.md) | Movie search system | Three-way alt, relay/middleman pattern |

### Recommended Order (by difficulty):
```
5 (Ecommerce) → 1 (ABEC) → 6 (Hoichoi) → 2 (Smart Home) → 3 (OTP) → 4 (Online Exam)
   Easy            Easy+       Medium        Medium+          Hard       Hardest
```

---

## 🧠 The Universal 5-Step Method

Both diagram types use the same core approach:

```
┌─────────────────────────────────────────────────┐
│  Step 1: READ & HIGHLIGHT                       │
│  → Annotate the problem text by element type    │
├─────────────────────────────────────────────────┤
│  Step 2: EXTRACT BUILDING BLOCKS                │
│  → Table of actors, actions, decisions, flows   │
├─────────────────────────────────────────────────┤
│  Step 3: BUILD THE FLOW                         │
│  → Connect elements in logical order            │
├─────────────────────────────────────────────────┤
│  Step 4: DRAW THE DIAGRAM                       │
│  → Complete Mermaid diagram with all elements   │
├─────────────────────────────────────────────────┤
│  Step 5: VERIFY                                 │
│  → Every sentence → at least one diagram element│
└─────────────────────────────────────────────────┘
```

---

## 🔑 Quick Decision Guide

> **"Should this be a Decision or a Fork?"**
>
> - **Decision (Diamond)** → Only ONE path is taken (if/else, either/or)
> - **Fork (Bar)** → ALL paths happen simultaneously (and, meanwhile, at the same time)

> **"Should this be an `alt` or a `loop`?"**
>
> - **`alt`** → Choose one path based on a condition (if/else)
> - **`loop`** → Repeat the same actions multiple times
> - **`opt`** → Do something only if a condition is true (optional)

---

*Generated for CSE-471 System Analysis and Design · BRAC University*
