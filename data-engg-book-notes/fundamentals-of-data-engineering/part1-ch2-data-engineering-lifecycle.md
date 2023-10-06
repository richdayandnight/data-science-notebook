# Chapter 2: The Data Engineering Lifecycle

## What is Data Engineering Life Cycle
- Data Engineering Lifecycle stages
    1. Generation
    2. Storage
    3. Ingestion
    4. Transformation
    5. Serving Data
- Undercurrents
    1. Security
    2. Data Management
    3. DataOps
    4. Data Architecture
    5. Orchestration
    6. Software Engineering

![Data Engineering Life Cycle](./ch1-fig1.png)

- The middle stages- storage, ingestion, trasformation- can get a bit jumbled, repeat themselves, overlap, or weave together in interesting and unexpected ways
- The data engineering lifecycle is a subset of the data lifecycle.

## 1. Generation: Source Systems
- A source system is the origin of the data used in the data engineering lifecycle.
- A data engineer consumes data from the source system but doesn't typically own or control the source system itself.
- Understanding of the way systems owrk
  - way they generate data
  - the frequency
  - velocity of data
  - variety of data they generate
- Data Engineer must need to keep open line of communication w/ source system owners on changes that could break pipelines and analytics
- Questions data engineers must consider/ask when assessing source systems
  - What are the essential characteristics of the data source? Is it an application? A swarm of IoT devices?
  - How is data persisted in the source system? Is data persisted long term, or is it temporary and quickly deleted?
  - At what rate is data generated? How many events per second? How many gigabytes per hour?
  - What level of consistency can data engineers expect from the output data? If you’re running data-quality checks against the output data, how often do data inconsistencies occur—nulls where they aren’t expected, lousy formatting, etc.?
  - How often do errors occur?
  - Will the data contain duplicates?
  - Will some data values arrive late, possibly much later than other messages produced simultaneously?
  - What is the schema of the ingested data? Will data engineers need to join across several tables or even several systems to get a complete picture of the data?
  - If schema changes (say, a new column is added), how is this dealt with and communicated to downstream stakeholders?
  - How frequently should data be pulled from the source system? (Will there be a limit to the query to be used in order not to cause any resource contention or performance issues)
  - For stateful systems (e.g., a database tracking customer account information), is data provided as periodic snapshots or update events from change data capture (CDC)? What’s the logic for how changes are performed, and how are these tracked in the source database?
  - Who/what is the data provider that will transmit the data for downstream consumption?
  - Will reading from a data source impact its performance?
  - Does the source system have upstream data dependencies? What are the characteristics of these upstream systems?
  - Are data-quality checks in place to check for late or missing data?

### Schema
- Fixed Schema
- Schemaless
  - Schemaless doesn't mean the absence of schema
  - It means the application defines the schema as data is written (ex. document database such as MongoDB)

> Challenge: Schema changes over time. Refer to Chapter 6 and 8 for data modeling on schemas and data modeling.

## 2. Storage

- Choosing a storage solution is key to success in the rest of the data lifecycle
- Questions data engineers must consider/ask when choosing a storage system for a data warehoue, data lakehoue, database, or object storage:
  - Is this storage solution compatible with the architecture’s required write and read
speeds?
  - Will storage create a bottleneck for downstream processes?
  - Do you understand how this storage technology works? Are you utilizing the storage system optimally or committing unnatural acts? For instance, are you applying a high rate of random access updates in an object storage system? (This is an antipattern with significant performance overhead.)
  - Will this storage system handle anticipated future scale? You should consider all capacity limits on the storage system: total available storage, read operation rate, write volume, etc.
  - Will downstream users and processes be able to retrieve data in the required service-level agreement (SLA)?
  - Are you capturing metadata about schema evolution, data flows, data lineage,
and so forth? Metadata has a significant impact on the utility of data. Metadata represents an investment in the future, dramatically enhancing discoverability and institutional knowledge to streamline future projects and architecture changes.
  - Is this a pure storage solution (object storage), or does it support complex query patterns (i.e., a cloud data warehouse)?
  - Is the storage system schema-agnostic (object storage)? Flexible schema (Cassandra)? Enforced schema (a cloud data warehouse)?
  - How are you tracking master data, golden records data quality, and data lineage for data governance? (We have more to say on these in “Data Management” on page 50.)
  - How are you handling regulatory compliance and data sovereignty? For example, can you store your data in certain geographical locations but not others?
- Data Access Frequency
  - Data access frequency will determine the temperature of your data
  - Data that is most frequntly accessed is called *hot data*
    - Hot data - commonly retrieved many times per day, perhaps even several times per second
    - Lukewarm data - might be accessed every so often -- say, every week or month
    - Cold data 
      - seldom queried and is appropriate for storing in an archival system
