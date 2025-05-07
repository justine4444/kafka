# Apache Kafka – Introduction and Fundamentals

Apache Kafka is a **distributed event streaming platform** used to build **real-time data pipelines** and **streaming applications**. It is designed to be **fault-tolerant**, **horizontally scalable**, and capable of **handling high-throughput data streams**.

Kafka allows systems to **produce**, **store**, **process**, and **consume** data in a decoupled and scalable way.

---

## 🔧 Core Components

### 1. **Topic**
- A **logical channel** to which producers send records and consumers subscribe.
- Topics are **append-only logs** and are **partitioned** for horizontal scalability.
- Kafka retains messages for a configured period (e.g., 7 days), regardless of consumption.

### 2. **Partition**
- A **subdivision of a topic**, allowing Kafka to scale horizontally and maintain **message ordering** within each partition.
- Each message in a partition has a unique **offset**.
- Partitions are distributed across brokers and can be replicated for fault tolerance.

### 3. **Broker**
- A **Kafka server** that holds topic partitions and handles all read/write operations from clients.
- A Kafka **cluster** is a group of brokers.
- Brokers handle **replication**, **leadership**, and **client coordination**.

### 4. **Producer**
- A **client application** that publishes messages to Kafka topics.
- Producers can control **which partition** a message goes to using keys or partitioners.
- Kafka supports **asynchronous and batched** writes for performance.

### 5. **Consumer**
- A **client application** that subscribes to one or more topics and processes messages.
- Consumers belong to a **consumer group**; each partition is read by **only one consumer in a group**.
- Kafka tracks the **offset** per partition to resume from where the consumer left off.

### 6. **Offset**
- A **sequential ID** assigned to each message within a partition.
- Consumers use offsets to track their progress.
- Kafka supports both **automatic** and **manual** offset commits for flexibility and reliability.

### 7. **ZooKeeper / KRaft**
- Kafka used **ZooKeeper** (pre-3.0) to manage metadata, broker registration, and controller election.
- Kafka now supports **KRaft (Kafka Raft)** mode for **ZooKeeper-less architecture** in versions 2.8+ and beyond.
- KRaft simplifies Kafka’s architecture and improves scalability.

---

## ✅ Kafka Guarantees

| Feature                | Guarantee                                      |
|------------------------|-----------------------------------------------|
| Message Durability     | Replication across brokers                     |
| Ordering               | Maintained per partition                      |
| Delivery Semantics     | At-most-once, at-least-once, exactly-once     |
| Scalability            | Partition-based parallelism                   |

---

## 📌 Use Cases

- Real-time analytics (e.g., user behavior tracking)
- Log aggregation and monitoring
- Event-driven microservices
- Data lake ingestion pipelines
- Stream processing (using Kafka Streams or ksqlDB)

---

## 📚 Resources

- [Apache Kafka Documentation](https://kafka.apache.org/documentation/)
- [Kafka Streams](https://kafka.apache.org/documentation/streams/)
- [Confluent Platform](https://www.confluent.io/)

---

## 📎 Summary

Kafka enables decoupling of services through durable, distributed messaging with real-time capabilities. It plays a foundational role in modern data engineering systems.

