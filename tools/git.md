### Some Helpful Config Stuff

```
$ git config --global alias.staash 'stash --all'
```

```
https://gist.github.com/schacon
$ git config --global alias.bb !better-branch.sSh
```

```
Conditional Configs

[includeIf "gitdir:~/projects/work/"]
path = ~/projects/work/.gitconfig
[includeIf "gitdir:~/projects/oss/"]
path = ~/projects/oss/.gitconfig
```

### Oldier But Goodies

```
$ git blame -L
  just blame a "L"ittle
```

```
git log -L 15,26:path/to/file
```

```
$ git blame -W
  ignore whitespace

$ git blame -w -C
  ignore whitespace
  and detect lines moved or copied in the same commit
```

```
$ git log -S
  the "pickaxe"

git log -S files_watcher -p
```

```
git diff --word-diff
```

```
$ git config --global rerere.enabled true
  REuse REcorded REsolution
```

### Some New Stuff You May Not Have Noticed

```
$ git branch --column

git config --global column.ui auto
git config --global branch.sort -committerdatce
```

```
$ git push --force-with-lease
```


