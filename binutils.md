# binutils

## What functions in `.init_array` ?

Code:

```d
enum body = "import std.stdio;writeln(__PRETTY_FUNCTION__);";

pragma(crt_constructor)
extern (C) void crt_constructor()
{
    mixin(body);
}

void main()
{
    mixin(body);
}
```

Use `readelf -Wx` and `nm`, note that x86 is little endian.

```console
)$ LANG=C readelf -Wx .init_array ./hoge

Hex dump of section '.init_array':
  0x00291dd0 70590400 00000000 70530400 00000000 pY......pS......
  0x00291de0 7c530400 00000000 f0d80600 00000000 |S..............
  0x00291df0 bcfb0600 00000000 54fc0600 00000000 ........T.......

$ nm ./hoge| grep 291dd0
0000000000291dd0 t __init_array_start

$ nm ./hoge| grep 00045370
0000000000045370 t frame_dummy
$ nm ./hoge| grep 0004537c
000000000004537c t
000000000004537c W crt_constructor
$ nm ./hoge| grep 0006fbbc
000000000006fbbc t
000000000006fbbc W _d_register_conservative_gc
$ nm ./hoge| grep 0006d8f0
000000000006d8f0 t
000000000006d8f0 W _d_register_manual_gc
$ nm ./hoge| grep 0006fc54
000000000006fc54 W _d_register_precise_gc
```

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
