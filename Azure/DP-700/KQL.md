---
id: KQL Overview
aliases:
  - KQL Overview
tags: []
---

Kusto Query Language

**Read-only** request language

Can handle large volumes of structured/semi-structured/unstructured data

```kql
person
| where name == "AAA"
| project name, age

```

A more complex example

```kql
stock
 | where ["time"] > ago(5m)
 | summarize avgPrice = avg(todecimal(bidPrice)) by symbol
 | project symbol, avgPrice
```

[[Use KQL effectively]]

[[Materialized views and stored functions]]

