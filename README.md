# Index
Crash course on Git and the Version Control System (VCS).

**Duration**: ~1.5 hours (approx.)


### Topics
- What is **[Version control](Version%20control.md)**
	- Purposes and benefits
- What is **[Git](Git.md)**
	- Software used and how to download them on major OSes (and in particular Linux / Ubuntu)
		- **Main**
			- `git` (terminal)
			- GitHub Desktop
			- Git integration of Visual Studio Code
		- Secondary / paid
			- Tower
			- GitKraken
- What is a **[Repository](Repository.md)**
	- **Single-repo** model
	- Poly-repo model
	- **Submodules**
	- **Repository [Management](Management.md)**
		- Creating a new repo
		- Updating an existing one
- What are **[Branch](Branch.md)es**
	- Branching models
		- Git flow model
			- Benefits in CI/CD and large-scale projects
		- Feature-branch model
			- Advantages in small- to medium-scale projects
	- **[Pull request](Pull%20request.md)s**
- How an **[Organization](Organization.md)** works
	- Teams
	- GitHub Projects
		- Kanban boards
- How to update a **repo**
	- **[Authentication](Authentication.md)**
		- Personal Access Token
		- SSH public key
	- `git commit`
		- Commit signing -S
			- GPG and SSH public key
		- Syntax commit messages -m
			- ≤ 50 char in the first line (title)
			- n char in subsequent ones (message)
			- **Co-authoring** a commit
				- Visual Studio Code - [Live Share](Live%20Share.md)
- Main commands and functions
	- **Merge**: `git merge` of one branch into another
		- **[Merge conflicts](Merge%20conflicts.md)** and how to handle them
		 - `git stash`
	- **Reset**: `git reset` some commits
	- **Checkout**: `git checkout` to a specific commit
	- **Switch (branch)**: `git switch` to a specific branch
- [Thank you](Thank%20you.md)