# dub

## Compiling a C dependency

https://github.com/dlang/dub/wiki/Cookbook#compiling-a-c-dependency

like this:

```sdl
configuration "vendored" {
    preBuildCommands "cc -O0 -ffunction-sections -fdata-sections -g -fPIC -Wall -Wextra -o source/c/global_static.o -c source/c/global_static.c"
    sourceFiles "source/c/global_static.o"
}
```
