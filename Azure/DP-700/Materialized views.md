> Think of views as *queries pretending to be tables*

Summary of data from a source table or another materialized view

```kql
# View containing number of trips for each vendor each day
.create materialized-view TripsByVendor on table Automotive
{
    Automotive
    | summarize trips = count() by vendor_id, pickup_date = format_datetime(pickup_datetime, "yyyy-MM-dd")
}
```

View will be populated *as new data is ingested into the source table*

```kql
# Asynchronous operation to create a view with a backfill option to populate data
.create async materialized-view with (backfill=true)
TripsByVendor on table Automotive
{
    Automotive
    | summarize trips = count() by vendor_id, pickup_date = format_datetime(pickup_datetime, "yyyy-MM-dd")
}

# Then we query the view just like how we query a table
TripsByVendor
| project pickup_date, vendor_id, trips
| sort by pickup_date desc
```