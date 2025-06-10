For users to filter the data displayed in the tiles

We can assign a variable name to a parameter so we can refer to it in tiles or [[Base queries]]

```kql
# Modify the base query with the selected_neighbourhoods parameter
bikes
| where ingestion_time() between (ago(30min) .. now())
    and (isempty(['selected_neighbourhoods']) or Neighbourhood in (['selected_neighbourhoods']))
| summarize latest_observation = arg_max(ingestion_time(), *) by Neighbourhood
```