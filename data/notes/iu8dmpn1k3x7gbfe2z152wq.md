

## git stash

```bash
git stash push 
```

- like an array method this will create a _Box_ and put all your changes inside of it and shove that _box_ in the corner of the room and give you a clean working tree.
- The _box_ is now portable and you can switch to another branch and open the _box_ there and take out all of the changes.

```bash
git stash pop
```

- This opens the _box_ and applies all those stashed changes to the current working tree.
- This is very useful for the situations where maybe you made a bunch of changes and you forgot to make a new branch and you're still on `master`/`main` and you want to move all those changes to the actual feature branch.

## Saving and moving changes

```bash
# say you're on master, and you have changes to docs and you're about to make a commit, but you realize "oh crap, I'm still on master, I needed to put this on a feature branch!" 
# you can run 
git stash push 
# to basically package up all those uncommitted changes into a "box" and shove it into a corner returning to a master branch that is a mirror of remote master (CLEAN!) 
# then make your branch, switch to it and run 
git stash pop 
# to grab your changes and put them onto the current working branch. 
```

