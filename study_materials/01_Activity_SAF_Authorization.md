# Activity Diagram: SAF Authorization

Welcome to the problem-solving guide for the Student Assistance Fund (SAF) authorization process! We'll use the 5-step method to build real intuition about how to translate a text description into a UML Activity Diagram.

## Step 1: Read & Highlight
Let's break down the problem text and see what structural elements we can extract.

> "A SAF authorization form is used in most universities to approve funding for students to aid their studies. Suppose a student fills out a blank form and sends it to his or her departmental chairperson for a signature."
**Element Type:** Actors (`Student`, `Chairperson`), Action (`Fill out form`), Flow (`Student` -> `Chairperson`).

> "If the amount of funds requested by the student is small (under Tk. 10,000), then the chairperson signs the form and routes it to accounts payable to be input into the accounting system."
**Element Type:** Decision (`Amount size?`), Guard condition (`< 10,000`), Actor (`Accounts Payable`), Action (`Sign form`, `Input to system`).

> "The system cuts a check that is sent to the student for the right amount, and after the check is cashed, the form is filed away with the canceled check."
**Element Type:** Actor (`Accounting System`), Actions (`Cut check`, `Cash check`, `File form`). 

> "If the check in not cashed within 30 days, the form expires."
**Element Type:** Decision/Timer (`Check cashed within 30 days?`), Action (`Expire form`).

> "When the amount of the requested fund is large (over Tk. 10,000), the chairperson signs the form and sends it to the chief financial officer along with a paragraph explaining the reason for the grant, and the chief financial officer will sign the form and pass it along to accounts payable."
**Element Type:** Guard condition (`>= 10,000`), Actor (`CFO`), Actions (`Sign & send with reason`, `Sign & pass to accounts payable`).

> "Both the chairperson and the chief financial officer can reject the SAF authorization form if they do not feel that the reasons for seeking funding are reasonable."
**Element Type:** Decisions (`Chairperson approves?`, `CFO approves?`), Actions (`Reject form`).

> "In this case, the student can change the form to include more explanation or decide to pay the entire fee."
**Element Type:** Decision (`Update or pay?`), Actions (`Update form`, `Pay fee`).

## Step 2: Extract the Building Blocks

**Actors (Swimlanes):**
- Student
- Chairperson
- CFO
- Accounts Payable
- Accounting System

**Decisions:**
1. Chairperson approval (Approve/Reject)
2. Amount check (< 10k or >= 10k)
3. CFO approval (Approve/Reject)
4. Student reaction to rejection (Update form / Pay fee)
5. Check cashing timeout (Cashed / 30 days pass)

**Key Actions:**
- Fill out form
- Sign form
- Evaluate reason
- Input into system
- Cut check
- Cash check
- File form
- Expire form

## Step 3: Build the Flow
1. **Start:** The `Student` begins by filling out the form.
2. The form moves to the `Chairperson`. They must first evaluate it. Decision time!
3. If **rejected** by Chairperson, it goes back to the `Student` who decides to either update (loop back to start) or pay the fee (end).
4. If **approved** by Chairperson, we hit the next decision: **Amount Size**.
5. **Path A (< 10k):** Chairperson signs, goes to `Accounts Payable` to input, then `System` cuts check.
6. **Path B (>= 10k):** Chairperson sends to `CFO`. The CFO evaluates. Another decision!
7. If **CFO rejects**, it goes back to the `Student` (same rejection handling).
8. If **CFO approves**, CFO signs, goes to `Accounts Payable` to input, then `System` cuts check.
9. **Merging the paths:** Both paths eventually hit the check cutting step.
10. **The Timeout:** After the check is cut and sent to the student, we wait. If the student cashes it, it's filed. If 30 days pass, it expires. This is effectively a decision node modeling an event.

## Step 4: The Complete Diagram

```mermaid
graph TD
    ((start)) --> FillForm

    subgraph Student
        FillForm[Fill out blank form]
        StudentRejectDec{Update or Pay?}
        UpdateForm[Update form with more explanation]
        PayFee[Pay entire fee]
        CashCheck[Cash check]
    end

    subgraph Chairperson
        ChairEval{Reasonable?}
        ChairSign[Sign form]
        AmountDec{Amount size?}
        ChairSignLarge[Sign form & explain reason]
    end

    subgraph CFO
        CFOEval{Reasonable?}
        CFOSign[Sign form]
    end

    subgraph Accounts Payable
        APInput[Input to accounting system]
    end

    subgraph Accounting System
        CutCheck[Cut check]
        FilingDec{Check cashed or 30 days passed?}
        FileForm[File form with canceled check]
        ExpireForm[Expire form]
    end

    FillForm --> ChairEval
    ChairEval -->|No| StudentRejectDec
    StudentRejectDec -->|Update| UpdateForm
    UpdateForm --> ChairEval
    StudentRejectDec -->|Pay| PayFee
    PayFee --> ((end1))

    ChairEval -->|Yes| AmountDec
    AmountDec -->|< 10,000| ChairSign
    ChairSign --> APInput
    AmountDec -->|>= 10,000| ChairSignLarge
    ChairSignLarge --> CFOEval
    
    CFOEval -->|No| StudentRejectDec
    CFOEval -->|Yes| CFOSign
    CFOSign --> APInput

    APInput --> CutCheck
    CutCheck --> FilingDec
    
    FilingDec -->|Cashed by student| CashCheck
    CashCheck --> FileForm
    FileForm --> ((end2))
    
    FilingDec -->|30 days pass| ExpireForm
    ExpireForm --> ((end3))
```

## Step 5: Self-Check
Ask yourself these questions to verify your diagram:
1. **Did I capture all rejection paths?** The text says *both* the chairperson and CFO can reject. In our diagram, both evaluations point back to the student's decision.
2. **Is the amount decision in the right place?** It happens *after* the chairperson decides the reasons are reasonable.
3. **How did I handle the 30-day timeout?** We used a decision node after the check is cut to represent the two mutually exclusive outcomes: cashed or expired.
4. **Are all the swimlanes correctly representing the actors?** Yes, each actor has their specific actions grouped.
