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

Command:

```console
$ valgrind --tool=callgrind --callgrind-out-file=callgrind.out.slow.1 ./slow
```

D's symbols will need to be demangled by `ddemangle`.

```console
$ callgrind_annotate callgrind.out.slow.1| ddemangle
```
