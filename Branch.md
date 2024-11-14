# Branch
### What is a `branch`?

A branch is a separation from the main state of the repository.

Its history is shared with the main repository up until the moment of its creation, after which it becomes independent.

For small projects, you won’t need to make any other branches. The `main` branch will be everything you’ll need. Your changes will directly go there and you’ll only keep track of one version of the codebase.

For bigger projects, however, it can be useful to create a branch for each new feature or change being developed.

### Branching models
There’s two main branching models, used in larger projects:
- Git Flow
- Feature branches

#### Git Flow
> ⚠️ This one is definitely overkill for our scopes, so this is mostly for your own knowledge.\
\
However, this model is **very** widely used in companies and enterprises, making it worthy of learning.

Its structure is as follows:

`feat/new-stuff -> develop -> release/0.1.0 -> main`
1. The first branch is the **feature branch**: here is where you code your actual feature
2. The second branch is the `develop` branch: it is the latest state of the code, and contains all of the other branches’ changes, merged into it.
3. The third branch is the `release` branch: this is the one into which you will merge every change into, **once they are fully polished**.\
\
Once there’s been enough changes and updates, this branch gets merged into `main`, and **tagged** with a version number.
> At this point, it should get merged back into `develop` to bring it up to date, which might’ve changed since the release was initiated.

This model allows for teams to polish the current release while another team continues working on features for the next release.

It also defines clear releases, as well as their associated goals.

##### Hotfix branches
If a bug manages to slip by into production, you would now create a **hotfix branch** to quickly patch it and merge it directly into `main`.\
\
⚠️ **This is the only time when you should merge directly into `main`.**

#### Feature-branch
Its structure is as follows:

`feat/new-stuff -> main`

Essentially, it’s a more simplified version of Git Flow, where you develop each feature into its own branch, then merge it back into `main` once it’s ready.

This allows for another thing: **pull requests**.