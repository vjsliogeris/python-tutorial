# HOOOLUP

HAHA TRICKED YOU YOU'RE DOING GIT NOW.

This homework will modify this code and make it better.
Let's make our own branch to do stuff in!

To make a branch, in the terminal type
```bash
git checkout -B basics_homework
```
This will create a branch called `basics_homework`.
If you're interesting what's going on, type:
```bash
git status
```
It will tell you what's going on - the branch you're on,
what changes you've made, etc.
For me it looks like this

```bash
<renamorcen@salomeike:~/education/python-tutorial>
zsh/4 48  (git)-[main]-% git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   tutorial_python/base/README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        tutorial_python/base/homework/

no changes added to commit (use "git add" and/or "git commit -a")
```
It say I'm on branch `main` (I'm naughty, should do it in another branch).
It says that "my branch is up to date with `origin/main`",
which means that nobody has changed the main branch while I was working on it.
Then it shows all the changes I did - an untracked folder and modifications in a file.

For now you can work on the code, and we'll get back to it.

# So you think you can print?

Listen up.
I want some heavy machinery here.
I want a program that _takes a name_.
_Politely greets you with the name_.
_Asks for the age_.
And then gives a compliment like "damn you look like <age>",
where <age> is the square of the age provided.
It should look like this:

```bash
<renamorcen@salomeike:~/education/python-tutorial/tutorial_python/base/homework>
zsh/4 9 [1]  (git)-[main]-% python homework.py
What's your name?
Evaldas
Hi, Evaldas, nice to meet you!
How old are you?
21
Really? You look like you're 441
[Thu 24/12/26 23:40 EET][pts/3][x86_64/linux-gnu/6.12.6-arch1-1][5.9]
<renamorcen@salomeike:~/education/python-tutorial/tutorial_python/base/homework>
zsh/4 10  (git)-[main]-%
```

Fucking pwned!


## Done?
BACK TO GIT.

Okay, you've made your feature, it works great - gotta publish it!
Type `git status` to see what files you've changed - it should only be `homework.py`.
If you want, you can type the following
```bash
git diff
```
This will show you the exact lines you've changed.

Now we are concerned if somebody didn't update the code while we were working on it.
For this we run a few commands.

```bash
git fetch
```
This command quickly pulls the summary of changes from github so your local git knows what's up.
Then:
```bash
git checkout main
git pull
```
This makes you go to your main branch (omg le your code is le gone!),
and `git pull` makes you download the newest version of the main branch (there may be nothing new).
Then you wanna include those changes in your own code.
```bash
git checkout basics_homework
git merge main
```
This takes the changes in main, and applies them to your branch.
Now your branch is comatible with main!
You can publish the changes by typing
```bash
git push
```
It will create a new branch in github, there you can create a pull request (we'll do that on discord).
Yippee!
