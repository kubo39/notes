# gdb

## language d

* Automatically detected by `DW_AT_language`

```console
$ dmd -g helloworld.d
$ readelf -wi helloworld| grep DW_AT_language| head -1
    <24>    DW_AT_language    : 19    (D)
```

* Use `set language d` manually.

```
(gdb) show language
The current source language is "auto; currently d".
(gdb) set language d
(gdb) show language
The current source language is "d".
```
