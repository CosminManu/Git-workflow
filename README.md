# Git Branching workflow

This document outlines steps to set up a Git repo and manage the branching workflow for dev & prod

## Initializing the repository

1. **Initialize Git repo**

```bash
git init
```

2. **Check status of the repository**

```bash
git status
```

3. **Add all files to staging area**

```bash
git add .
```

4. **Commit changes**

```bash
git commit -m "enter your text here"
```

5. **Rename the default branch to `main`**

```bash
git branch -M main
```

6. **Add the remote repository**

```bash
git remote add origin <repo_url>
```

7. **Push the `main` branch to the remote repository:**

```bash
git push -u origin main
```

---
## Creating and using the `development` branch

1. **Create and switch to the `development` branch (if not already created):**

```bash
git checkout -b development
```
2. **If the `development` branch is already created, switch to it:**

```bash
git checkout development
```

3. **Check status of the branch**

```bash
git status
```

---
## Work on development branch

1. **Check the status of the repository:**

```bash
git status
```

2. **Add changes to the staging area:**

```bash
git add .
```

3. **Commit the changes:**

```bash
git commit -m "Your commit message"
```

4. **Push the changes to remote `development` branch**

```bash
git push origin development
```

---
## Merging `development` into `main` (production branch) after testing and QA

1. **Switch to the `main` branch**

```bash
git checkout main
```

2. **Check the status of the repository**

```bash
git status
```

3. **Make sure the `main` branch is up to date**

```bash
git pull origin main
```

4. **Merge the `development` branch into `main`**
```bash
git merge development
```

5. **Check the status again**
```bash
git status
```

6. **Push the updated `main` branch to remote repository**
```bash
git push origin main
```


## Summary of Commands

```bash
# Initialize the repository
git init
git status
git add .
git status
git commit -m "Initial commit"
git branch -M main
git remote add origin <remote_repository_URL>
git push -u origin main

# Create and push the development branch (if not already created)
git checkout -b development
git push -u origin development

# If the development branch is already created, switch to it
git checkout development
git status

# Work on development branch
git status
git add .
git status
git commit -m "Your commit message"
git push origin development

# Merge development into main after testing
git checkout main
git status
git pull origin main
git merge development
git status
git push origin main

