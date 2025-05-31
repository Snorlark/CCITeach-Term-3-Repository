# Git Cheatsheet

## Basic Commands

### Configuration
```bash
# Set user name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# View configuration
git config --list
git config user.name
git config user.email

# Set default editor
git config --global core.editor "code --wait"
```

### Repository Setup
```bash
# Initialize new repository
git init

# Clone repository
git clone <repository-url>
git clone <repository-url> <directory-name>

# Add remote repository
git remote add origin <repository-url>
git remote -v  # List remotes
```

### Basic Workflow
```bash
# Check status
git status

# Stage changes
git add <file>
git add .  # Stage all changes
git add -p  # Interactive staging

# Commit changes
git commit -m "Commit message"
git commit -am "Commit message"  # Stage and commit in one command

# View history
git log
git log --oneline
git log --graph --oneline --all
git log --author="name"
git log --since="2 weeks ago"
```

## Branching & Merging

### Branch Operations
```bash
# List branches
git branch
git branch -a  # List all branches
git branch -r  # List remote branches

# Create branch
git branch <branch-name>
git checkout -b <branch-name>  # Create and switch

# Switch branch
git checkout <branch-name>
git switch <branch-name>  # New Git command

# Delete branch
git branch -d <branch-name>  # Safe delete
git branch -D <branch-name>  # Force delete
```

### Merging
```bash
# Merge branch
git merge <branch-name>
git merge --no-ff <branch-name>  # No fast-forward

# Abort merge
git merge --abort

# Resolve conflicts
git status  # Check conflicting files
# Edit files to resolve conflicts
git add <resolved-files>
git commit  # Complete merge
```

### Remote Operations
```bash
# Fetch changes
git fetch
git fetch origin
git fetch --all

# Pull changes
git pull
git pull origin <branch-name>
git pull --rebase origin <branch-name>

# Push changes
git push
git push origin <branch-name>
git push -u origin <branch-name>  # Set upstream
git push --force  # Force push (use with caution)
```

## Advanced Operations

### Stashing
```bash
# Save changes
git stash
git stash save "message"
git stash -u  # Include untracked files

# List stashes
git stash list

# Apply stashes
git stash apply  # Apply most recent
git stash apply stash@{n}  # Apply specific stash
git stash pop  # Apply and remove

# Remove stashes
git stash drop stash@{n}
git stash clear  # Remove all stashes
```

### Rebasing
```bash
# Rebase branch
git rebase <branch-name>
git rebase -i HEAD~n  # Interactive rebase

# Abort rebase
git rebase --abort

# Continue rebase
git rebase --continue

# Skip commit in rebase
git rebase --skip
```

### Cherry-picking
```bash
# Apply specific commit
git cherry-pick <commit-hash>
git cherry-pick -x <commit-hash>  # Add reference
git cherry-pick --no-commit <commit-hash>  # Stage only
```

### Resetting & Reverting
```bash
# Reset to commit
git reset --soft <commit-hash>  # Keep changes staged
git reset --mixed <commit-hash>  # Keep changes unstaged
git reset --hard <commit-hash>  # Discard changes

# Revert commit
git revert <commit-hash>
git revert --no-commit <commit-hash>  # Stage only
```

## Working with Remotes

### Remote Management
```bash
# Add remote
git remote add <name> <url>

# Remove remote
git remote remove <name>

# Rename remote
git remote rename <old-name> <new-name>

# Update remote URL
git remote set-url <name> <new-url>
```

### Remote Branches
```bash
# List remote branches
git branch -r

# Create tracking branch
git checkout -b <branch-name> origin/<branch-name>
git checkout --track origin/<branch-name>

# Delete remote branch
git push origin --delete <branch-name>
```

## Advanced Features

### Submodules
```bash
# Add submodule
git submodule add <repository-url> <path>

# Initialize submodules
git submodule init
git submodule update
git submodule update --init --recursive

# Update submodules
git submodule update --remote
```

### Git Hooks
```bash
# List hooks
ls .git/hooks/

# Create hook
touch .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

### Git Workflow
```bash
# Feature branch workflow
git checkout -b feature/new-feature
# Make changes
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
# Create pull request

# Gitflow workflow
git checkout develop
git checkout -b feature/new-feature
# Make changes
git add .
git commit -m "Add new feature"
git checkout develop
git merge feature/new-feature
git push origin develop
```

## Best Practices

### Commit Messages
```bash
# Conventional Commits
<type>(<scope>): <description>

[optional body]

[optional footer]

# Types
feat:     New feature
fix:      Bug fix
docs:     Documentation
style:    Formatting
refactor: Code restructuring
test:     Adding tests
chore:    Maintenance
```

### Git Ignore
```bash
# Common .gitignore patterns
node_modules/
.env
*.log
.DS_Store
dist/
build/
*.pyc
__pycache__/
```

### Git Configuration
```bash
# Global .gitconfig
[user]
    name = Your Name
    email = your.email@example.com
[core]
    editor = code --wait
    autocrlf = input
[init]
    defaultBranch = main
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
```

## Troubleshooting

### Common Issues
```bash
# Undo last commit
git reset HEAD~1

# Recover deleted branch
git reflog
git checkout -b <branch-name> <commit-hash>

# Clean untracked files
git clean -n  # Dry run
git clean -f  # Force
git clean -fd  # Include directories

# Fix detached HEAD
git checkout <branch-name>
```

### Git Maintenance
```bash
# Garbage collection
git gc

# Prune objects
git prune

# Verify repository
git fsck

# Optimize repository
git repack -a -d --depth=250 --window=250
```

## Git Tools

### Git GUI
```bash
# Open Git GUI
git gui

# Open GitK
gitk

# Open GitHub Desktop
github
```

### Git LFS
```bash
# Install Git LFS
git lfs install

# Track large files
git lfs track "*.psd"
git lfs track "*.zip"

# List tracked files
git lfs ls-files
```

### Git Credentials
```bash
# Store credentials
git config --global credential.helper store
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'

# Remove stored credentials
git config --global --unset credential.helper
```

## Git Security

### SSH Keys
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add to SSH agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Add to GitHub
cat ~/.ssh/id_ed25519.pub
# Copy and paste to GitHub SSH keys
```

### GPG Signing
```bash
# Generate GPG key
gpg --full-generate-key

# List GPG keys
gpg --list-secret-keys --keyid-format LONG

# Configure Git to use GPG
git config --global user.signingkey <key-id>
git config --global commit.gpgsign true
```

## Git Resources

### Documentation
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Pro Git Book](https://git-scm.com/book/en/v2)

### Tools
- [GitHub Desktop](https://desktop.github.com/)
- [GitKraken](https://www.gitkraken.com/)
- [SourceTree](https://www.sourcetreeapp.com/)
- [VS Code Git Integration](https://code.visualstudio.com/docs/editor/versioncontrol)

### Learning Resources
- [GitHub Learning Lab](https://lab.github.com/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
- [Learn Git Branching](https://learngitbranching.js.org/)
- [Oh My Git!](https://ohmygit.org/) 