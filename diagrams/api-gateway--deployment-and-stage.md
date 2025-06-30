# API Gateway - Deployment and stage (WIP)

```mermaid
graph LR
    Dev["Developer"]
    A["API configuration<br>(Resouces, method, integration)"]
    C["**Deployment** _1_<br>(a snapshot of API configuration)"]
    C2["**Deployment** _2_<br>(a snapshot of API configuration)"]
    E[Endpoint URL]
    U[Users]
    S["**Stage** _dev_"]


    subgraph Key Concepts
      S -->|3 - Named reference of| C
      A -->|2a - Deploy| C
      %% C -.->|2b - Snapshot of| A
      %% C2 -.->|5a - Snapshot of| A
      A -->|5b - Deploy| C2
      S -->|6 - Named reference of| C2
    end

    U -->|"https...api-id..._dev"_| E
    E --> S
    
    Dev -->|1 - Develope| A 
    Dev -->|4 - Update| A
```
