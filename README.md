# git cheatsheet

Common commands. Easy for future use.

## reset one file

```bash
git checkout HEAD -- my-file.txt
```

## reset to remote

```bash
git fetch origin
git reset --hard origin/master
```

## merge two commits into one

```bash
git log --pretty=oneline
a931ac7c808e2471b22b5bd20f0cad046b1c5d0d c
b76d157d507e819d7511132bdb5a80dd421d854f b
df239176e1a2ffac927d8b496ea00d5488481db5 a

git rebase --interactive HEAD~2
pick b76d157 b
pick a931ac7 c

pick   b76d157 b
squash a931ac7 c
```

## move git repository

```bash
git fetch origin
git remote add new-origin git@github.com:user/repo.git
git push --all new-origin
git push --tags new-origin
git remote rm origin
git remote rename new-origin origin
```

## remove local branches no longer on remote

```bash
git fetch -p && for branch in `git branch -vv | grep ': gone]' | awk '{print $1}'`; do git branch -D $branch; done
```

## local gitignore

```bash
.git/info/exclude
```

## remove a folder from git tracking

```bash
git rm -r --cached path_to_your_folder/
```

## update cached credential on macOS

```bash
git config --global credential.helper osxkeychain
```

## rewrite the most recent commit message

```bash
git commit --amend
```

## push a local Git branch to master branch in the remote

```bash
git push origin develop:master

git push <remote> <local branch name>:<remote branch to push into>
```

## show file differences between staging and the last file version

```bash
git diff --staged
```

## stash a single file

```bash
git stash push -m welcome_cart app/views/cart/welcome.thtml
```

## undo git add

```bash
git reset <file>
git reset # unstage all changes
```

## undo last commit

```bash
git reset --soft HEAD~1
```
