# This is the course project of ECE1755 Parallel Computing and Architecture.

In this project we explored the potential benefit of adding role-switching between access and execute cores to reduce hardware stalls due to load imbalance.

# Motivation
Traditional, DAE (decoupled access and execute) has one access and one execute thread and the access thread will run ahead of the execute thread to prefetch the data.

However, different task has different load for access and execute and it rarely comes in balance.

As a result, either the access thread or the execute thread will run too far ahead and deplete the data queue (or filled the queue) and stall.

# Proposed Solution
Instead of stalling, we propose to add detection of queue empty and full event and trigger role switch to improve hw utilization.

# Results
We successfully demonstrated the benefit of the role-switching mechanism. We see drastic reduce in stalls due to load imbalance.
Although the execution time increased due to software overhead, we believe it can be mitigated by implementing the mechanism completely in HW.
