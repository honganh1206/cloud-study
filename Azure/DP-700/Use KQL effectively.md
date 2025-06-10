```kql
# Retrieve only the columns we need
Automotive
| project trip_id, vendor_id, pickup_datetime, fare_amount

# Filter by rows
Automotive
| where getmonth(pickup_datetime) == getmonth(now())
  and getyear(pickup_datetime) == getyear(now())
| project trip_id, vendor_id, pickup_datetime, fare_amount

# Filter by when the data was loaded into the table e.g., past hour
Automotive
| where ingestion_time() > ago(1h)
| project trip_id, vendor_id, pickup_datetime, fare_amount

# Retrieve the average fare collected by each taxi vendor each hour
Automotive
| where ingestion_time() > ago(1d)
| summarize average_fare = avg(fare_amount) by vendor_id, pickup_hour = hourofday(pickup_datetime)
| project pickup_hour, vendor_id, average_fare
| sort by pickup_hour
```