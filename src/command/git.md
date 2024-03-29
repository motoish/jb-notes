# Git

## Tag

### 1. create & push tag to remote branch

```sh
$ git tag {tag_name}
$ git push origin {tag_name}
```

### 2. delete local & remote tag

```sh
$ git tag -d {tag_name}
$ git push origin --delete {tag_name}
```

*引用: [第18話 便利なgit tagの使い方！コミットにタグをつけて管理しやすくしよう【連載】マンガでわかるGit ～コマンド編～](https://www.r-staffing.co.jp/engineer/entry/20201120_1)*

### 3. synchronize branch list

The `-p` flag means "prune". After fetching, branches which no longer exist on the remote will be deleted.

```sh
$ git fetch -p
```

## Branch

### 1. change local branch name

```sh
$ git branch -m {old_branch_name} {new_branch_name}
// change current branch name
$ git branch -m {new_branch_name}
```

### 2. change remote branch name

In fact, there is no change regarding the remote branch name.  
It's just to create a new branch with the same "git log", and then delete old remote branch.  

```sh
$ git branch -m {old_branch_name} {new_branch_name}
$ git push -u origin {current_branch_name}
$ git push origin :{old_branch_name}
```

**Example**  
input-1:

```sh
❯ git branch -m feature-tree master
❯ git push -u origin master
```

output-1:

```tex
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/motoish/self-notes/pull/new/master
remote: 
To github.com:motoish/self-notes.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

input-2:

```sh
❯ git push origin :feature-tree 
```

output-2:

```tex
To github.com:motoish/self-notes.git
 - [deleted]         feature-tree
```

### 3. pull remote branch

```sh
$ git branch -a
$ git checkout {the_same_branchName_with_origin}
```

::: {tip} Example

```sh
❯ git branch
* main
❯ git branch -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/feb
  remotes/origin/main
  remotes/origin/master
❯ git checkout feb
Switched to a new branch 'feb'
Branch 'feb' set up to track remote branch 'feb' from 'origin'.
❯ git branch
* feb
  main
```

:::

## Clone

### 1. clone from specific branch

```sh
$ git clone -b {branch_name} https://...{repository_address}...
```

## Rebase

### 1. rebase commits(squash) or change commit message(reword)

```sh
$ git rebase -i HEAD~{n}
< edit commits to drop, squash, fixup.. >
< edit commit messages >
$ git push origin {branch} -f
```

## Reset

### 1. reset HEAD, index and working tree

```sh
$ git reset --hard HEAD^
```

## Fetch

### 1. Update local branch forcefully

```sh
$ git fetch origin master
$ git reset --hard origin/master
```

### 2. Fech all remote branches

```sh
$ git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done
$ git fetch --all
$ git pull --all
```

## Stash

### 1. Stash the work

```sh
$ git stash
```

### 2. Apply stashes

```sh
$ git stash apply
```

### 3. Create a branch from a stash

```sh
$ git stash branch {branch_name}
```
