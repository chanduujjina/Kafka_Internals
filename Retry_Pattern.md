## 🔥 First: What is Retry in Kafka Producer?

- If producer sends a request and:
  - No ACK received

  - Timeout happens
  - Broker returns error
  - Producer retries automatically.

```properties
retries=3
retry.backoff.ms=100
delivery.timeout.ms=120000
```
## Internal Architecture

Producer has:
```Plain Text
Application Thread
     ↓
RecordAccumulator (buffer)
     ↓
Sender Thread
     ↓
NetworkClient
     ↓
Broker
```


### Case 1: Broker Temporarily Unavailable

- Network error

- Leader changed

- Connection reset

- Producer receives exception.


### What Happens Internally?

- 1️⃣ Request marked as failed
- 2️⃣ Metadata refreshed
- 3️⃣ Batch put back into accumulator
- 4️⃣ Wait retry.backoff.ms
- 5️⃣ Resend
