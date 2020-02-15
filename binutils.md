# binutils

## demangle (for old mangling rule)

* addr2line/nm/objdump: `--dmangle=dlang`
* c++file: `-s dlang` or `--format=dlang`

```console
$ echo _Dmain| c++filt -s dlang $1
```

However, ddemangle would be better in general case (ddemangle supports new mangling rule).

```console
$ nm binary| ddemangle
```
