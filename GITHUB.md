
- undo a commit and KEEP the files `git reset --soft HEAD~1`. the notation `HEAD~1` means  previous to last commit *last commit*.
- get remote url, in ssh or https format according to settings, `git remote show origin`
- set repo remote url (origin) `git remote set-url origin git@github.com:account/repo.git` 
- download submodules of an already downloaded repo `git submodule update --init`
- store token and username `git config --global credential.helper store`
