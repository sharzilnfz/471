# CSE-471 — UML Diagram Study Guide

> Learn the *thinking process*, not just the answers. Solve any diagram problem yourself.

---

## How to Use

1. Start with the **Masterclass** for the diagram type you're studying
2. Learn the **5-Step Method** — your universal solving framework
3. Attempt each problem **before** reading the walkthrough
4. Use the **Self-Check** questions to verify your diagram

All diagrams use [Mermaid](https://mermaid.js.org/) syntax — renders natively in VS Code, GitHub, Obsidian, or [mermaid.live](https://mermaid.live).

---

## Foundations

| File | Type | Covers |
|:-----|:-----|:-------|
| [Use Case Masterclass](./study_materials/00_Use_Case_Diagram_Masterclass.md) | Use Case | Actors, include vs extend, generalization |
| [Activity Diagram Masterclass](./study_materials/00_Activity_Diagram_Masterclass.md) | Activity | Fork/join, decisions, swimlanes |
| [Sequence Diagram Masterclass](./study_materials/00_Sequence_Diagram_Masterclass.md) | Sequence | Alt/loop/opt, activation bars, create/destroy |

---

## Use Case Diagrams

| # | Problem | Key Concepts |
|:-:|:--------|:-------------|
| 1 | [Google Classroom](./study_materials/13_UseCase_Google_Classroom.md) | Secondary actors, extend |
| 2 | [BDEX Courier](./study_materials/14_UseCase_BDEX_Courier.md) | Three distinct actors, conditional extend |
| 3 | [Ticket Booking](./study_materials/15_UseCase_Ticket_Booking.md) | Generalization (3 types), external gateway |
| 4 | [Assignment Management](./study_materials/16_UseCase_Assignment_Management.md) | Shared use cases across actors |
| 5 | [Robbery Prevention](./study_materials/17_UseCase_Robbery_Prevention.md) | Many actors, volunteer generalization |
| 6 | [Course Management](./study_materials/18_UseCase_Course_Management.md) | BSc/MSc generalization, adviser actor |
| 7 | [Bookflix](./study_materials/19_UseCase_Bookflix.md) | Premium generalization, author actor |
| 8 | [E-Learning](./study_materials/20_UseCase_ELearning.md) | Extend for optional payment |
| 9 | [QuickFix Mechanix](./study_materials/21_UseCase_QuickFix_Mechanix.md) | Multiple generalizations, secondary actors |

**Difficulty:** 8 → 1 → 4 → 2 → 3 → 7 → 6 → 5 → 9

---

## Activity Diagrams

| # | Problem | Key Concepts |
|:-:|:--------|:-------------|
| 1 | [SAF Authorization](./study_materials/01_Activity_SAF_Authorization.md) | Nested decisions, rejection paths, timeout |
| 2 | [Pentagon Security](./study_materials/02_Activity_Pentagon_Security.md) | Fork/join (parallel flows) |
| 3 | [NFT Marketplace](./study_materials/03_Activity_NFT_Marketplace.md) | Decisions + parallelism combined |
| 4 | [TeaLeaves Order](./study_materials/04_Activity_TeaLeaves_Order.md) | Merge nodes, fork at the end |
| 5 | [GroceryDash](./study_materials/05_Activity_GroceryDash.md) | Loops, multi-approval |
| 6 | [Sarah the Editor](./study_materials/06_Activity_Sarah_Editor.md) | Multi-actor swimlanes, handoffs |

**Difficulty:** 4 → 1 → 6 → 2 → 3 → 5

---

## Sequence Diagrams

| # | Problem | Key Concepts |
|:-:|:--------|:-------------|
| 1 | [ABEC Food Ordering](./study_materials/07_Sequence_ABEC_Food_Ordering.md) | Loop fragments, search-fetch pattern |
| 2 | [Smart Home](./study_materials/08_Sequence_Smart_Home.md) | Nested alt fragments |
| 3 | [OTP Authentication](./study_materials/09_Sequence_OTP_Authentication.md) | Self-messages, internal processing |
| 4 | [Online Exam](./study_materials/10_Sequence_Online_Exam.md) | Create/destroy, loops + alts + opts |
| 5 | [Ecommerce](./study_materials/11_Sequence_Ecommerce.md) | Stock checking, alt patterns |
| 6 | [Hoichoi Streaming](./study_materials/12_Sequence_Hoichoi.md) | Three-way alt, relay pattern |

**Difficulty:** 5 → 1 → 6 → 2 → 3 → 4

---

## Quick Reference

| Question | Answer |
|:---------|:-------|
| Include or Extend? | **Include** = always required. **Extend** = optional. |
| Decision or Fork? | **Decision** = one path (if/else). **Fork** = all paths simultaneously. |
| Alt, Loop, or Opt? | **Alt** = if/else. **Loop** = repeat. **Opt** = optional. |
| Include arrow direction? | Base → Included |
| Extend arrow direction? | Extending → Base |

---

## Coverage

| Type | Masterclass | Problems | Total |
|:-----|:-----------:|:--------:|:-----:|
| Use Case | 1 | 9 | 10 |
| Activity | 1 | 6 | 7 |
| Sequence | 1 | 6 | 7 |
| **Total** | **3** | **21** | **24** |

---

*CSE-471 System Analysis and Design · BRAC University*
