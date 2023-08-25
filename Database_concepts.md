ACID
---
- Atomicity: Each transaction is treated as a single "unit", which either succeeds completely or fails completely.
- Consistency: guarantee that any transactions started in the future necessarily see the effects of other transactions committed in the past.
- Isolation: ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially.
- Durability: guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure


CAP Theorem
---
- Consistency 
- Availability
- Partition Tolerance
- Eventual Consistency