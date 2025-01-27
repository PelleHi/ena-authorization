```mermaid
sequenceDiagram
    %% OIDC Authentication Flow: User to Server
    %% Step 1: User attempts to access a protected resource on the Relying Party (RP).
    User->>RP: Access Protected Resource

    %% Step 2: RP detects the user is not authenticated and redirects the user to the OpenID Provider (OP) for authentication.
    RP->>User: Redirect to OP for Authentication

    %% Step 3: User authenticates with the OP (e.g., enters credentials) and consents to the requested scopes.
    User->>OP: Authenticate and Consent

    %% Step 4: After successful authentication, the OP redirects the user back to the RP with an authorization code.
    OP->>User: Redirect to RP with Authorization Code

    %% Step 5: The user's browser sends the authorization code to the RP.
    User->>RP: Send Authorization Code

    %% Step 6: The RP exchanges the authorization code with the OP for an ID Token and Access Token.
    RP->>OP: Exchange Authorization Code for Tokens

    %% Step 7: The OP validates the authorization code and returns the ID Token and Access Token to the RP.
    OP->>RP: Return ID Token and Access Token

    %% Step 8: (Optional) If additional user information is needed, the RP can use the Access Token to request the UserInfo endpoint.
    RP->>OP: (Optional) Request UserInfo

    %% Step 9: The OP returns the requested user information (e.g., name, email) to the RP.
    OP->>RP: Return UserInfo (if requested)

    %% Step 10: The RP validates the ID Token and grants the user access to the protected resource.
    RP->>User: Grant Access to Resource
