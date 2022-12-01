## New commands

_git checkout_ has been splitted to `git switch` and `git restore` [link](https://stackoverflow.com/a/57266005/7924557)

### Unstage - Discard
`git reset` unstage all files
-   `<path>` unstage file
-   `--hard` **discard** all files, both in staged and not
-   `--hard <path>`, `--soft <path>` do not work

`git restore <path>`
-   (`--worktree` default) **discard** file changes if unstaged (from _git checkout -- foo_)
-   `--staged` unstage file (from the old _git reset file_)
-   `--worktree --staged` unstage and discard changes

### Delete file
`git update-index --assume-unchanged <file>` ignore changes of a commited file
`git rm --cached <file>` removes remote file

### Delete branch
`git branch --delete master`
`git push origin --delete master`
-   `--force` if was not merged

### Rebase ???
`git rebase master` updates branch to last commit
`git rebase -i <sha>` delete merge commit [link](https://stackoverflow.com/a/17577876/7924557)
