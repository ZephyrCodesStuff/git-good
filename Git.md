# Git
Git is one of the multiple types of Version Control Systems (the other most notable ones being Mercurial, Subversion and Perforce).
> You’ll only encounter those if you ever deal with game development in a company

### How do we get it?
The installation is very straightforward. On Linux machines, all you have to do is use your distro’s package manager, and install the desired software.

#### Wait, there’s more?
Yup — the baseline version of Git is simply named `git` and it’s a CLI (command-line interface) software.

Some people might find it tricky and, if you don’t know what you’re doing and mindlessly copy-pasting commands from StackOverflow, you could easily nuke your entire codebase.

For this reason, there’s multiple **GUI** (graphical user interface) **programs** which wrap Git’s functionality and allow for beginners to use it in a safer manner.

The most notable one is **GitHub Desktop**, though there are multiple alternatives for all OSes, such as **Tower**, or **GitKraken** (used in businesses).

#### Installing a flavour of Git
On Ubuntu:

```bash
sudo apt-get install git
```

On Arch Linux

```bash
sudo pacman -Sy git
```

On macOS:

```zsh
brew install git
```

### Installing GitHub Desktop
The commands aforementioned install the baseline CLI version of `git`, but if you want something like **GitHub Desktop** (recommended), you’ll have to run the following:

```bash
## Get the @shiftkey package feed (so Ubuntu can find the package)
wget -qO - https://apt.packages.shiftkey.dev/gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/shiftkey-packages.gpg > /dev/null
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/shiftkey-packages.gpg] https://apt.packages.shiftkey.dev/ubuntu/ any main" > /etc/apt/sources.list.d/shiftkey-packages.list'

## Install Github Desktop for Ubuntu
sudo apt update && sudo apt install github-desktop
```

> ⚠️ Though I recommend you also get accustomed to the basic usage of the CLI interface.

#### Visual Studio Code’s Git integration
Visual Studio Code bundles a complete Git integration, which you can use to manage your projects.