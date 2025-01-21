```mermaid 
sequenceDiagram
autonumber
    box rgb(230,255,255) Region A
    participant A as Användar-<br>browser
    participant B as IdP
    end
    box rgb(230,255,230) EHM
    participant C as SP Förskrivarkollen
    participant D as Förskrivarkollen
    end
    Note over A,D: TILLIT I FEDERATION
    A->>C: HTTP GET (trust verified)
    C-->>A: User not authenticated, redirect Browser to user IdP
    A->>B: Autenticate request
    B-->>A: Authenticate and SAML response
    A->>C: SAML responce to SP 
    C->>D: User logged in 
