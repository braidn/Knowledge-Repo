### Most Used Commands

* Remove a commit: `git rebase -i sha_to_be_removed~1`
  * This will open a rebase up to the commit you want removed (will be top of list)
  * if this is done on a merge bubble, all of the bubble will be expanded with all commits, not just one.
* Checkout and track remote repo: `git checkout -t origin/branchName`
* Delete remote branch: `git push origin :branchName`
* Rename a branch: `git branch -m <branch_you_want_to_rename> <new_name>`
  * if already on that branch: `git branch -m <new_branch_name>`
* Create a patch: `git diff > changes.patch`
  * this patch can then be applied to any project using: `git apply changes.patch`

### Diffing

* If you need to omit files from a git diff:
  1. `git config diff.nodiff.command /usr/bin/true` the `--global` flag can be used if needed globally
  1. add: `irrelevant.file_name    diff=nodiff` lines to .git/info/attributes
* If two buffers are open they can be diffed by performing:
  * `windo.diffthis` and turned off with `windo.diffoff`

### Branching

* to rename a target branch: `git branch -m <oldname> <newname>`
* to rename current branch: `git branch -m <newname>`

### GitHub or _HUB_

* Turn issue into pr: `hub pull-request -i issue# -h owner:name/of/branch`

### Rewriting

#### Changing files included in previous commit

1. git-checkout <bad-commit>
   ... make your changes ...
2. git-commit --amend -v
3. git-rebase --onto HEAD <bad-commit> <checked-out-branch>