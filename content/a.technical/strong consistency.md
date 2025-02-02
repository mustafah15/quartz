---
tags:
  - distributed-systems
related: "[[consistency]]"
type: permanent
---

Strong consistency guarantees that **an update to a piece of data needs agreement from all nodes before it becomes visible**. we can apply strong consistency by using a non-distributed system as a lock to our data that lock has the data only and the whole distributed system reads from it. that comes at a cost, It affects our availability to recline to be elastic as this becomes a point of contention in the system. **Traditional monolithic architecture** is usually based on strong consistency.
But how can we reach a strong consistency if physics tells us that we can't? so we usually do it by introducing techniques that simulate strong consistency **Locks** are examples of this, by taking a distributed system problem and reducing it to non-distributed resource. so if we have different distributed services that communicate to a non-distributed database where we have the lock and we have only one copy of it. because this database is not distributed we can eliminate distributed system problem that only exists when we have multiple services that are responsible for the same piece of data. so this can give us a strong consistent system. However, this comes with a cost as whenever we introduce a lock like this it comes with a cost of contention that might affect our ability to be elastic and resilient. we will discuss the effect of contention in the next part.
