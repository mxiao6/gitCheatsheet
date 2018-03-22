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

## moving git repository
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
