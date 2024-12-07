# Java Counter Race Condition

This repository demonstrates a common race condition in Java multithreaded programming.  The `Counter` class attempts to increment a counter from multiple threads. Due to the non-atomic nature of the increment operation, the final count is often less than the expected value.

**Problem:** The `count++` operation is not atomic. It can be broken down into multiple steps:
1. Read the value of `count`.
2. Increment the value.
3. Write the new value back to `count`.

If two threads execute this simultaneously, they might both read the same value of `count`, increment it independently, and then write the same (incorrect) value back, leading to a loss of increments.

**Solution:**  Use appropriate synchronization mechanisms (e.g., `AtomicInteger`, `synchronized` blocks/methods) to ensure atomicity.