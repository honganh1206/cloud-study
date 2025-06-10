Fabric provides a number of security features like RBAC, TLS encryption, etc.

We have *workspace permissions* and *item permissions* and we can grant permissions via T-SQL

We can use *dynamic management views* i.e., `sys.dm_exec_connections`, `sys.dm_exec_sessions` and `sys.dm_exec_requests` to monitor connection, session and request status to see live SQL query lifecycle insights

```sql
-- Identify long-running queries that may be impacting the overall performance
SELECT request_id, session_id, start_time, total_elapsed_time
    FROM sys.dm_exec_requests
    WHERE status = 'running'
    ORDER BY total_elapsed_time DESC;
```