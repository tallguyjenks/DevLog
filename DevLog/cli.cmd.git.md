---
id: jak8s12bepa7jt6n3pem8ro
title: Git
desc: ''
updated: 1641185553213
created: 1641105063853
stub: false
isDir: false
---


## General Info

- The `git checkout` command was replaced by `git switch` in git v2.23 as `git checkout` was apparently too overloaded.
- **Rebasing:** essentially takes a set of commits, "copies" them, and plops them down somewhere else.
  - if you have 2 parallel branches and you rebase 1 onto the other it essentially looks for their common origin point (commit), takes the "base" of that branch and places the base at the end and right on top of branch you're Rebasing.
  - Then the branch that was the recipient of the rebasing needs to be updated so you rebase that onto the branch that was just rebased. This just moves the pointer to the tip of the merged branches
  - Interactive Rebasing with `git rebase -i <commit hash>` make it a more interactive way to move around and reorder commits
- **HEAD** is simply the name of the currently checked out commit hash
  - each commit is a pointer to the repo at a point in time
    - each branch is a named pointer to a particular commit
- **Relative References** using `^` and `~` to traverse commits in the `git log` so that you don't need to type even the minimum 6 characters of the commit hash.
  - `^` when given the name of a commit hash/branch name it will refer to the parent commit: `main^`
    - These can be stacked too so you can refer to grandparent commit with `main==`
    - can also use with **HEAD** to traverse from current point: `git checkout HEAD^`
  - `~` will let you specify a number of commits to travel back instead of `git checkout HEAD====` you can use `git checkout HEAD~4` to traverse 4 commits backward
- **Forcing Branches** You can move what commit a branch is referencing with something like:
  - `git branch -f myBranch locationToMoveItTo`
- **Reversing Commits** There are at least 2 ways to do this `git reset` and `git revert`
  - `git reset` move the branch backwards in time
  - `git revert` move the branch backwards in time and acts like the commit never even happened
- `git cherry-pick <commit hash> <commmit hash> ...`
  - `git cherry-pick c2 c4`
- **Tagging** To tag commits as a project milestone or something the commands are very simple
  - `git tag v1 <commit hash>` will tag what ever referenced commit hash with the tag _"v1"_
  - `git tag v1` will tag what ever commit hash **HEAD** is on with the tag _"v1"_
- `git describe <ref>` If no ref is provided it will just look at wherever HEAD is. This can, however, be used on Tags.
  - If you have a tag on the first commit of the repo such as `0.1` with a message of `initialized repository` and then ran the command `git describe` all it would tell you is something like:
    - _"0.1-62-g07f34f4"_
      - _0.1_ for the tag
      - _62_ for the commits since that tag
      - _g07f34f4_ is the hash being described (your current one that hasn't been committed yet)
