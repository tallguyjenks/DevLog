

### git worktree

```bash
git worktree add master
```

- Create a bare repo and start making new worktrees [[import.git#^faf0c6]]
  - This means that a copy of the repo files is made for each worktree at the source commit that the bare repo was made from
  - Worktrees make it easier to open multiple repo branches at once under a unified workspace for easy switching of work between multiple features
  - Doesn't lend itself to easy updating.
    - The bare repo doesn't `git pull` itself but the worktrees after creation can use `git pull` but this is not ideal. The bare repo is basically frozen at a single commit for all new worktrees made.

## Making work-trees

- [ThePrimeagen](https://youtu.be/2uEqYw-N8uE)

```bash
git clone --bare <repo url.git> <name of the folder to create>
# ex:
git clone --bare git@github.com:tallguyjenks/CV.git CV


# makes a bare repo of my resume
# there's nothing in it, none of the files from the repo just git stuff
# THEN

git worktree add master
git worktree add test
git worktree add feature

# it takes the current commit at the HEAD of the repo (git pull at you're at the most recent) and this way # you're working with 3 folders basically 3 branches of the same repo but simultaneously. NO SWITCHING BACK & AND FORTH 🤯️🤯️🤯️
```
