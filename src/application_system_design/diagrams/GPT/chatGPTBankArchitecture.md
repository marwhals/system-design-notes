```mermaid

graph TD;

    %% Customer Channels
    A[Customer Channels] -->|Mobile App| B[Mobile Banking]
    A -->|Web| C[Online Banking]
    A -->|ATM| D[ATM Services]
    A -->|Branch| E[Branch Operations]

    %% Core Banking System
    subgraph Core Banking System
        F[Accounts Management]
        G[Payments & Transfers]
        H[Loans & Mortgages]
        I[Cards & Transactions]
    end

    %% AI & Analytics Layer
    subgraph AI & Analytics
        J[Fraud Detection AI]
        K[Risk Management]
        L[Personalized Offers]
        M[AI Chatbots & Support]
    end
    
    %% Security & Compliance Layer
    subgraph Security Layer
        N[Identity & Access Management]
        O[API Gateway]
        P[Firewalls & Intrusion Detection]
    end

    %% Infrastructure Layer
    subgraph Infrastructure
        Q[On-Prem Data Centers]
        R[Cloud Services AWS/GCP/Azure]
        S[Hybrid Cloud Architecture]
    end

    %% Connections
    B & C & D & E -->|APIs| O
    O -->|Secure API Calls| F & G & H & I
    F & G & H & I -->|Data Feeds| J & K & L & M
    J & K & L & M -->|Insights| B & C
    N -->|User Authentication| B & C & D & E
    O -->|Security Enforcement| P
    P -->|Threat Monitoring| Q & R
    Q & R & S -->|Data Storage & Processing| F & G & H & I
