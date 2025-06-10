Contains descriptive information about the data in the fact tables

Small number of rows. 

Provide **context** for the data in [[Fact tables]] e.g., Information about customers who placed sale orders

Has a **unique key column** that *uniquely identifies each row in the table*

A dimension table usually has two key columns:

- A **surrogate key** to identify each row in the table -> Maintain consistency and accuracy of the data
- An **alternate key** that identifies a specific instance of an entity in the transactional source system e.g., product code or customer ID -> Maintain traceability between the data warehouse and the source system

[[Business key and surrogate key]]

> Think of dimension tables as the "who, what, where, when, why" of your data warehouse

## Special types of dimension tables

**Time dimensions** provide *information about the time period when an event occurred* e.g., a time dimension tables include columns for the year/quarter/month...

**[[Slowly changing dimensions]]** track changes to dimension attributes over time.


