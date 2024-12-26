# Python/Git tutorial

This repository will be used to teach you the basics of Git and Python.

## Git

Git is a super popular version control system.
A version control system is software that helps manage large projects.
It helps cleanly work on separate sides of the same project,
conveniently merging them when needed.

Logically it takes for of a tree that grows,
with several branches meaning several different versions of the program.
The `main` branch is the main branch of the repository -
it is the best and cleanest version of the code.
When somebody wants do a feature for the project,
they make another branch which they name anyway they wish.
This creates a separate node that stems from `main`,
with changes being recorded in subsequent nodes.
When the feature is completed, they can merge it back to `main`,
which then includes the feature in the main branch (and thus the main code).

### Setting up git.

Setting up git should be easy.

On ubuntu, just run the following:

```bash
apt-get install git
```

This will install `git` to the system from the APT,
which is the ubuntu software manager.

On windows, it is a bit trickier, since windows is ass.
The easiest way is to install it as a vscode extension.
I don't have vscode on me to produce an example.

### Cloning a repository.

Cloning a repository is the act of downloading the code from a repository.
The general command is:
```bash
git clone <repo>
```
Where the `<repo>` is the URL to the repository.
It can be done via HTTPS (how browsers transfer data),
or via `ssh` (the utility that lets you log into other computers,
going to be discussed later).

`ssh` is the preferable way to do it,
as it lets github know that it's actually you doing the changes.
However, it may require a github account with ssh keys set up,
which we'll do in the future.

The URL for the repo should be taken from the green button on github that says "<> code".
Tab should be local, and there you can choose from the three options.
The third option is Github CLI, and it is ass.

For now, clone the repo with this in the terminal:
```bash
git clone git@github.com:vjsliogeris/python-tutorial.git
```
This should download the code into the current directory (folder).
It automatically sets most stuff up for further work.
If that doesn't work, ping me and we'll set github up to do it.

Congratulaitons!

