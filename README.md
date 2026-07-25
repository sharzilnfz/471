# CSE-471: UML Diagram Study Guide 📚

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

| File | Diagram Type | What You'll Learn |
|:-----|:-------------|:-----------------|
| [00 — Use Case Masterclass](./study_materials/00_Use_Case_Diagram_Masterclass.md) | Use Case | Actors, use cases, include vs extend, generalization, library example |
| [00 — Activity Diagram Masterclass](./study_materials/00_Activity_Diagram_Masterclass.md) | Activity | Notation cheat sheet, 5-step method, worked coffee shop example |
| [00 — Sequence Diagram Masterclass](./study_materials/00_Sequence_Diagram_Masterclass.md) | Sequence | Notation cheat sheet, 5-step method, worked login example |

---

## 📝 Use Case Diagram Problems (9 Problems)

| # | File | Scenario | Key Concepts |
|:-:|:-----|:---------|:-------------|
| 1 | [Google Classroom](./study_materials/13_UseCase_Google_Classroom.md) | Teacher/student platform | Secondary actors (Email), extend for materials |
| 2 | [BDEX Courier](./study_materials/14_UseCase_BDEX_Courier.md) | Courier service | Three distinct actors, conditional extend |
| 3 | [Ticket Booking](./study_materials/15_UseCase_Ticket_Booking.md) | Online tickets | **Generalization** (3 passenger types), PAYBD gateway |
| 4 | [Assignment Management](./study_materials/16_UseCase_Assignment_Management.md) | Student assignments | Shared use cases across Teacher/TA |
| 5 | [Robbery Prevention](./study_materials/17_UseCase_Robbery_Prevention.md) | Safety platform | Most complex, many actors, volunteer generalization |
| 6 | [Course Management](./study_materials/18_UseCase_Course_Management.md) | University courses | BSc/MSc generalization, adviser actor |
| 7 | [Bookflix](./study_materials/19_UseCase_Bookflix.md) | Book borrowing | Premium generalization, author actor |
| 8 | [E-Learning](./study_materials/20_UseCase_ELearning.md) | Online learning | Simpler, extend for optional payment |
| 9 | [QuickFix Mechanix](./study_materials/21_UseCase_QuickFix_Mechanix.md) | Car servicing | Complex, multiple generalizations, secondary actors |

### Recommended Order (by difficulty):
```
8 (E-Learning) → 1 (Classroom) → 4 (Assignment) → 2 (BDEX) → 3 (Tickets) → 7 (Bookflix) → 6 (Course) → 5 (Robbery) → 9 (QuickFix)
   Easy            Easy+           Medium          Medium       Medium+        Hard          Hard         Hardest       Hardest
```

---

## 📝 Activity Diagram Problems (6 Problems)

| # | File | Scenario | Key Concepts |
|:-:|:-----|:---------|:-------------|
| 1 | [SAF Authorization](./study_materials/01_Activity_SAF_Authorization.md) | University funding approval | Nested decisions, rejection paths, 30-day timeout |
| 2 | [Pentagon Security](./study_materials/02_Activity_Pentagon_Security.md) | Multi-factor authentication | **Fork/Join** (parallel flows), swimlanes |
| 3 | [NFT Marketplace](./study_materials/03_Activity_NFT_Marketplace.md) | Blockchain minting process | Decisions + parallelism combined |
| 4 | [TeaLeaves Order](./study_materials/04_Activity_TeaLeaves_Order.md) | Production order management | Merge nodes, fork at the end |
| 5 | [GroceryDash](./study_materials/05_Activity_GroceryDash.md) | Online grocery delivery | Loops, multi-approval, most complex |
| 6 | [Sarah the Editor](./study_materials/06_Activity_Sarah_Editor.md) | Book publishing workflow | Multi-actor swimlanes, handoff patterns |

### Recommended Order (by difficulty):
```
4 (TeaLeaves) → 1 (SAF) → 6 (Sarah) → 2 (Pentagon) → 3 (NFT) → 5 (GroceryDash)
   Easy            Medium      Medium      Medium+        Hard        Hardest
```

---

## 📝 Sequence Diagram Problems (6 Problems)

| # | File | Scenario | Key Concepts |
|:-:|:-----|:---------|:-------------|
| 1 | [ABEC Food Ordering](./study_materials/07_Sequence_ABEC_Food_Ordering.md) | University food system | Loop fragments, search-fetch pattern |
| 2 | [Smart Home](./study_materials/08_Sequence_Smart_Home.md) | Home automation & security | **Nested alt** fragments |
| 3 | [OTP Authentication](./study_materials/09_Sequence_OTP_Authentication.md) | Mobile OTP security protocol | Self-messages, internal processing |
| 4 | [Online Exam](./study_materials/10_Sequence_Online_Exam.md) | Timed MCQ test system | Create/destroy, loops + alts + opts |
| 5 | [Ecommerce](./study_materials/11_Sequence_Ecommerce.md) | Online shopping | Stock checking, alt patterns |
| 6 | [Hoichoi Streaming](./study_materials/12_Sequence_Hoichoi.md) | Movie search system | Three-way alt, relay/middleman pattern |

### Recommended Order (by difficulty):
```
5 (Ecommerce) → 1 (ABEC) → 6 (Hoichoi) → 2 (Smart Home) → 3 (OTP) → 4 (Online Exam)
   Easy            Easy+       Medium        Medium+          Hard       Hardest
```

---

## 🧠 The Universal 5-Step Method

All three diagram types use the same core approach:

```
┌─────────────────────────────────────────────────┐
│  Step 1: READ & HIGHLIGHT                       │
│  → Annotate the problem text by element type    │
├─────────────────────────────────────────────────┤
│  Step 2: EXTRACT BUILDING BLOCKS                │
│  → Table of actors, actions, decisions, flows   │
├─────────────────────────────────────────────────┤
│  Step 3: FIND RELATIONSHIPS                     │
│  → Connect elements with proper UML notation    │
├─────────────────────────────────────────────────┤
│  Step 4: DRAW THE DIAGRAM                       │
│  → Complete Mermaid diagram with all elements   │
├─────────────────────────────────────────────────┤
│  Step 5: VERIFY                                 │
│  → Every sentence → at least one diagram element│
└─────────────────────────────────────────────────┘
```

---

## 🔑 Quick Decision Guides

### Use Case Diagrams
> **"Include or Extend?"**
>
> - **Include** → The base use case ALWAYS needs this. Arrow: Base → Included. ("I MUST also do this")
> - **Extend** → The base use case SOMETIMES triggers this. Arrow: Extending → Base. ("I CAN optionally do this")
>
> **"Is this a Generalization?"**
> - "Two types of X: A and B" → YES. A and B inherit from X.

### Activity Diagrams
> **"Decision or Fork?"**
>
> - **Decision (Diamond)** → Only ONE path is taken (if/else, either/or)
> - **Fork (Bar)** → ALL paths happen simultaneously (and, meanwhile, at the same time)

### Sequence Diagrams
> **"Alt, Loop, or Opt?"**
>
> - **`alt`** → Choose one path based on a condition (if/else)
> - **`loop`** → Repeat the same actions multiple times
> - **`opt`** → Do something only if a condition is true (optional)

---

## 📊 Total Coverage

| Diagram Type | Masterclass | Problems | Total Files |
|:------------|:-----------:|:--------:|:-----------:|
| Use Case    | 1           | 9        | 10          |
| Activity    | 1           | 6        | 7           |
| Sequence    | 1           | 6        | 7           |
| **Total**   | **3**       | **21**   | **24**      |

---

*Generated for CSE-471 System Analysis and Design · BRAC University*
