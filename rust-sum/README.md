# Sum two numbers

1. Update the nightly toolchain

```
rustup update nightly

# I personally like to set it as default while I experiment,
# the remainder of the README assumes this
rustup default nightly
```

2. Add the wasm target

```
rustup target add wasm32-unknown-unknown
```

3. Compile

```
rustc sum.rw --target=wasm32-unknown-unknown --crate-type=cdylib
```

4. Optimize the wasm file (optional, using [wasm-gc](https://github.com/alexcrichton/wasm-gc))

```
wasm-gc sum.wasm sum.small.wasm
```

5. Serve the directory and open `index.html` in a browser, e.g.
with Python

```
python -m SimpleHTTPServer 8081
```

You should see the result of calling the function defined in Rust
in the console.