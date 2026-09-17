---
"chat": patch
---

Retry initialization after a failed state connection. Once the state adapter (for example Redis) recovers, the next `initialize()` call or webhook tries again instead of rejecting with the original connection error. Concurrent callers still share one attempt. Adapter initialization failures remain cached until `shutdown()` so retries cannot restart adapters that are already running or still starting.
