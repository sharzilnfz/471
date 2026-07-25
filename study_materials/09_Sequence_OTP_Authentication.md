# Sequence Diagram Practice: OTP Authentication

## 📋 Problem Statement

> The following scenario shows a successful authentication of a client using the mobile OTP solution.
> The authentication is initiated when a user requests access to a service that requires authentication. The SP notifies the authenticator that a user needs to be authenticated. The session is redirected to the authenticator and the user is asked to enter a username. The username is sent to the AS, which gets the secret key for this client and, from this generates an OTP. The OTP is also based on a challenge. A different challenge is used every time so the generated OTP is always changing. At last a message authentication code (MAC) based on the secret key is calculated over the OTP. The AS sends the triplet (challenge, MAC, OTP) to the Authenticator which relays the challenge and the MAC to the client. Upon receiving the challenge, the client calculates the OTP. Then it calculates the MAC and compares it to the one received from the Authenticator. If the values match the client can authenticate the AS since the AS has proved that it is in possession of the shared key. The client then sends the OTP back to the Authenticator. If the MAC is wrong, the authentication is aborted. The Authenticator compares the OTP with the one received from the AS and if they match, notifies the SP that the client is authenticated. A mutual authentication of the client and server has been achieved and the session is redirected back to the SP which grants the user access to the service.
>
> *Draw a sequence diagram based on the above information.*

---


Let's model this security protocol sequence diagram.

## Step 1: Identify the Objects
- **Client (User)**: The entity trying to authenticate.
- **SP (Service Provider)**: The service being accessed.
- **Authenticator**: The middleman relaying messages.
- **AS (Authentication Server)**: Generates and verifies OTP/MAC.

## Step 2: Trace the Messages
- Client requests access -> SP
- SP notifies -> Authenticator
- Session redirected, User enters username -> Authenticator
- Authenticator sends username -> AS
- AS gets secret key, generates OTP, calculates MAC (internal processing)
- AS sends (challenge, MAC, OTP) -> Authenticator
- Authenticator relays (challenge, MAC) -> Client
- Client calculates OTP and MAC (internal)
- Client compares MAC. If match -> Client sends OTP to Authenticator
- Authenticator compares OTP. If match -> notifies SP
- SP redirects session and grants access -> Client

## Step 3: Spot the Fragments
- **Self-messages**: AS generating OTP/MAC. Client calculating OTP/MAC.
- **Alt 1 (Client MAC Check)**: 
  - `if MAC matches`: Client sends OTP to Authenticator
  - `else`: Authentication aborted
- **Alt 2 (Authenticator OTP Check)**:
  - `if OTP matches`: Notify SP, grant access
  - `else`: (Implicit failure/abort)

## Step 4: The Complete Diagram

```mermaid
sequenceDiagram
    actor Client
    participant SP as Service Provider
    participant Auth as Authenticator
    participant AS as Authentication Server

    Client->>SP: request access
    activate SP
    SP->>Auth: notify user needs authentication
    activate Auth
    SP-->>Client: redirect to Authenticator
    deactivate SP
    
    Client->>Auth: enter username
    Auth->>AS: send username
    activate AS
    
    Note right of AS: Internal Processing
    AS->>AS: get secret key
    AS->>AS: generate OTP (based on challenge)
    AS->>AS: calculate MAC
    
    AS-->>Auth: send (challenge, MAC, OTP)
    deactivate AS
    
    Auth-->>Client: relay (challenge, MAC)
    
    Note left of Client: Internal Processing
    Client->>Client: calculate OTP
    Client->>Client: calculate MAC
    
    alt MAC matches
        Client->>Auth: send OTP
        
        alt OTP matches
            Auth->>SP: notify client authenticated
            deactivate Auth
            activate SP
            SP-->>Client: grant access & redirect
            deactivate SP
        else OTP mismatch
            Auth-->>Client: authentication failed
        end
        
    else MAC mismatch
        Client->>Client: abort authentication
    end
```

## Step 5: Self-Check
- Did I use self-messages (`Client->>Client`) to show internal calculations?
- Is it clear that the Authenticator keeps the OTP from the AS and only relays the challenge and MAC?
- Are the `alt` blocks placed where the decisions are actually made (Client checking MAC, Authenticator checking OTP)?
