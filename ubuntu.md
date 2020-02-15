# ubuntu

## Search a package

```console
$ apt-cache madison <pattern>
```

## which package provide the program X ?

```console
$ dpkg -S $(command -v route)
net-tools: /sbin/route
```

## List all packages installed

```console
$ dpkg -l
(...)
```
