![[Pasted image 20250522163112.png]]

Here we split up the `DimProduct` table (normalized) to create separate dimension tables for `DimSupplier` and `DimCategory`: Each row in `DimProduct` contains a key corresponding to rows in `DimSupplier` and `DimCategory`

Similarly, each row in `DimStore` and `DimCustomer` contains a key value corresponding to a row in `DimGeography`
