# Lazy

Super-simple scoped lazily-initialised objects, because eager evaluation is for
dopes. I am frankly shocked that there is no crate that does this and compiles
on any current version of Rust.

Serving suggestion:

```rust
let lazy = Lazy::new(|| {
	println!("Doing something complicated!");
	42
});

println!("{}", *lazy);
println!("{}", *lazy);
println!("{}", *lazy);

/* Prints:
 *   Doing something complicated!
 *   42
 *   42
 *   42
 */
```

Currently implemented with RefCell, but it will not panic. This class is *not*
thread-safe, the project I made it for will eventually need it to be though,
so I'll probably update it to use something thread-safe eventually.
