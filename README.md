
```mermaid
flowchart TD
    UserAPI["User API"] -->|Protobuf| ImageStorage
    CompanyAPI["Company API"] -->|Protobuf| ImageStorage
    OtherAPI["Other Services"] -->|Protobuf| ImageStorage

    subgraph ImageStorage["Image Storage Service"]
        Config["Evaluate Config & Type"] --> Process["Process Image"]
        Process --> Decision{{Choose Storage}}
        style ImageStorage fill:#f5f5dc,stroke:#333,stroke-width:2px
    end

    Decision --> RegionalDB[(Regional DB)]
    Decision --> GlobalDB[(Global DB)]

    classDef api fill:#934cbb,stroke:#333,stroke-width:2px;
    classDef config fill:#cce5ff,stroke:#333,stroke-width:2px;
    classDef process fill:#ffe5cc,stroke:#333,stroke-width:2px;
    classDef decision fill:#fff2cc,stroke:#333,stroke-width:2px;
    classDef db fill:#0081ad,stroke:#344,stroke-width:2px;
    classDef regionaldb fill:#b3e6b3,stroke:#333,stroke-width:2px;

    class UserAPI,CompanyAPI,OtherAPI api;
    class Config config;
    class Process process;
    class Decision decision;
    class RegionalDB regionaldb;
    class GlobalDB db;

   ```
