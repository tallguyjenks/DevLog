---
title: Git
tags: tools
---

## ^^Resources^^
### https://git-scm.com/docs
## ^^Commands^^
### Pretty Log Output (_PLOG_)
#### 
```bash
git config --global  alias.plog "log --graph --format='%Cgreen%h %Cred%aN%Cblue%d%Creset %s %C(yellow)(%cr)%Creset'"
```
## ^^Configuration^^
### Great bash config for using git from [this thoughtbot article](https://thoughtbot.com/upcase/videos/git-customizing)
#### 
```bash
# No arguments: `git status`
# With arguments: acts like `git`
g() {
  if [[ $# > 0 ]]; then
    git $@
  else
    git status
  fi
}

# Complete g like git
compdef g=git
```
### A great tip to update your master branch return to the original branch you left and then merge changes. this is made as a git alias.
#### `!git checkout master && git pull && git fetch --prune && git checkout - && git merge master`
#### Aliased as `mup` for _"Master Up"_
#### The `!` is running it as a shell command as git aliases can only run 1 command. So this way we're still chaining commands
## ^^Troubleshooting^^
### Removing a file from git history from [this SO article](https://stackoverflow.com/questions/307828/how-do-you-fix-a-bad-merge-and-replay-your-good-commits-onto-a-fixed-merge/15729420#15729420)
## ^^General Info^^
### The `git checkout` command was replaced by `git switch` in git v2.23 as `git checkout` was apparently too overloaded.
### **Rebasing:** essentially takes a set of commits, "copies" them, and plops them down somewhere else.
#### if you have 2 parallel branches and you rebase 1 onto the other it essentially looks for their common origin point (commit), takes the "base" of that branch and places the base at the end and right on top of branch you're Rebaasing.
#### Then the branch that was the recipient of the rebasing needs to be updated so you rebase that onto the branch that was just rebased. This just moves the pointer to the tip of the merged branches
#### Interactive Rebasing with `git rebase -i <commit hash>` make it a more interactive way to move around and reorder commits
### **HEAD** is simply the name of the currently checked out commit hash
#### each commit is a pointer to the repo at a point in time
##### each branch is a named pointer to a particular commit
### **Relative References** using `^` and `~` to traverse commits in the `git log` so that you don't need to type even the minimum 6 characters of the commit hash.
#### `^` when given the name of a commit hash/branch name it will refer to the parent commit: `main^`
##### These can be stacked too so you can refer to grandparent commit with `main^^`
##### can also use with **HEAD** to traverse from current point: `git checkout HEAD^`
#### `~` will let you specify a number of commits to travel back instead of `git checkout HEAD^^^^` you can use `git checkout HEAD~4` to traverse 4 commits backward
### **Forcing Branches** You can move what commit a branch is referencing with something like:
#### `git branch -f myBranch locationToMoveItTo`
### **Reversing Commits** There are at least 2 ways to do this `git reset` and `git revert`
#### `git reset` move the branch backwards in time
#### `git revert` move the branch backwards in time and acts like the commit never even happened
### `git cherry-pick <commit hash> <commmit hash> ...`
#### ![2021_04_27_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e383e15d4ae-be18-4a8f-acb1-c3e3cc45cbaf2021_04_27_image.png?Expires=4773158404&Signature=Tz~VjOeuALHDo~htM6IzYhAjMY6xItAyynFz4MnJhk1JuwNeQqhMgDmARACUARHT1pgrWRWvtdRuxTBPBVCZGtGwqJMN~yyT2xn12PKBGixRgjMdf4R~Q8m9wsm58~mjXNoL4M5bVb-WbGmV1m9RCOMw9UwiFb0nqN7ms7mroIC3MSZmlvDrbz8LpJPWkp~KlacU9ZeF6knUV2doFho0cckWfW9LsXiJ3y3goCEEleYOjC9WWDwNBDciRKukUXQZEeH87pkLGlr2NB2ZhYat4NhwlfNbdgRye~iTD7WMMX-p5hOYzuuFCxt0-7H8-5wboemZCELbhveVxvwsP70vSQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
#### `git cherry-pick c2 c4`
#### ![2021_04_27_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e382d520a7f-8f7e-4611-8688-f577103228a12021_04_27_image.png?Expires=4773158436&Signature=OVIU3Ae4tfpm0qsdn6a7~pHwIgTHuqNKtnIO7zb46Q2ccC~mLbV8RHgXErVUjRLjeYX3Ya80cR6sHTwqsFx~IW9ejEilesi1YNAr2UNeWN4uw8G8n7PxNHO-v30ZCMEsPfU36liohp6RoGfdpl5v-DfRrlREtKy7jUIofPrG0s0bs7QTIywuW-bB85LxFlI4BO7cavXXqlJhf5SRVVDKg7DSnmxJ4K4v-oxZGfzuBhAfsvU7Vh60JS1CjDI~zX-S7tZ8d5t~5dDl8FR0~J1L2eskouayjFNAIFtSpJ5cIuPH3gHIMXPgXF4UuFl6hv8BTu1vrPiXN5uG~X3Ck3YCyQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### **Tagging** To tag commits as a project milestone or something the commands are very simple
#### `git tag v1 <commit hash>` will tag what ever referenced commit hash with the tag _"v1"_
#### `git tag v1` will tag what ever commit hash **HEAD** is on with the tag _"v1"_
### `git describe <ref>` If no ref is provided it will just look at wherever HEAD is. This can, however, be used on Tags.
#### If you have a tag on the first commit of the repo such as `0.1` with a message of `initialized repository` and then ran the command `git describe` all it would tell you is something like:
##### _"0.1-62-g07f34f4"_
###### _0.1_ for the tag
###### _62_ for the commits since that tag
###### _g07f34f4_ is the hash being described (your current one that hasn't been committed yet)
#### ![2021_04_27_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e38150b5d0a-c5e6-401b-b6ee-39fb4031aabe2021_04_27_image.png?Expires=4773160079&Signature=E6p6WMlzNrJ7yVeIR0bADUCYsOUg2QaJAYBnlyHNxG7fAK2XqQete8ZYAQ9yf7rxztozxD8Ya2DDk9GsITJuMpDHRvSaQePFgNkGYhAeflkD-ZDqntqPVNWsyD-TkxdX5Z1WfAhGcR1L6ixWbwAXnOgGa1YRFeqsyCwJOdBSWJfGHbJAJMmAgjQyS4~1-NI7K2ZXX-WYu-hg0GoN4QZ2BiNt4JdrWUN2~flky49CNhFNdZplz1eBLSr~m19CTHNIX3x8kPjHNMO0qzRXaTz6ersk5I2vPpzwcqT8MXoI77suIXgH9nsdFEu4fkxUu5Ac2nEeg8CbcOe91C18Hdi7oQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA){:height 256, :width 543}
