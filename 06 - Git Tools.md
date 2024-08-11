# Stashing and Cleaning
## summary

```shell
git stash -a
git stash list
git stash drop stash@{<n>}
git stash apply stash@{<n>} --index
```

## saving in stash

to save dirty changes into the stack :
```shell
git stash
```
or
```shell
git stash push
```

## inspection

to see stored changes list :
```shell
git stash list
```

## applying stashes

this one will apply the most recent saved stash in your stack :
```shell
git stash apply
```

it you want to specify to apply which stack you should do this :
```shell
git stash apply stash@{2}
```

## applying with staged files

```shell
git stash apply --index
```

## dropping stashes

```shell
git stash drop stash@{<n>}
```

example : `git stash drop stash@{2}`

## popping stashes

to remove the most recent stash :
```shell
git stash pop
```

## --keep-index

This tells Git to not only include all staged content in the stash being created, but simultaneously leave it in the index :
```shell
git stash --keep-index
```

## --include-untracked or -u

```shell
git stash --include-untracked
```
or :
```shell
git stash -u
```

## --patch

Git will not stash everything that is modified but will instead prompt you interactively which of the changes you would like to stash and which you would like to keep in your working directory :
```shell
git stash --patch
```

## cleaning your working directory

```shell
git clean
```

> [!DANGER] DON'T USE IT !
> `git clean` is a really powerful command which will remove all untracked files and directories in your workspace . use `git stash --all` instead to save messy work in the stack instead . 
 
substitute :
```shell
git stash --all
```

### using it on purpose

removes any files and also any subdirectories that become empty as a result :
```shell
git clean -f -d
```

> [!IMPORTANT] clean.requireForce = true !
> is required if the Git configuration variable clean.requireForce is not explicitly set to false .
### --dry-run or -n

If you ever want to see what it would do :
```shell
git clean -d -n
```

### with ignored files

```shell
git clean -n -d -x
```

### interactive clean or -i

```shell
git clean -x -i
```















