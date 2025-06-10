Encapsulate a query as a function, making it easier to *repeat common queries*

```kql
# Retrieve the ID and pickup time for trups with at least the specified number of passengers
.create-or-alter function trips_by_min_passenger_count(num_passengers:long)
{
    Automotive
    | where passenger_count >= num_passengers 
    | project trip_id, pickup_datetime
}

# Use the function
trips_by_min_passenger_count (3)
| take 10
```