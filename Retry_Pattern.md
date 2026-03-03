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
