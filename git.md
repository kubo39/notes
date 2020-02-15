# git

## rebasing

https://wiki.dlang.org/Starting_as_a_Contributor#Rebasing

* after rebasing, need to force an update to upstream.

```console
$ git push --force-with-lease origin my-branch
```

## squashing

https://wiki.dlang.org/Starting_as_a_Contributor#Squashing

```console
$ git commit --amend
$ git push --force-with-lease
```
