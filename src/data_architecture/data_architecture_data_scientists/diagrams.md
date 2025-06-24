# Data Architecture for Data Scientists

---

Notes taken from - https://www.udemy.com/course/data-architecture-for-data-scientists

---
# The million $dollah!$ slide

[//]: # (# &#40;TODO&#41; Write diagram in mermaid)

---

# Data warehouse
Diagram to accompany notes.

```mermaid
flowchart TD

subgraph operational_databases
    DB1[(Sales)]
    DB2[(Customer)]
    DB3[(Employee)]
    DB4[(Supplier)]    
end


DW[(Data Warehouse)]

DB1 ----> DW
DB2 ----> DW
DB3 ----> DW
DB4 ----> DW

subgraph external_data - For data enrichment
%% External Datasets
EXT1([🌐 Market Data])
EXT2([📤 Third-Party CRM])
EXT3([📦 Public Demographics])

end

EXT1 --> DW
EXT2 --> DW
EXT3 --> DW

style DW fill:green,stroke:#333,stroke-width:2px

```

---
[//]: # (keep this diagram incase i need to make mermaid look "good")
```mermaid
flowchart TD
%% Nodes
Cloud[(☁️ Cloud Service)]
DB1[(🗄️ Database 1)]
DB2[(🗄️ Database 2)]
DB3[(🗄️ Database 3)]
DB4[(🗄️ Database 4)]

    %% Layout links (invisible to control positioning)
    Cloud --> DB1
    Cloud --> DB2
    Cloud --> DB3
    Cloud --> DB4

    %% Optional positioning using subgraphs
    subgraph Top [ ]
        direction LR
        DB1
        DB2
    end

    subgraph Bottom [ ]
        direction LR
        DB3
        DB4
    end

    DB1 -->|Reads/Writes| Cloud
    DB2 -->|Reads/Writes| Cloud
    DB3 -->|Backup| Cloud
    DB4 -->|Analytics| Cloud
```

---

# Data Architecture flowchart

```mermaid
flowchart TD
    A{Batch or Real Time?}
    B{Which Datatype?}
    C{Frequency of model training}
    D([Start])
    E(Choose between Data Lake or Data Lakehouse)
    F(Choose between Data Lake or Data Lakehouse)
    G(Choose between Data Warehouse or Data Lakehouse)
    H(Kappa Architecture)
    I(Lambda Architecture)
    J[[Enquire about data governance]]
    K[[Enquire about ML specific data infra]]

    D -.-> J
    D -.-> K
    D --> A
    A -->|Batch| B
    A -->|Real Time| C
    B -->|Semi-Structured or Unstructured| E
    B -->|mixed or multimodal| F
    B -->|Structured| G
    C -->|In minutes or online training| H
    C -->|Daily or every few hours| I

    A:::important
    classDef important fill:#283593,stroke:#000,stroke-width:10px,color:#42A5F5;

```