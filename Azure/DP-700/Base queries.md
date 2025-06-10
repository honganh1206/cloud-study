Common dashboard design: Multiple tiles based on a *related set of data*

What should we do? Make **base queries** that retrieve a general set of records relevant for multiple tiles, then use tile-specific queries to filter/group data

```kql
# Return ALL DATA FIELDS within the last 30 minutes
bikes
| where ingestion_time() between (ago(30min) .. now())
| summarize latest_observation = arg_max(ingestion_time(), *) by Neighbourhood

```

We can assign a variable name to refer to in tile-specific queries