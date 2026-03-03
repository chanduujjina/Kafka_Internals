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
