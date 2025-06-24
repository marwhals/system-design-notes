# Data Architecture for Data Scientists

---
## The million dollar slide / the big picture. 

*Only batch processing architecture here*

- TODO include stream processing
- TODO make prettier

```mermaid
graph LR

    subgraph unstructured_data
        Video
        Audio
        Speech
        Social_Media
    end

    subgraph semi-structured_data
        World-Wide-Web
        Sensor
        GeoJSON
    end

    subgraph structured_data
        Databases
        CSV_files
        Excel_Spreadsheets
    end

    Data_Integration

    structured_data --> Data_Integration
    semi-structured_data --> Data_Integration
    unstructured_data --> Data_Integration
    Data_Integration --> data_orchestration
    Data_Integration -->|Extract| Data_Lake
    Data_Integration -->|Extract| Staging_Tables
    Data_Integration -->|Extract/Load| NoSQL_DBs

    subgraph data_orchestration_Data_pipelines
        Staging_Tables --> Data_Warehouse --> Data_Marts
        Data_Lake <---> Big_Data_Frameworks
        Data_Lake --> NoSQL_DBs
        Data_Lake -->|Load| Data_Lake
        Staging_Tables -->|Transform| Staging_Tables
        NoSQL_DBs -->|Transform| NoSQL_DBs
        Big_Data_Frameworks --> NoSQL_DBs
    end

    subgraph Semantic_layer_and_governance
        Data_Lake_Semantic
        Data_Catalog
        Cubes
        Identity_Management
    end

    Data_Marts --> Semantic_layer_and_governance
    NoSQL_DBs --> Semantic_layer_and_governance
    Big_Data_Frameworks --> Semantic_layer_and_governance

    subgraph Data_Science_Platforms
        Python
        Jupyter
        R
        DataBricks
    end

    subgraph Analytics_Platforms
        Tableau
    end

    subgraph Users_applications_and_automation
        SAP
        Salesforce
    end

    Semantic_layer_and_governance --> Data_Science_Platforms
    Semantic_layer_and_governance --> Analytics_Platforms
    Users_applications_and_automation --> Analytics_Platforms
    Users_applications_and_automation --> Data_Science_Platforms

    Users_applications_and_automation:::users
    classDef users fill:#283593,stroke:#000,stroke-width:3px,color:#42A5F5;

    Semantic_layer_and_governance:::semantic
    classDef semantic fill:#283593,stroke:#000,stroke-width:3px,color:#42A5F5;

```

---

## Data warehouse
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