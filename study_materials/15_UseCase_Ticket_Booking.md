# Use Case Diagram: Ticket Booking

Hello again! This Ticket Booking system is a classic example of actor generalization and secondary actors. Let's break it down!

## Step 1: Identify the Actors
- **Passenger**: A general actor.
- **General, Premium, New**: Subtypes of Passenger. This is a perfect spot for **Generalization**!
- **System Admin**: Confirms tickets.
- **PAYBD**: The payment gateway. This is a **Secondary Actor** because the system calls out to it.

## Step 2: Extract the Use Cases
- **Passenger (General)**: Register, Login, Buy Ticket, Pay Online, Cancel Booking, Request Refund.
- **System Admin**: Confirm Ticket.

## Step 3: Find the Relationships
- **Generalization**: General, Premium, and New actors inherit from Passenger. *Note: "New" is an actor here because they can only Register and haven't logged in yet.*
- **Buy Ticket** requires admin confirmation, so **Buy Ticket** `<<include>>` **Confirm Ticket**.
- **Pay Online** relies on PAYBD, so the use case connects to the PAYBD actor.
- Requesting a refund happens after a cancellation, usually as an optional step, so **Request Refund** `<<extend>>` **Cancel Booking**.

## Step 4: The Complete Diagram

```mermaid
graph LR
    %% Actors
    P((Passenger))
    NewP((New Passenger))
    GenP((General Passenger))
    PremP((Premium Passenger))
    
    SA((System Admin))
    PAYBD((PAYBD Gateway))

    %% Actor Generalization
    NewP -->|inherits| P
    GenP -->|inherits| P
    PremP -->|inherits| P

    %% System Boundary
    subgraph Online Ticket Booking
        UC1([Register])
        UC2([Login])
        UC3([Buy Ticket])
        UC4([Confirm Ticket])
        UC5([Pay Online])
        UC6([Cancel Booking])
        UC7([Request Refund])
    end

    %% Actor Connections
    P --- UC1
    P --- UC2
    P --- UC3
    P --- UC5
    P --- UC6
    
    SA --- UC4
    UC5 --- PAYBD

    %% Use Case Relationships
    UC3 -.->|<<include>>| UC4
    UC7 -.->|<<extend>>| UC6
```

## Step 5: Self-Check
- Did I capture the actor generalization correctly? Yes, New, General, and Premium inherit from Passenger. Arrow points FROM child TO parent.
- Is PAYBD shown as an external/secondary actor? Yes, connected to Pay Online.
- Is Request Refund an extend? Yes, it's optional behavior after a cancellation.
