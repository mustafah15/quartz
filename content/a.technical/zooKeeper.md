---
tags:
  - system-design
  - distributed-systems
related: "[[kafka]]"
type: permanent
---
- What is ZooKeeper?
	- A critical dependency of Apache Kafka is Apache ZooKeeper, which is a distributed configuration and synchronization service. ZooKeeper serves as the coordination interface between the Kafka brokers, producers, and consumers. Kafka stores basic metadata in ZooKeeper, such as information about brokers, topics, partitions, partition leader/followers, consumer offsets, etc.