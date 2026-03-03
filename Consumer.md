## Topic Internals

```code
Topic
  ├── Partition 0 → [msg1, msg2, msg3, ...]
  ├── Partition 1 → [msg1, msg2, msg3, ...]
  ├── Partition 2 → [msg1, msg2, msg3, ...]
```


- Messages are stored inside partitions

- Each partition is an append-only log

- Each message has a unique offset
