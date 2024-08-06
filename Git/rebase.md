### reorganize local revisions

`git rebase -i`


### move branch to another point in history

```
start         master  public
|                 |   |
v                 v   v
o---o-- ... --o---o---o
```

to

```
start         master
|                 |
v                 v
o---o-- ... --o---o
 \
  o <- public
```

```
git checkout public
git rebase -i start
```

https://stackoverflow.com/questions/7254992/move-branch-to-another-point-in-history