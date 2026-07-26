# Activity Diagram Breakdown: Sarah the Editor

## 📋 Problem Statement

> Sarah also works as a part-time editor. She logs into an app with her email and password where she is already registered and she reviews any book proposal she gets. She can choose to accept a proposal after analyzing the proposal or reject the proposal. If the project is rejected it will notify the agent and end the scenario. The agent also uses the same app and is registered as an agent with a different interface where he/she can send book proposals to enlisted editors and contracts to enlisted writers. Due to Sarah accepting the proposal, the agent can offer a contract to the writer. The writer analyzes the offer and asks the agent's opinion on the offer. If both are positive to work on it, the writer will notify Sarah, who is the editor, about accepting it and then begin his/her writing.
>
> *Design an activity diagram from the above scenario.*

---


Hello! In this problem, we're looking at a system heavily driven by interactions between different people. It's a great exercise in visualizing how control passes back and forth between different roles.

## Step 1: Read & Highlight

Let's pick out the actors and their specific actions from the scenario.

> **Sarah (Editor)** **[logs in]** and **[reviews book proposal]**.
> She can **[accept proposal]** or **[reject proposal]**.
> **{If rejected}**, **[notify agent]** and **[end]**.
> The **Agent** can **[send book proposals]** and **[send contracts]**.
> **{If accepted}**, the **Agent** **[offers contract to writer]**.
> The **Writer** **[analyzes offer]** and **[asks agent's opinion]**.
> **{If both are positive}**, writer **[notifies Sarah (Editor)]** and **[begins writing]**.

## Step 2: Extract the Building Blocks

This problem is all about the hand-offs. Let's list our components.

*   **Actors (Swimlanes):** Sarah (Editor), Agent, Writer.
*   **Actions:** Log in, review proposal, accept, reject, notify agent, offer contract, analyze offer, discuss opinion, notify editor, begin writing.
*   **Decisions:**
    *   Does Sarah accept or reject the proposal?
    *   Are *both* the writer and agent positive about the contract?

## Step 3: Build the Flow

Let's trace the path of the proposal as it moves between the actors.

1.  **The Start:** The Agent sends a proposal to Sarah.
2.  **Sarah's Review:** Sarah logs in, reviews it, and makes a decision.
    *   *Rejection Path:* She rejects it, the system notifies the agent, and the process dies right there.
    *   *Acceptance Path:* She accepts it, and control passes *back* to the Agent.
3.  **The Contract Offer:** Because Sarah accepted, the Agent creates and sends a contract offer to the Writer.
4.  **The Negotiation:** The Writer gets the contract, analyzes it, and talks it over with the Agent.
5.  **The Final Decision:** We need *both* of them to feel positive about it. If they are, the Writer sends a notification back to Sarah and finally begins writing. (Note: The problem doesn't explicitly state what happens if they aren't positive, but usually, it would end or loop back to negotiation. For this diagram, we'll assume it just ends if they aren't both positive, based on the text).

## Step 4: The Complete Diagram

Look at how the flow crosses the swimlane boundaries. This perfectly illustrates communication between different users in the system.

```mermaid
graph TD
    subgraph Agent [Agent]
        direction TB
        Start((start))
        A1([Send book proposal to Editor])
        A2([Receive rejection notification])
        End1(((end)))
        A3([Offer contract to Writer])
        A4([Discuss contract opinion with Writer])
    end

    subgraph Editor [Editor]
        direction TB
        S1([Log into app])
        S2([Review book proposal])
        D_Sarah{Accept or Reject?}
        S3([Receive acceptance notification])
    end

    subgraph Writer [Writer]
        direction TB
        W1([Analyze contract offer])
        W2([Ask Agent's opinion])
        D_Both{Both positive?}
        W3([Notify Editor of acceptance])
        W4([Begin writing])
        End2(((end)))
        End3(((end)))
    end

    Start --> A1
    A1 --> S1
    S1 --> S2
    S2 --> D_Sarah
    D_Sarah -->|Reject| A2
    A2 --> End1
    D_Sarah -->|Accept| A3
    A3 --> W1
    W1 --> W2
    W2 --> A4
    A4 --> D_Both
    D_Both -->|Yes| W3
    W3 --> S3
    W3 --> W4
    W4 --> End2
    D_Both -->|No| End3
```

## Step 5: Self-Check

Here are the questions to ask yourself when reviewing this diagram:

1.  **Do the swimlanes accurately reflect the problem?** Are Sarah's actions in Sarah's lane, the Agent's in the Agent's lane?
2.  **Is the hand-off clear?** When Sarah accepts, does the flow clearly cross over to the Agent's lane to offer the contract?
3.  **Did I capture the "Both are positive" condition?** Does the flow show that the decision happens *after* the writer and agent have discussed it?
4.  **Are the end states correct?** Does a rejection by Sarah lead to an end state after notifying the agent?

This problem shows why swimlanes are so powerful for understanding complex team workflows!
