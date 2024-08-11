# Initializing a git repository

open a terminal and go to your project folder, example :
```shell
cd ~/coding/my-project
```

and then enter this command :
```shell
git init
```

add a few files like README.md and then commit :
```shell
git add README.md
git commit -m "Initial project version"
```

# cloning a repository

with https:
```shell
git clone https://path_to_repository
```

with ssh, for example github.com :
```shell
git clone git@github.com:username/repository_name
```

If you want to clone the repository into a directory named something other than libgit2, you can specify the new directory name as an additional argument:
```shell
git clone https://github.com/libgit2/libgit2 mylibgit
```

it will create `.git/mylibgit` directory in `my-project` folder .

# Inspecting Status

to inspect the current state of your repository go to your project folder and enter :
```shell
git status
```

then hit `Enter` .

# Tracking a new file

```shell
git add <file_name>
```

> [!IMPORTANT] ## Add Directory !
> The git add command takes a path name for either a file or a directory; if it’s a directory, the command adds all the files in that directory recursively.

# Short Status

```shell
git status -s
```

```shell
git status --short
```

# Git Ignore

```shell
cat .gitignore
```

```gitignore
/build
/dist
*.[oa]
```

example :

```gitignore
# ignore all .a files
*.a
# but do track lib.a, even though you're ignoring .a files above
!lib.a
# only ignore the TODO file in the current directory, not subdir/TODO
/TODO
# ignore all files in any directory named build
build/
# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt
# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```

# git diff

for unstaged changes :
if you wanna see what you have done in files generally :
```shell
git diff
```

or in particular file :
```shell
gid diff <file_name>
```

for staged changes :
```shell
git diff --staged
```

```shell
git diff --cached
```

# Commiting

```shell
git commit -m "message"
```

# Skipping git add

```shell
git commit -am "message"
```

# Removing Files

```shell
git rm <path_to_file>
```

```shell
git rm --cached <path_to_file>
```

# Moving Files / Renaming Files

```shell
git mv file_from file_to
```

# Viewing the Commit History - git log

```shell
git log
```

## --patch
to show the details of commit with `-p` or `--patch` and you can limit the number of commits shown with `-n` like `-2` :
```shell
git log -p -2
```

## --stat
abbreviation status :
```shell
git log --stat
```

## --pretty

```shell
git log --pretty
```

### oneline value

```shell
git log --pretty=oneline
```

### format value

```shell
git log --pretty=format:"%h - %an, %ar : %s"
```

#### Useful Specifiers 

| **Specifier** | Description of Output                           |
| ------------- | ----------------------------------------------- |
| %H            | Commit hash                                     |
| %h            | Abbreviated commit hash                         |
| %T            | Tree hash                                       |
| %t            | Abbreviated tree hash                           |
| %P            | Parent hashes                                   |
| %p            | Parent hashes                                   |
| %an           | Author name                                     |
| %ae           | Author email                                    |
| %ad           | Author date (format respects the --date=option) |
| %ar           | Author date, relative                           |
| %cn           | Committer name                                  |
| %ce           | Committer email                                 |
| %cd           | Committer date                                  |
| %cr           | Committer date, relative                        |
| %s            | Subject                                         |

## --graph option

```shell
git log --graph
```

## Common Options

| **Option**      | **Description**                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| -p              | Show the patch introduced with each commit.                                                                                                 |
| --stat          | Show statistics for files modified in each commit.                                                                                          |
| --shortstat     | Display only the changed/insertions/deletions line from the --stat command.                                                                 |
| --name-only     | Show the list of files modified after the commit information.                                                                               |
| --name-status   | Show the list of files affected with added/modified/deleted information as well.                                                            |
| --abbrev-commit | Show only the first few characters of the SHA-1 checksum instead of all 40.                                                                 |
| --relative-date | Display the date in a relative format (for example, “2 weeks ago”) instead of<br>using the full date format.                                |
| --graph         | Display an ASCII graph of the branch and merge history beside the log output.                                                               |
| --pretty        | Show commits in an alternate format. Option values include oneline, short,<br>full, fuller, and format (where you specify your own format). |
| --oneline       | Shorthand for --pretty=oneline --abbrev-commit used together.                                                                               |


## Limiting Log Output

```shell
git log --since=2.weeks
```

This command works with lots of formats — you can specify a specific date like "2008-01-15", or a relative date such as "2 years 1 day 3 minutes ago".

You can also filter the list to commits that match some search criteria. The --author option allows you to filter on a specific author, and the --grep option lets you search for keywords in the commit messages.

> [!INFO]
> You can specify more than one instance of both the --author and --grep search criteria, which will limit the commit output to commits that match any of the `--author` patterns and any of the `--grep` patterns; however, adding the `--all-match` option further limits the output to just those commits that match all `--grep` patterns.

## -S option
Another really helpful filter is the -S option (colloquially referred to as Git’s “pickaxe” option), which takes a string and shows only those commits that changed the number of occurrences of that string. For instance, if you wanted to find the last commit that added or removed a reference to a specific function, you could call:
```shell
git log -S "function_name"
```

The last really useful option to pass to git log as a filter is a path. If you specify a directory or file name, you can limit the log output to commits that introduced a change to those files. This is always the last option and is generally preceded by double dashes (--) to separate the paths from the options:
```shell
git log -- path/to/file
```




previous [[00 - Getting Started]]
next [[]]









