# CPU profiling

## Tracing

### Built-in `-profile`

* On Linux, x86_64's `rdtsc` instruction is used.

```console
$ dmd -profile ...
```

or

```console
$ dub build --build=profile
```

### callgrind

```console
$ valgrind --tool=callgrind ./binary
```

D's symbols will need to be demangled by `ddemangle`.
