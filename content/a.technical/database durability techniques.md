---
tags:
  - database
related: "[[database engineering]]"
type: permanent
---
- WAL - write-ahead log
	- writing a lot of data to disk is expensive, which is why DBMSs persist a compressed version of the changes known as WAL

- asynchronous snapshot
	- In this approach everything we write is kept in-memory and later on, asynchronously, it’s snapshot is synced/ written to the drive (persisted disk/ SSD/ Hard-drive) all at once.

- AOF - append-only file
	- Very similar to the WAL strategy, It keeps track of only the changes happening. A very lightweight way of storing the changes and also gives the possibility of reconstructing the state of the system in case of failures.