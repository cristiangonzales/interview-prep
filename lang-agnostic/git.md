Git Review
---
* Git is a distributed VCS that allows you to track changes and revert to previous changes
* Does not rely on central server to store all versions
* Every developer clones a local copy of the repo (hence, making it distributed)
* There is one central repo/Git server to commit changes
* What is a *bare* repository in Git?
  * Just contains version control information and no files or working tree, and contains the `.git/` subdirectory in the main/root directory of the repo
  * A *working* directory consists of a `.git/` subdirectory with all revision hisory and a working tree
* C is used in Git to reduce the overhead of runtimes associated with other high-level languages
* How to revert a commit that has already been pushed: `git revert <commit-id>`
* `git pull` versus `git fetch`?
  * `git pull` = `git fetch` + `git merge`
  * `git pull` pulls new changes and updates the target branch in the local repository
  * `git fetch` pulls new commits and stores it in a new branch
* Staging area/index: Where working changes are added on your local repo (changes are in the staging area, ready to be commited when you `git add` them)
* `git stash` takes the working directory (modified gtracked files and staged changes) and saves it in a stack of unfinished changes
  * `git stash drop` will pop an item off this stack (or remove a specific item)
* How to find a list of files that has changed in a particular commit
  * `git diff-tree -r {hash}`
    * `-r` flag lists individual files rather than root directory names [of files] only
  * `git diff-tree -no-commit-id -name-only -r {hash}`
* Purpose of `git config`: change git configuration (username/email associated with the developer)
* Commit objects contain
  * Set of files
  * Reference to parent commit object
  * SHA1 name, a 40-character string that uniquely identifies the commit object
* Squashing the last n commits into a single commit
  * Write a new commit message from scratch: `git reset -soft HEAD~n && git commit`
* `git bisect <subcommand> <options>`
  * Used to find commit that introduced bug using binary search
  * User tells it a "bad commit" that is known to contain the bug and a "good" commit known before the bug, and it will ask if subsequent commits are "good" or "bad" between this reange until you find the bad commit
* *Feature branching*: All changes for that feature kept within your branch, integrated only when the feature is done (into the master branch)
* How to check which branches have/haven't been merged with the master branch
  * `git branch -merged`
  * `git branch -no-merged`
* `git rebase`: merge another branch into the branch you are currently working and move all commits ahead of the rebased branch to the top of the git history
