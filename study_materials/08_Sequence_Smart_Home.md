# Sequence Diagram Practice: Smart Home Automation

Let's break down this complex logical problem step-by-step.

## Step 1: Identify the Objects
Who and what are involved in this smart home?
- **User**: The actor.
- **CPU**: The central processing unit handling logic.
- **Sensor**: Handles fingerprint input.
- **Display**: Shows information to the user.
- **Mobile**: Receives remote alerts/tasks.

## Step 2: Trace the Messages
- User asks for scheduled tasks -> CPU
- CPU checks task count -> displays on Display OR sends to Mobile
- User sets fingerprint -> Sensor
- User sets PIN -> CPU
- (Time passes: User returns)
- User provides fingerprint -> Sensor
- Sensor verifies fingerprint and sends message -> CPU
- CPU checks PIN
- CPU shows welcome on Display OR sends instructions
- CPU sends intruder alert to Mobile (if fingerprint mismatched)

## Step 3: Spot the Fragments
This problem is heavy on alternatives (`alt`):
- **Alt 1 (Task Count)**: 
  - `if tasks > 5`: send to Mobile
  - `else`: show on Display
- **Nested Alts (Returning Home)**:
  - **Outer Alt**: Fingerprint match vs mismatch
    - `if matched`: CPU checks PIN
      - **Inner Alt**: PIN correct vs incorrect
        - `if correct`: Welcome on Display
        - `else`: Reset instructions to User
    - `else (mismatched)`: Intruder alert to Mobile

## Step 4: The Complete Diagram

```mermaid
sequenceDiagram
    actor User
    participant Sensor
    participant CPU
    participant Display
    participant Mobile

    User->>CPU: ask scheduled tasks
    activate CPU
    
    alt tasks > 5
        CPU->>Mobile: send tasks
    else tasks <= 5
        CPU->>Display: show tasks
    end
    deactivate CPU

    Note over User, CPU: At 10:00 AM (Before leaving)
    
    User->>Sensor: set fingerprint
    activate Sensor
    Sensor-->>User: fingerprint set
    deactivate Sensor
    
    User->>CPU: set PIN
    activate CPU
    CPU-->>User: PIN set
    deactivate CPU

    Note over User, CPU: Upon returning home
    
    User->>Sensor: provide fingerprint
    activate Sensor
    
    alt fingerprint matched
        Sensor->>CPU: fingerprint-matched signal
        deactivate Sensor
        activate CPU
        User->>CPU: provide PIN
        
        alt correct PIN
            CPU->>Display: show welcome message
        else incorrect PIN
            CPU->>User: send reset instruction
            User->>CPU: reset PIN
        end
        deactivate CPU
        
    else fingerprint mismatched
        activate Sensor
        Sensor->>CPU: fingerprint-mismatched signal
        deactivate Sensor
        activate CPU
        CPU->>Mobile: send intruder alert
        deactivate CPU
    end
```

## Step 5: Self-Check
- Did I properly nest the inner PIN check `alt` inside the "matched" condition of the outer fingerprint `alt`?
- Are messages going to the correct devices (Mobile for >5 tasks and intruder alert, Display for <=5 tasks and welcome message)?
- Did I capture the sequential setup steps before leaving?
