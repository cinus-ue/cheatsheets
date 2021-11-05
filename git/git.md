# GIT CHEAT SHEET

## SETUP
```
$ git config --global user.name  "[firstname lastname]"
$ git config --global user.email "[valid-email]"
$ git config --global color.ui auto
$ git config core.ignorecase true // case sensitive
```

## CREATE REPOSITORY
```
$ git clone ssh://user@domain.com:repo.git
$ git init
```
## LOCAL CHANGES
```
$ git status 
$ git diff
$ git add .
$ git commit -am "[message]"
```

## COMMIT HISTORY
```
$ git log
$ git log -p [file]
```

## BRANCHS & TAGS
```
$ git branch -a
$ git tag [tag-name]
```

## UPDATE & PUBLISH
```
$ git push [alias] [branch]  / git push origin master 
$ git pull 
```

## MERGE & REBASE
```
$ git merge  [branch]
$ git rebase [branch]
$ git rebase --abort
$ git rebase --continue
```
## UNDO
```
$ git reset --hard HEAD
$ git revert [commit]
```
## LFS
```
$ git lfs track "*.zip"
$ git add .gitattributes
$ git lfs ls-files
```

## IGNORING PATTERNS
```
logs/ 
*.tmp
~$*.doc*
pattern*/
```