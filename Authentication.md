# Authentication
The first thing to do is to **authenticate with GitHub**. This can be done in two ways:
- SSH, with a private key (preferred)
- HTTPS, with a Personal Access Token (PAT)

### Git configuration (independent of login)
1. `git config --set user.name <username>`
> ℹ️ This is the name your commits will show up as

2. `git config --set user.email <user@domain.com>`

### HTTPS authentication
When you run a `git pull` or a `git fetch`, Git will ask for your password.

> https://github.com/settings/tokens

Screenshot 2024-11-13 alle 09.05.50.png

> ⚠️ When you generate a token, GitHub will only display it once. Make sure to store it somewhere safe!

Here you can generate a Personal Access Token, to then copy and paste into the Terminal.

> Note: the terminal will NOT display the token, for privacy reasons.

### SSH authentication
Generate an SSH key-pair, as follows:

```bash
$ ssh-keygen -t ed25519 -C "user@domain.com"
```

Follow the guided procedure with the `ssh-keygen` tool and finish creating a key.

The tool will then have generated the two important files:
- `id_ed25519.pub`: the **public** key we’ll upload to GitHub
- `id_ed25519`: the **private** key we **<u>keep locally!</u>**

> https://github.com/settings/ssh/new

This is where you’ll add a new SSH **public** key that GitHub will accept the private counterpart for.

Screenshot 2024-11-13 alle 09.11.49.png

Finally, **add the new SSH key** to your SSH agent:

```bash
# Start the agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid XXXXX

# Add the key
$ ssh-add ~/.ssh/id_ed25519
```

> If you don’t want to run the `ssh-agent` every time, you may add the command above to start it into your `~/.bashrc` / `~/.zshrc` file, to have it run automatically.

#### Why pick SSH for `git` authentication?
- Commit signing with the same key
- More versatile than a Personal Access Token
- More private (encrypted secret — SSH key never leaves your machine)