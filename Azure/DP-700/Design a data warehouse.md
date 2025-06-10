
Data warehouses contain tables organized in schema that is *optimized for multidimensional modeling*. An example is numerical data related to events e.g., sale orders are grouped by 

Tables in data warehouses are designed to efficiently and effectively handle large amounts of data in the form of **dimensional modeling**. This involves structuring tables into [[Fact tables]] and [[Dimension tables]]

## Data warehouse schema designs

In most transactional databases, the data is *normalized* to reduce duplication, but data in data warehouses is *de-normalized* to reduce the number of `JOIN` queries

Often a data warehouse is organized as a [[Star schema]] but if there are a lot of levels or information is shared by different things, we use the [[Snowflake schema]]

