# Learning Git
___


For help:

```bash
    git help
```

1. Setting up Git

Before that, For check

```bash
    git config --list --global
```

```bash
    git config --global user.name "iamprasadraju"
    git config --global user.email "iamprasadraju@duck.com"
```

**(Optional)** Setting code editor

```bash
    git config --global core.editor "vim"
```


2.  Creating a Repository (local)

```bash
    mkdir <projectname>
    cd <projectname>

    // Initializing Repository
    git init
```
.git dir is created, it stores all the history


3. Tracking Changes

```bash
    git status
```

<quote>
    On branch main
    No commits yet
    nothing to commit (create/copy files and use "git add" to track)
</quote>

4. Adding a file to track

    Create a file ```README.md```

```bash
    git add <file>
```

Then check **git status**

<quote>
    On branch main

    No commits yet

    Untracked files:
    (use "git add <file>..." to include in what will be committed)

   	guacamole.md

    nothing added to commit but untracked files present (use "git add" to track)
</quote>


5. Writing commit messages

```bash
    git commit -m "<commit messages"
```

<quote>
    Example:

    [main (root-commit) af6f22b] Initial commit
    1 file changed, 81 insertions(+)
    create mode 100644 README.md
</quote>

![gitworkflow img](https://swcarpentry.github.io/git-novice/fig/git-staging-area.svg)

If we modified any tracked file -> It will show *modified:<file>*

Check the difference/modified content by ```git diff <file>``` or ```git diff``` for all modified content in that Repository. ```git diff --staged``` for staged files.

<quote>
    diff --git a/guacamole.md b/guacamole.md
    index 315bf3a..b36abfd 100644
    --- a/guacamole.md
    +++ b/guacamole.md
    @@ -1,6 +1,6 @@
    # Guacamole
    ## Ingredients
    * avocado
    -* lemon
    +* lime
    * salt
    ## Instructions
</quote>


We can look at history of repo (just like logs):

```bash
    git log
```

<quote>
    Example:

    commit 005937fbe2a98fb83f0ade869025dc2636b4dad5 (HEAD -> main)
    Author: Alfredo Linguini <a.linguini@ratatouille.fr>
    Date:   Thu Aug 22 10:14:07 2013 -0400

        Modify guacamole to the traditional recipe

    commit 34961b159c27df3b475cfe4415d94a6d1fcd064d
    Author: Alfredo Linguini <a.linguini@ratatouille.fr>
    Date:   Thu Aug 22 10:07:21 2013 -0400

        Add ingredients for basic guacamole

    commit f22b25e3233b4645dabd0d81e651fe074bd8e73b
    Author: Alfredo Linguini <a.linguini@ratatouille.fr>
    Date:   Thu Aug 22 09:51:46 2013 -0400

        Create initial structure for a Guacamole recipe
</quote>

Useful code:

```bash
    // using -N, where N is the number of commits that you want to view
    git log -1

    // You can also reduce the quantity of information using the --oneline
    git log --oneline

    // --graph to display the commit history as a text-based graph
    git log --oneline --graph
```

![github workflow](https://swcarpentry.github.io/git-novice/fig/git-committing.svg)


6. Exploring History

```bash
    git diff HEAD <file>
```

Note that HEAD is the default option for git diff, so omitting it will not change the command’s output at all (give it a try). However, the real power of git diff lies in its ability to compare with previous commits. For example, by adding ~1 (where “~” is “tilde”, pronounced [til-duh]), we can look at the commit before HEAD.

```bash
    git diff HEAD~1 <file>
```

<quote>
    diff --git a/guacamole.md b/guacamole.md
    index df0654a..b36abfd 100644
    --- a/guacamole.md
    +++ b/guacamole.md
    @@ -1,3 +1,6 @@
    # Guacamole
    ## Ingredients
    +* avocado
    +* lime
    +* salt
    ## Instructions
</quote>

We could also use git show which shows us what changes we made at an older commit as well as the commit message, rather than the differences between a commit and our working directory that we see by using git diff.

```bash
    git show HEAD~2 guacamole.md
```

<quote>
    Create a template for recipe

    diff --git a/guacamole.md b/guacamole.md
    new file mode 100644
    index 0000000..df0654a
    --- /dev/null
    +++ b/guacamole.md
    @@ -0,0 +1,3 @@
    +# Guacamole
    +## Ingredients
    +## Instructions
</quote>