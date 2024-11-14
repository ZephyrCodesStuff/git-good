# Repository management

### Getting a local copy of a repo

- **SSH authentication**: `git clone git@github.com:IcarusPoliTO/repo-name.git`
- **HTTPS authentication**: `git clone https://github.com/IcarusPoliTO/repo-name.git`

### Getting the new changes locally
```bash
# Update the repo's metadata
$ git fetch

# Actually get the changes to the files
# NOTE: `main` is the branch name
$ git pull main
```

https://wac-cdn.atlassian.com/dam/jcr:9c543e76-04df-429e-af48-43a5276d7f4f/04-06%20Git%20pull%20discussion.svg?cdnVersion=2420

### Pushing changes to a repo
Each repository update is packed into **commits**. A **commit** is a bundle of changes (additions or deletions).

Screenshot 2024-11-14 alle 11.13.47.png

Screenshot 2024-11-14 alle 11.15.18.png

#### Commit contents
- **Author**
- A **hash** that identifies the commit
- A **commit message** detailing what was done
- **Additions** and/or **deletions**
- Date and time of **creation**
- (Optional) signature verification 

### How commits work
Commits operate on a **file-level**:
1. You change some files
2. You `git add` the files you want to put into your commit
3. You create the commit: `git commit -m <message>`
4. You the commit: `git push origin main`

### Commit history
Each repository keeps a history of all of the changes happening, at a **commit-level**.

This means that you may skip back and forth between commits as you please.

```bash
$ git checkout <commit_hash>
```

This will bring your local copy to the specified commit.

### Undoing changes
If you want to revert the state of the repository back a couple commits, you can use `git reset`:

- Find the commit you want to `reset` to:

```bash
$ git log --oneline
> e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
> 52418f7 Just a regular update, definitely no accidents here...
> 9a9add8 (origin/master) Added .gitignore
```

- Pick the commit you want as the last one (basically the last “good” commit):

```
9a9add8
```

- Reset to that commit

```bash
$ git reset 9a9add8  
```

- Update the remote repository

```bash
$ git push --force
```

> ⚠️ WARNING! This will delete every commit after the one you picked.\
\
**Make sure nobody is working on those commits before nuking them like this!**

### Switching branches
```bash
$ git switch fix/something
```

To **create** the branch, if it doesn’t exist, **add the `-c` flag after `git switch`**, as follows:
`git switch -c ...`

### Merging a branch’s changes into another one (usually `main`)

https://wac-cdn.atlassian.com/dam/jcr:7afd8460-b7bf-4c42-b997-4f5cf24f21e8/01%20Branch-2%20kopiera.png?cdnVersion=2420

Merging will **create a commit** that brings those changes into the desired branch.

https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=2420

- Move to the destination branch

```bash
$ git checkout main
```

- Merge the source branch

```bash
$ git merge fix/something
```

> The Git Terminal should now guide you to write a message cor the merge commit.

- Delete the unnecessary source branch

```bash
$ git branch -d fix/something
```

- Push the merge commit

```bash
$ git push main
```
