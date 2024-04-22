# Lecture 1: Introduction

## Infrastructure

This course is about the infrastructure the applications use.
How can we make the distributed systems in a way that we can think about them just like a non-distributed system?

- **Storage**: replicated, fault-tolerant, high-performance, distributed implementation of storage.
- **Computation**: eg. map-reduce, threads, concurrency control, ...
- **Communication**: how systems talk to each other eg. rpc

## Performance with Scalability

- can I horizontally scale to solve the problem faster. 2x computers -> 2x throughput.
- cheaper than hiring engineers to optimize
- How can I split the requests to multiple instances of web servers connected to the single (abstraction of) database.
- When the storage becomes the bottleneck, why can we solve this? eg. sharding

## Fault Tolerance

0.3% failure rate means 3 out of 1,000 computers will fail. eg. fan broken, worn-out hardwares, defect cable, etc...

- **Availability**: replicas in different region, data center, rack, machine, etc...
  - consistency between replicas
- **Recoverability**: can it perform as nothing happened after addressing the failure eg. power comes back up
  - non-volatile storage eg. WAL for Postgres
  - dealing with slow disc eg. moving arms & rotating disc

## Consistency

  In distributed system, there are more than one copy of the data.
  We need **concurrency control**.

- How do we invoke Put and Get on different versions of the data? eg. via table lock
- Stale copy from read replica
- Strong vs weak guarantee eg. transaction (expensive)
