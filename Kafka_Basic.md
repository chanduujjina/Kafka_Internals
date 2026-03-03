## Each broker contains:
```Code
Kafka Broker
 ├── Topic Partitions (stored on disk)
 ├── Replica Manager
 ├── Log Manager
 ├── Network Layer
 ├── Controller (if elected)
 ├── Group Coordinator
 └── Request Handler Threads
```
🔹 1. Log (Storage Layer)

### Each partition = append-only log file.
```code
/kafka-logs/
   topicA-0/
   topicA-1/
```
