# Repository
### What are `repositories`?

A “**repo**” (shorthand for “**repository**”), is essentially one project. It has:
- One **history**
- One or multiple **branches**
	- One `main` or `master` (deprecated name) branch
- One or multiple **collaborators**
- (Optional) one or multiple **submodules**

### What is a `submodule`?
A submodule is essentially a repository, embedded in another repository.

The main repository will track which version of the submodule it’s currently using, so that you can keep updating the submodule repository without affecting the main one, until it’s ready.

## How to create a repository
### On GitHub...
- Create the repository on **GitHub**

Screenshot 2024-11-14 alle 11.26.37.png

Screenshot 2024-11-14 alle 11.31.01.png

### Locally...

- `git init` in your project’s folder, to **initialise a new empty repository**

Screenshot 2024-11-14 alle 11.23.24.png

Now it’s time to link the GitHub repository to the local one we’ve just created.

- `git remote add origin <link>`

Screenshot 2024-11-14 alle 11.42.39.png

> Here’s what this does:
- `git remote add` creates a new **remote**, called `origin`
	- A **remote** is basically an link to a service hosting your repository.
	- `origin` is the name we gave to this link. We might as well name it `github` and nothing would change, but `origin` is conventional.
- The `link` afterwards varies depending on your authentication mechanism.
	- **SSH authentication**: `git@github.com:<username>/<repo>.git`
	- **HTTPS authentication**: `https://github.com/<username>/<repo>.git`

Let’s **add our files** to it.

- `git add -A` to **add all of the files**
> If you want to add just a file or a folder, you can use a **file path** or a **glob**; for example:
>	- `git add ./src/main.c` for one file
>	- `git add ./src/**/*.c` for every file ending in `.c`

Screenshot 2024-11-14 alle 11.25.05.png

We need to **create a commit** to push changes.

- `git commit -m <message>` to **create a commit**

Screenshot 2024-11-14 alle 11.25.45.png

Now we have to **push** our commit.

- `git push origin main`

Screenshot 2024-11-14 alle 11.42.56.png

> Here’s what this does:
- `git push` tells Git to **push a commit**
- `origin` is the **name of the remote**; this tells Git to push to that specific GitHub repository.
- `main` is the **branch’s name**. Conventionally, `main` (or `master`, though that’s now deprecated) is used.

## Updating an existing repo
Let’s clone the repository.

- `git clone git@github.com:ZephyrCodesStuff/hello-markdown.git`
> ⚠️ Again, this part varies for your authentication mechanism. For SSH, I’m using an SSH-like link.
- `cd hello-markdown` to enter the directory

Now, simply follow all steps from `git add` to `git push`, in order to:
1. Add your changes: `git add -A`
2. Create a commit: `git commit -m <message>`
3. Push them: `git push origin <branch>`

> ⚠️ Pushing directly on `main` is not always recommended. Consider following a **branching model** (as explained in [[Branch]])

## Exercise: clone the `git good` repo!
1. **Open** a terminal
2. **Clone** the repo: `git clone git@github.com:zephyrcodesstuff/git-good.git`
3. **Enter** the folder: `cd git-good`

✨ There you go; simple as that!