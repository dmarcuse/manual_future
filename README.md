# manual_future

Explicitly completed `Future` type for Rust, similar to Java's `CompletableFuture`

## Example

```rust
// create a new, incomplete ManualFuture
let (future, completer) = ManualFuture::new();

// complete the future with a value
completer.complete(5).await;

// retrieve the value from the future
assert_eq!(future.await, 5);

// you can also create ManualFuture instances that are already completed
assert_eq!(ManualFuture::new_completed(10).await, 10);
```