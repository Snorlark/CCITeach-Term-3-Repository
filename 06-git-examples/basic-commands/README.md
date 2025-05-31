# Basic Git Commands

This directory contains examples and scenarios for basic Git commands. Each scenario demonstrates common Git operations you'll use in your daily workflow.

## Common Scenarios

### 1. Initializing a Repository
```bash
# Create a new directory and initialize Git
mkdir my-project
cd my-project
git init

# Clone an existing repository
git clone https://github.com/username/repository.git
```

### 2. Basic Workflow
```bash
# Check repository status
git status

# Add files to staging area
git add filename.txt        # Add specific file
git add .                   # Add all files
git add *.js               # Add all JavaScript files

# Commit changes
git commit -m "Initial commit"
git commit -am "Update README"  # Add and commit in one command

# View commit history
git log
git log --oneline          # Compact view
git log --graph           # Show branch history
```

### 3. Working with Branches
```bash
# List branches
git branch                 # Local branches
git branch -r             # Remote branches
git branch -a             # All branches

# Create and switch branches
git branch feature-x      # Create new branch
git checkout feature-x    # Switch to branch
git checkout -b feature-x # Create and switch in one command

# Delete branches
git branch -d feature-x   # Delete local branch
git branch -D feature-x   # Force delete local branch
```

### 4. Remote Operations
```bash
# Add remote repository
git remote add origin https://github.com/username/repo.git

# List remotes
git remote -v

# Fetch and pull
git fetch origin          # Download changes
git pull origin main     # Fetch and merge

# Push changes
git push origin main     # Push to specific branch
git push -u origin main  # Set upstream branch
```

### 5. Undoing Changes
```bash
# Discard changes in working directory
git checkout -- filename.txt

# Unstage changes
git reset filename.txt

# Amend last commit
git commit --amend -m "New commit message"

# Revert a commit
git revert commit-hash
```

## Example Scenarios

### Scenario 1: Starting a New Project
```bash
# Initialize new project
mkdir my-project
cd my-project
git init

# Create and edit files
echo "# My Project" > README.md
touch index.html style.css

# First commit
git add .
git commit -m "Initial project setup"
```

### Scenario 2: Working on a Feature
```bash
# Create and switch to feature branch
git checkout -b feature-login

# Make changes
echo "Login form" > login.html
git add login.html
git commit -m "Add login form"

# Switch back to main
git checkout main
```

### Scenario 3: Updating from Remote
```bash
# Get latest changes
git fetch origin

# Update local main branch
git checkout main
git pull origin main

# Update feature branch
git checkout feature-login
git rebase main
```

## Best Practices

1. **Commit Messages**
   - Use present tense ("Add feature" not "Added feature")
   - Be specific and concise
   - Start with a capital letter
   - Keep under 50 characters for the first line

2. **Branching**
   - Use descriptive branch names
   - Delete branches after merging
   - Keep branches up to date with main

3. **Commits**
   - Make small, focused commits
   - Commit frequently
   - Test before committing

4. **Remote Operations**
   - Pull before pushing
   - Use meaningful commit messages
   - Keep remote branches clean

## Common Issues and Solutions

1. **Accidental Commit to Wrong Branch**
   ```bash
   # Create new branch with the commit
   git branch new-branch
   
   # Reset original branch
   git checkout original-branch
   git reset --hard HEAD~1
   ```

2. **Forgot to Add File to Last Commit**
   ```bash
   git add forgotten-file.txt
   git commit --amend --no-edit
   ```

3. **Need to Update Remote URL**
   ```bash
   git remote set-url origin new-url
   ```

## Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) 