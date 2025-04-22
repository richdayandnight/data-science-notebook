# The Data Warehouse Toolkit (3rd edition)

- Ralph Kimball
  - Founded Kimball group
  - mid-1980s data warehouse and business intelligence industry's thought leader on the dimensional approach
  - PhD in electrical engineering in Stanford University
- Margy Ross
  - president of Kimball Group
  - focus on data warehousing and data intelligence
  - taught dimensional best practices to thousands of students

### Skimming Table of Contents

- Chapter 1: Intro to data warehousing, business intelligence, and dimensional modeling
  - core vocabulary established to be used throughout the book
- Chapter 2: Modeling Techniques Overview
  - more than 75 dimensional modeling techniques
- Chapter 3-16: Case Studies
  - Retail Sales
  - Inventory
  - Procurement
  - Order Management
  - Accounting
  - Customer Relationship Management
  - Human Resources Management
  - Financial Services
  - Telecommunications
  - Transportation
  - Education
  - Healthcare
  - Electronic Commerce
  - Insurance
- Chapter 17: Kimball Data Warehouse/ Business Intelligence Life cycle Overview
- Chapter 18: Big Picture of the Workflow of the processes done to do Dimensional Modeling
- Chapter 19-20: Anything outside of Data Warehousing (Includes undercurrents of a data engineering lifecycle)
  - ETL Subsystems and Techniques
  - ETL System Design and Development Process and Tasks
- Chapter 21: Big Data Overview (Analytics)

## Introduction

- Dimensional modeling
  - accepted as mainstream/ dominant technique for DW/BI presentation
  - "Simplicity is the fundamental key that allows users to easily understand databases and software to efficiently navigate databases"
  - Concepts mentioned that withstood the test of time:
    - conformed dimensions
    - slowly changing dimensions
    - heterogeneous products
    - factless fact tables
    - enterprise data warehouse bus matrix
  - Intended audience
    - data stewards
    - all members of project team
      - goal: to be conversant in dimensional modeling
  - impact of dimensional model:
    - beginning with the translation of business requirements up to data warehouse
  - Book is written
    - with broad audience in mind
    - non-denominational: db engine agnostic

## Vocabulary mentioned

- date dimension
- degenerate dimension
- snowflaking
- surrogate keys
- 3 fundamental types of fact tables
  - transaction
  - periodic snapshot
  - accumulating snapshot
- slowly changing dimension
- accounting
  - year-to-date facts
  - multiple fiscal calendars
  - consolidated fact tables
  - dimension attribute hierarchies
    - simple denormalized fixed depth hierarchies
    - bridge tables (for multivalued dimension attributes)
- when a dimensional table begins to behave like a fact table
- supertype schema
- subtype schemas
