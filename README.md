# Git Cheat Sheet

[Set the Name and Email for Git Commits](./SETUP.md)

## Start a Project

Create a local repo (initialize the current directory as a git repo):

```bash
$ git init <directory>
```

Download a remote repo:

```bash
$ git clone <url>
```

---

## Make a Change

Add a file to staging:

```bash
$ git add <file>
```

Stage all files:

```bash
$ git add .
```

Commit all staged files to git:

```bash
$ git commit -m "commit message"
```

Add changes to tracked files to staging:

```bash
$ git commit -am "commit message"
```

---

## Remove node_module / .env file from GitHub

To remove a file from your GitHub repository, follow these steps:

1. **Remove the file from your local repository** using the `git rm` command:

   ```bash
   git rm <file_path>
   ```

2. **Commit the changes** to your local repository:

   ```bash
   git commit -m "Removed <file_path>"
   ```

3. **Push the changes** to your remote GitHub repository:
   ```bash
   git push origin <branch_name>
   ```

If you want to remove the file from version control but keep it in your local file system, use:

```bash
git rm --cached <file_path>
```

## Retrieve a File from a Previous Commit

To retrieve a file from a previous commit in your Git repository, follow these steps:

1. **Find the commit hash** that contains the version of the file you want. Use:

   ```bash
   git log --oneline
   ```

2. **Checkout the file from the specific commit** using:

   ```bash
   git checkout <commit_hash> -- <file_path>
   ```

   This command retrieves the version of the file from the specific commit and places it in your working directory.

3. **Optionally, commit the changes** if you want to keep the retrieved version:
   ```bash
   git add <file_path>
   git commit -m "Reverted <file_path> to version from <commit_hash>"
   git push origin <branch_name>
   ```

---

---

## Change the Remote Repository URL

To change the remote repository URL in your Git repository, follow these steps:

1. **View the current remote URL** (optional):

   ```bash
   git remote -v
   ```

2. **Change the remote URL** using the `set-url` command:

   ```bash
   git remote set-url origin <new_url>
   ```

3. **Verify the change** (optional):
   ```bash
   git remote -v
   ```

---

## Basic Concepts

- `master`: Default development branch
- `origin`: Default remote name
- `HEAD`: Current branch
- `HEAD^`: Parent of HEAD
- `HEAD~4`: 4th commit back from HEAD

---

## Branches

List all local branches (add `-r` flag to show all remote branches, `-a` to show all branches):

```bash
$ git branch
```

Create a new branch:

```bash
$ git branch <new-branch>
```

Switch to a branch and update the working directory:

```bash
$ git checkout <branch>
```

Create a new branch and switch to it:

```bash
$ git checkout -b <new-branch>
```

Delete a merged branch:

```bash
$ git branch -d <branch>
```

Delete a branch, whether merged or not:

```bash
$ git branch -D <branch>
```

Add a tag to current commit (use `-a` to tag new releases):

```bash
$ git tag <tag-name>
```

---

## Merging

Merge a branch into a branch B (add `--no-ff` to avoid fast-forward merge):

```bash
$ git merge <branch>
```

Merge and rebase all commits at once (single commit):

```bash
$ git merge --squash <branch>
```

[Undoing Things](./UNDOING.md)

[Rebasing](./REBASING.md)

[Review your Repo](./REVIEWREPO.md)

[Synchronizing](./SYNCHRONIZING.md)

[Stashing](./STASHING.md)

---

This cheat sheet summarizes the most common Git commands and operations. For more detailed information, refer to the official Git documentation.

---

<p align="center">
  <a href="https://mostafizur.diginieit.com"><strong>Portfolio &rarr;</strong></a> 
</p>
