flowchart TD
UA["fa:fa-cog User API"] -->|Protobuf Request| IS
CA["fa:fa-cog Company API"] -->|Protobuf Request| IS
OS["fa:fa-cog Other Services"] -->|Protobuf Request| IS

    subgraph IS["Image Storage Service"]
        IS_CFG["Evaluate Config & Image Type"]
        PROCIMG["Process Image"]
        SD{{Choose Storage}}
        IS_CFG --> PROCIMG
        PROCIMG --> SD
        style IS fill:#f5f5dc,stroke:#333,stroke-width:2px
    end

    SD --> LDB[(Regional Database)]
    SD --> GDB[(Global Database)]

    classDef userapi fill:#934cbb,stroke:#333,stroke-width:2px;
    classDef companyapi fill:#6545cc,stroke:#333,stroke-width:2px;
    classDef otherapi fill:#e5ccff,stroke:#333,stroke-width:2px;
    classDef eval fill:#cce5ff,stroke:#333,stroke-width:2px;
    classDef proc fill:#ffe5cc,stroke:#333,stroke-width:2px;
    classDef decision fill:#fff2cc,stroke:#333,stroke-width:2px;
    classDef db fill:#0081ad,stroke:#333,stroke-width:2px;
    classDef regionaldb fill:#b3e6b3,stroke:#333,stroke-width:2px;

    class UA userapi;
    class CA companyapi;
    class OS otherapi;
    class IS_CFG eval;
    class PROCIMG proc;
    class SD decision;
    class LDB regionaldb;
    class GDB db;
