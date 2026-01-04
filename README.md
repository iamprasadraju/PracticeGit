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





