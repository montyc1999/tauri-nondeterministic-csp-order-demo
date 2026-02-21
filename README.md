Run `touch src/main.rs && cargo build` a few times and see that it's slow every time:

```
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 4.83s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 4.72s
```

Then delete these lines from `tauri.conf.json`:

```
"img-src": "'self'",
"font-src": "'self'",
"media-src": "'self'",
"script-src": "'self'",
```

```
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 4.92s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.73s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.76s
```
