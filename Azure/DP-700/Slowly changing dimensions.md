SCDs evolve over time but at a slow pace and unpredictably. 

Example why SCDs are important: Say when a customer relocates their address change, and the historical data associated with the old address might be lost. When we analyze historical data, we need to know where the customer lived at the time of each sale.

6 types of SCD:

- **Type 0 SCD:** The dimension attributes never change.
- **Type 1 SCD**: Overwrites existing data, doesn't keep history.
- **Type 2 SCD**: Adds new records for changes, keeps full history for a given natural key.
- **Type 3 SCD:** History is added as a new column.
- **Type 4 SCD**: A new dimension is added.
- **Type 5 SCD**: When certain attributes of a large dimension change over time, but using type 2 isn't feasible due to the dimension’s large size.
- **Type 6 SCD**: Combination of type 2 and type 3.

Handle the business key in a type 2 SCD for the `Dim_Products` table:

```sql
IF EXISTS (SELECT 1 FROM Dim_Products WHERE SourceKey = @ProductID AND IsActive = 'True')
BEGIN
    -- Existing product record
    UPDATE Dim_Products
    SET ValidTo = GETDATE(), IsActive = 'False'
    WHERE SourceKey = @ProductID 
        AND IsActive = 'True';
END
ELSE
BEGIN
    -- New product record
    INSERT INTO Dim_Products (SourceKey, ProductName, StartDate, EndDate, IsActive)
    VALUES (@ProductID, @ProductName, GETDATE(), '9999-12-31', 'True');
END
```