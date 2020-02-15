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

## Using gold as system linker

- https://code.dawg.eu/reducing-vibed-turnaround-time-part-1-faster-linking.html

```console
$ update-alternatives --install "/usr/bin/ld" "ld" "/usr/bin/ld.gold" 20
$ update-alternatives --install "/usr/bin/ld" "ld" "/usr/bin/ld.bfd" 10
$ update-alternatives --config ld  # manually select linker
```
