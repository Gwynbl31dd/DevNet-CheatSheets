# Git cheatsheet

## Basic

### Commits

Commit 

```
git commit
```

Detached HEAD

```
git check <commit_hash>
```

HEAD: Currently checkout commit

Check the logs

```
git log
```

Go back one commit from a branch

```
git checkout <branch_name>^
## Works also with ^^, ^^^,...
```

Go back one commit from current commit

```
git checkout HEAD^
## Works also with ^^, ^^^,...
```

Go back several commit

```
git checkout <commit_branch_head>~<number>
```

### Reset

Reset a commit (The commit never happened.. But cannot be shared with remote)
```
git reset
# example: git reset HEAD^
```

```
git revert
# example: git revert HEAD
```

### Branches

branch early, and branch often 

Create a branch and move to it

```
git branch <branch_name>
git checkout <branch_name>
```

or 

```
git checkout -b <branch_name>
```

Merge branches

```
# When on the branch (with a *)
git merge <branch_name>
```

Git Rebase (Keep the commit history instead of a simple merge)

```
git rebase <branch_name>
```

Interactive rebase

```
git rebase -i
# Example git rebase -i HEAD~4
```

Branch forcing

Reassigne a branch 

```
git branch -f <branch_name> <commit>
```

### Tags

```
git tag <tag> <branch>
```

## Advance

### Cherry-pick

```
git cherry-pick <Commit1> <Commit2> <...>
```

### Change commit history

amend change a commit (Technically, creates a new commit)

```
git commit --amend ...
```

### Describe

```
git describe <ref>
# generate an output: <tag>_<numCommits>_g<hash>
# where tag is the closest ancestor tag in history, numCommits is how many commits away that tag is, and <hash> is the hash of the commit being described.
```

### Checkout to anther parent

```
git checkout <ref>^<parent>
# example: git checkout HEAD^2
# example 2: git checkout HEAD~^2~2
```

## Remote

```
git clone <url>
```

Only download the changes (And put them in origin)

```
git fetch
```

Fetch only specific branch

```
git fetch <remote> <branch>
```

Specify where to fetch

```
git fetch <remote> <source>:<destination>
```

Download the changes and sync them (Just like git fetch and it merge)

```
git pull
# Can also rebase with git pull --rebase
```

publish (default behavior depends on your push.default)

```
git push
```

```
git push <remote> <name>
```

Push to another branch 

```
git push <remote> <source>:<destination>
# Example: git push origin foo^^:main
```

Delete a remote branch

```
git push <remote> :<destination> 
#This pushed nothing to the remote
```
