# git

## rebasing

* after rebasing, need to force an update to upstream.

```console
$ git push --force-with-lease origin my-branch
```

## squashing

```console
$ git commit --amend
$ git push --force-with-lease
```
