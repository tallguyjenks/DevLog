

## Configuration

- Great bash config for using git from [this thoughtbot article](https://thoughtbot.com/upcase/videos/git-customizing)

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

- A great tip to update your master branch return to the original branch you left and then merge changes. this is made as a git alias.
  - `!git checkout master && git pull && git fetch --prune && git checkout - && git merge master`
  - Aliased as `mup` for _"Master Up"_
  - The `!` is running it as a shell command as git aliases can only run 1 command. So this way we're still chaining commands
