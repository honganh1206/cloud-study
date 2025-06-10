Define 
- The relationships between the different tables 
- The rules for how data is aggregated and summarized
- The calculations or measures used to get insights from the data

Every time  data warehouse is created, Fabric creates a *semantic model* for users from different departments to connect to

Semantic models are *automatically kept in sync* with the data warehouse

The *default semantic model* inherits business logic from parent lakehouse  or warehouse and is always kept in sync. New tables in the lakehouse are automatically added to the default semantic model