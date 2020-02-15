# elfutils

## eu-addrline

* Generate `.debug_aranges` in LDC.

```console
$ ldc2 -help-hidden| grep generate-arange-section
  --generate-arange-section                                       - Generate dwarf aranges
$ ldc2 -g --generate-arange-section helloworld.d
$ nm helloworld| grep _Dmain
000000000001f030 T _Dmain
$ eu-addr2line -e helloworld -f 1f030
_Dmain
/home/kubo39/dev/dlang/helloworld.d:3
```
