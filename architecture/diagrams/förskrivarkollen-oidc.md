´´mermaid
sequenceDiagram
    participant User
    participant RP as Relying Party (Client)
    participant OP as OpenID Provider (IdP)

    User->>RP: Access Protected Resource
    RP->>User: Redirect to OP for Authentication
    User->>OP: Authenticate and Consent
    OP->>User: Redirect to RP with Authorization Code
    User->>RP: Send Authorization Code
    RP->>OP: Exchange Authorization Code for Tokens
    OP->>RP: Return ID Token and Access Token
    RP->>OP: (Optional) Request UserInfo
    OP->>RP: Return UserInfo (if requested)
    RP->>User: Grant Access to Resource

