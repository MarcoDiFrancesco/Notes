## New commands

_git checkout_ has been splitted to `git switch` and `git restore` [link](https://stackoverflow.com/a/57266005/7924557)

`--` is the argument disambiguation [link](https://git-scm.com/docs/git-checkout#_argument_disambiguation)

## Files
`git update-index --assume-unchanged <path>` ignore changes of a commited file

`git reset` unstage all files
-   `<path>` unstage file
-   `--hard` **DISCARD** all files, both in staged and not
-   `--hard <path>`, `--soft <path>` do not work

`git restore <path>`
-   (`--worktree` default) **DISCARD** specified file changes if unstaged (from _git checkout -- foo_)
-   `--staged` unstage file (from the old _git reset file_)
-   `--worktree --staged` unstage and discard changes

`git rm <file>` remove physically
-   `--cached` just from index

## Branch
`git push origin --delete master` delete branch
-   `--force` if was not merged

![](https://i.imgur.com/9lBrILX.png)

## Rebase
`git rebase master` updates branch to last commit
`git rebase -i <sha>` delete merge commit [link](https://stackoverflow.com/a/17577876/7924557)
