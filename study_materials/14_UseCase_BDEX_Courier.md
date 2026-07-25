# Use Case Diagram: BDEX Courier

Welcome back! Let's tackle the BDEX Courier system. This one has some interesting conditional behaviors and multiple roles.

## Step 1: Identify the Actors
- **Customer**: Initiates delivery, chooses delivery type, receives contacts.
- **First Officer**: Fills out forms, handles packaging documents.
- **Manager**: Approves parcels, contacts customers, marks deliveries.

*Notice that these are three distinct actors with different roles. There is no generalization here because they aren't subtypes of a single generic user.*

## Step 2: Extract the Use Cases
- **Customer**: Initiate Delivery, Choose Delivery Type, Confirm Delivery.
- **First Officer**: Fill Courier Form, Fill Insurance Document.
- **Manager**: Approve Parcel, Contact Customer, Mark Delivered.

## Step 3: Find the Relationships
- Choosing express delivery adds reward points. We can show this as **Express Delivery** `<<include>>` **Add Reward Points**.
- Filling out insurance is conditional (only for confidential/fragile items), so **Fill Insurance Document** `<<extend>>` **Fill Courier Form**.
- Manager marking the package as delivered requires customer confirmation, so **Mark Delivered** `<<include>>` **Confirm Delivery** (or the Customer simply participates in the Confirm Delivery use case).

## Step 4: The Complete Diagram

```mermaid
graph LR
    %% Actors
    C((Customer))
    FO((First Officer))
    M((Manager))

    %% System Boundary
    subgraph BDEX Courier System
        UC1([Initiate Delivery])
        UC2([Regular Delivery])
        UC3([Express Delivery])
        UC4([Add Reward Points])
        UC5([Fill Courier Form])
        UC6([Fill Insurance Document])
        UC7([Approve Parcel])
        UC8([Contact Customer])
        UC9([Mark Delivered])
        UC10([Confirm Delivery])
    end

    %% Actor Connections
    C --- UC1
    C --- UC8
    C --- UC10
    
    FO --- UC5
    M --- UC7
    M --- UC8
    M --- UC9

    %% Relationships
    UC2 -.->|inherits| UC1
    UC3 -.->|inherits| UC1
    UC3 -.->|<<include>>| UC4
    
    UC6 -.->|<<extend>>| UC5
    UC9 -.->|<<include>>| UC10
```

## Step 5: Self-Check
- Are the conditional rules represented correctly? Yes, `<<extend>>` handles the fragile items rule.
- Did I avoid generalization for actors? Yes, Customer, First Officer, and Manager are completely separate.
- Do arrows for `<<include>>` point from the base to the included use case? Yes!
