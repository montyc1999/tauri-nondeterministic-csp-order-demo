Run `touch src/main.rs && cargo build` a few times and see that it's slow every time:

```
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 8.78s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 8.82s
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
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 9.01s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.94s
$ touch src/main.rs && cargo build
   Compiling tauri-nondeterministic-csp-order-demo v0.1.0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.87s
```
