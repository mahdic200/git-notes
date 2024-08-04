
> [!SUCCESS] # JUST ubuntu !
> the notes in this note :) is just for ubuntu OS and configurations like telling git what editor to use maybe differ to other systems like Windows . so just read the book for those particular parts .

# Inspection settings / configurations

You can view all of your settings and where they are coming from using:
```shell
git config --list --show-origin
```
# Git config file location

depends on your OS . `[path]/etc/gitconfig` or  `~/.gitconfig` or `~/.config/git/config` or maybe you overwrite all system configurations and use `--local` option to store a local git repository configuration in your project folder in `.git/config` .

# Initial git configurations

## your Identity

open a terminal and run this command :
```shell
git config --global user.name "your_name"
```

```shell
git config --global user.email "your_email"
```

## default editor

tell git what editor to use , for example I always use Vscode as my default text editor :
```shell
git config --global core.editor code
```

## default branch name

tell git what name to use as default branch name , for example I always use master :
```shell
git config --global init.defaultBranch master
```

## checking your settings

to check your settings :
```shell
git config --list
```

you can also check what Git thinks a specific key's value is by typing `git config <key>` :
```shell
git config user.name
```

> [!INFO]
> Since Git might read the same configuration variable value from more than one file, it’s possible that you have an unexpected value for one of these values and you don’t know why. In cases like that, you can query Git as to the origin for that value, and it will tell you which configuration file had the final say in setting that value:
```shell
git config --show-origin rerere.autoUpdate
```

# Getting help

```shell
git help <verb>
```

```shell
git <verb> --help
```

```shell
man git-<verb>
```

more concise and abbreviated :
```shell
git <verb> -h
```

next [[01 - Git Basics]]






























