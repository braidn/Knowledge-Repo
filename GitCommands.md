##Most Used Commands

* Checkout and track remote repo: `git checkout -t origin/branchName`
* Delete remote branch: `git push origin :branchName`
* Rename a branch: `git branch -m <branch_you_want_to_rename> <new_name>`
  * if already on that branch: `git branch -m <new_branch_name>`
* Create a patch: `git diff > changes.patch`
  * this patch can then be applied to any project using: `git apply changes.patch`


##GitHub or _HUB_

* Turn issue into pr: `hub pull-request -i issue# -h owner:name/of/branch`