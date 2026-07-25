# Activity Diagram: Pentagon Security

Welcome to the problem-solving guide for the Pentagon Security protocol! We'll use the 5-step method to understand how to model parallel processes (forks and joins) in a UML Activity Diagram.

## Step 1: Read & Highlight
Let's break down the problem text and see what structural elements we can extract.

> "1. The user must first enter their password on the password kiosk."
**Element Type:** Actors (`User`, `Password Kiosk`), Action (`Enter password`).

> "2. The password kiosk will send the hash of the password to the basic credentials module (which is a part of the credentials system) and prompt the user to enter their YubiKey."
**Element Type:** Actor (`Basic Credentials Module`), Actions (`Send hash`, `Prompt YubiKey`, `Enter YubiKey`).

> "3. The basic credentials module takes the hash and performs the following simultaneously:"
**Element Type:** Parallel Execution (**FORK!**). The word "simultaneously" is the magic word here.

> "a. It matches the hash against known passwords, and if there is a match, then it gets the user uuid, otherwise it generates a false uuid"
**Element Type:** Decision (`Match found?`), Actions (`Match hash`, `Get user uuid`, `Generate false uuid`). This happens *inside* one of the parallel branches.

> "b. generates a set of random numbers"
**Element Type:** Action (`Generate random numbers`). This is the second parallel branch.

> "4. After the uuid and the random numbers are generated, the basic credentials module concatenates them to create a string and sent back to the password kiosk."
**Element Type:** Synchronization (**JOIN!**), Action (`Concatenate and send`). The word "After" both are generated implies we must wait for both branches to finish.

> "5. The password kiosk will then use the YubiKey and the string to generate a hash"
**Element Type:** Action (`Generate hash`).

> "6. If the hash is under a specific limit, the user is allowed access, otherwise the user is declined access."
**Element Type:** Decision (`Hash under limit?`), Actions (`Allow access`, `Decline access`).

## Step 2: Extract the Building Blocks

**Actors (Swimlanes):**
- User
- Password Kiosk
- Basic Credentials Module

**Decisions:**
1. Hash match (Yes: get UUID / No: generate false UUID)
2. Final hash check (< limit / >= limit)

**Parallel Elements:**
- **Fork:** Split after receiving the hash.
- **Branch 1:** Checking hash and getting/generating UUID.
- **Branch 2:** Generating random numbers.
- **Join:** Merge after both branches complete to concatenate.

## Step 3: Build the Flow
1. **Start:** The `User` enters a password into the `Password Kiosk`.
2. The kiosk sends the hash to the `Basic Credentials Module` and prompts the user for a YubiKey. The user enters it.
3. The module receives the hash. **FORK!** Split the path in two.
4. **Parallel Path 1:** The module tries to match the hash. 
   - Decision: If matched -> Get user UUID. If not -> Generate false UUID.
5. **Parallel Path 2:** The module generates random numbers.
6. **JOIN:** Both paths merge back together.
7. The module concatenates the UUID and random numbers and sends them back to the kiosk.
8. The kiosk generates a new hash using the YubiKey and the string.
9. Final Decision: Is the new hash under the limit?
10. If yes -> Allow access (End). If no -> Decline access (End).

## Step 4: The Complete Diagram

```mermaid
graph TD
    ((start)) --> EnterPass

    subgraph User
        EnterPass[Enter password]
        EnterYubi[Enter YubiKey]
    end

    subgraph Password Kiosk
        SendHash[Send hash of password]
        PromptYubi[Prompt user for YubiKey]
        GenFinalHash[Generate hash with YubiKey and string]
        LimitCheck{Hash under limit?}
        AllowAccess[Allow access]
        DeclineAccess[Decline access]
    end

    subgraph Basic Credentials Module
        RecvHash[Receive hash]
        ForkNode===ForkOut1
        ForkNode===ForkOut2
        
        MatchHash[Match hash against passwords]
        MatchDec{Match found?}
        GetUUID[Get user UUID]
        GenFalseUUID[Generate false UUID]
        
        GenRandom[Generate random numbers]
        
        JoinNode===ConcatString
        ConcatString[Concatenate UUID and random numbers]
        SendString[Send string to Kiosk]
    end

    EnterPass --> SendHash
    SendHash --> PromptYubi
    SendHash --> RecvHash
    PromptYubi --> EnterYubi
    
    RecvHash --> ForkNode
    
    %% Branch 1
    ForkNode --> MatchHash
    MatchHash --> MatchDec
    MatchDec -->|Yes| GetUUID
    MatchDec -->|No| GenFalseUUID
    GetUUID --> JoinNode
    GenFalseUUID --> JoinNode
    
    %% Branch 2
    ForkNode --> GenRandom
    GenRandom --> JoinNode
    
    JoinNode --> ConcatString
    ConcatString --> SendString
    
    EnterYubi --> GenFinalHash
    SendString --> GenFinalHash
    
    GenFinalHash --> LimitCheck
    LimitCheck -->|Yes| AllowAccess
    LimitCheck -->|No| DeclineAccess
    
    AllowAccess --> ((end1))
    DeclineAccess --> ((end2))
```

## Step 5: Self-Check
Ask yourself these questions to verify your diagram:
1. **Did I include a Fork and a Join?** Whenever you see words like "simultaneously" or "at the same time," you need a fork. The subsequent step requiring the outputs of both ("After the uuid and... random numbers are generated") requires a join.
2. **Is the decision inside the parallel branch correctly isolated?** Yes, the check for the known passwords happens entirely within one path of the split execution.
3. **Did the Kiosk receive both inputs before the final hash?** Yes, the kiosk needs both the user's YubiKey input and the string from the module.
