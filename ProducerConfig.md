## Producer config:

```code
acks=0
acks=1
acks=all
```

### 🔹 acks=0

- Producer does NOT wait.

- No confirmation

- Fastest

- Risk of data loss

- Success value:
→ Producer assumes success immediately


### 🔹 acks=1

- Leader broker writes message to its log
- Leader sends success response

- Success means:
✔ Leader stored message
❌ Followers may not have replicated yet


### 🔹 acks=all (or -1)

- Leader waits for all ISR replicas to confirm

- Success means:
✔ Leader stored message
✔ All in-sync replicas stored message


```code
acks=all
retries=3
enable.idempotence=true
```
- ✔ No data loss
- ✔ No duplicate writes
- ✔ High durability


## What Scenarios Cause Producer-Side Lag?


### 🔹 1. Broker Overload

- If broker disk is slow:

- Writes are slow

- Producer waits

- Latency increases


```code
acks=all
```


###  🔹 2. Large Message Size

- Big payload (e.g., 10MB):

- Serialization slow

- Network slow

- Replication slow

### 🔹 3. High Replication Factor

- If replication factor = 3 and one follower is slow:

- Leader waits → delay.
