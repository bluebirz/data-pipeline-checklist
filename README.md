
# data-pipeline-checklist

Checklist for creating a new data pipeline

## data engineering principles

```mermaid
flowchart 
    A[Requirements] --> B[Analysis]
    B --> C[Design]
    C --> D[Implement]
    D --> E[Test]
    E --> F[Deploy]
    F --> G[Maintain]
    G --> H[Monitoring]
    H --> I[Documentation]
```

## 1. Requirements

- requirements gathering
- documents acquire  
  - data dictionary
  - data schema
  - data contracts
- batch or real-time
- retry mechanism
- error reporting
- stakeholders and contact points
-

## 2. Analysis

## 3. Design

- tools
  - ETL/ELT tools (e.g. Apache Airflow, Luigi, Prefect)
  - Data integration tools (e.g. Apache Nifi, Talend)
  - Data transformation tools (e.g. dbt, Apache Spark)

## 4. Implement

- test-driven development (TDD)
- reusable functions

## 5. Test

- unit tests
- integration tests
- smoke tests
- test data
- test environment
- test cases

## 6. Deploy

- CI/CD pipeline
- Infrastructure as Code (IaC)
  - tools (e.g. Terraform, Ansible, CloudFormation)

## 7. Maintain & Document

- Knowledge base (e.g. confluence, Notion)

### source

- Platform
  - On-premise
  - Cloud

### sink

- Platform
  - On-premise
  - Cloud

## Data privacy

### PII data

- Contact informations
  - Name (First name, Last name)
  - Telephone number
  - Email address
  -

### Sensitive information

## Data security

### Hash (e.g. SHA256)

### Encryption

- Field-level encryption (e.g. AES-GCM, AES-CBC)
- File-level encryption (e.g. GPG, PGP)

## Time-based integration

### Batch

- schedule time

### Near real-time

### Real-time

## Constraints

### Rate limits

## Credentials

### User accounts

### Service accounts

## Monitoring

### Push notification

### Email notification

## Post-productions

### Historical loads

### notes

- data contracts
- data quality
- data transformations

# Design

## Medalian architecture

```mermaid
stateDiagram-v2
  direction LR
  state "Data lake" as lake
  state "Raw data" as lake
  state "Bronze layer" as bronze
  state "Ingested data" as bronze 
  state "Silver layer" as silver
  state  "ProcessedData"  as silver
  state "Gold layer" as gold
  state "AnalyticsData" as gold
  
  lake --> bronze: ingest
  bronze --> silver: clean & <br>transform
  silver --> gold: business logics
```

## Data types

<details>
  <summary>Click to expand</summary>

```mermaid
mindmap
  root((Data types))
    (Numerical)
      [integer]
      [floating point]
    (Logical)
      [boolean]
        [True/False]
        [T/F]
        [1/0]
        [Y/N]
    (Text)
      [String]
      [Bytes]
    (Date/Time)
      [date]
      [time]
      [datetime]
      [timestamp]
      [timezone]
        [UTC]
        [Local]
    (Collection)
      [Array/List]
      [Struct]
      [JSON]
    (Others)
      [Geography]
```

</details>

## Naming conventions

<details>
  <summary>Click to expand</summary>

```mermaid
mindmap
  root((Naming<br/>conventions))
    (Case formatting)
      [snake_case]
      [kebab-case]
      [camelCase]
      [PascalCase]
      [UPPER_CASE]
    (Prefixes and suffixes)
      [table level] 
        [Fact<br>&lpar;fct&rpar;]
        [Dimension<br>&lpar;dim&rpar;]
        [Transactional<br>&lpar;txn&rpar;]
        [Aggregate<br>&lpar;agg&rpar;]
        [Temporary<br>&lpar;tmp&rpar;]
        [Views<br>&lpar;vw&rpar;]
        [History<br>&lpar;hist&rpar;]
        [Transform<br>&lpar;trf&rpar;]
        [Serving<br>&lpar;srv&rpar;]
        [Junk<br>&lpar;junk&rpar;]
      [column level]
        [ID &lpar;id&rpar;]
        [Indexes &lpar;idx&rpar;]
        [Constraints<br>&lpar;pk, fk, uk&rpar;]
```

</details>

## Performance-first

- Chunk/batch logics and configurations
- Min/Max instances

## Permissions

- Least privilege principle
- Service accounts
- Project-level roles
- Service-level roles

## Security

- PII data
- Hashing, Masking, Encryption
  - MD5
  - SHA256
  - AES
- Secret keys management
  - Hashicorp Vault
  - AWS Secrets Manager
  - Azure Key Vault
  - Google Cloud Secret Manager

# Requirements gathering

- sensor file
  - blank file
  - checksum file
  - record file
  - others
- data volume for performance-first design

## row ID

- incremental ID
- user ID (UID, UUID)
- Aggregated ID
  - hash functions
  - fingerprint
  -
