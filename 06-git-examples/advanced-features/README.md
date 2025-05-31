# Advanced Git Features

This directory contains examples and explanations of advanced Git features that can help you work more efficiently and handle complex scenarios.

## Advanced Topics

### 1. Git Hooks
Git hooks are scripts that run automatically at specific points in your Git workflow.

#### Pre-commit Hook Example
```bash
#!/bin/sh
# .git/hooks/pre-commit

# Run linter
npm run lint

# Run tests
npm test

# Check for console.log statements
if git diff --cached | grep -i "console.log"; then
    echo "Error: console.log statements found in commit"
    exit 1
fi
```

#### Post-commit Hook Example
```bash
#!/bin/sh
# .git/hooks/post-commit

# Send notification
curl -X POST https://api.notification-service.com/commit \
    -d "commit=$(git rev-parse HEAD)" \
    -d "author=$(git config user.name)"
```

### 2. Git Workflows

#### Gitflow Workflow
```bash
# Initialize Gitflow
git flow init

# Start a feature
git flow feature start new-feature

# Finish a feature
git flow feature finish new-feature

# Start a release
git flow release start 1.0.0

# Finish a release
git flow release finish 1.0.0
```

#### Trunk-Based Development
```bash
# Create short-lived feature branch
git checkout -b feature/quick-fix

# Keep branch up to date
git rebase main

# Merge back to main
git checkout main
git merge --no-ff feature/quick-fix
```

### 3. Advanced Branching Strategies

#### Branch Protection
```bash
# Protect main branch
git config branch.main.protect true

# Require pull request reviews
git config branch.main.requireReviews true

# Require status checks
git config branch.main.requireStatusChecks true
```

#### Branch Cleanup
```bash
# Delete merged branches
git branch --merged | grep -v "\*" | xargs -n 1 git branch -d

# Delete remote branches
git remote prune origin

# Clean up old branches
git fetch -p
```

### 4. Advanced Merging and Rebasing

#### Interactive Rebase
```bash
# Start interactive rebase
git rebase -i HEAD~3

# Squash commits
pick f7f3f6d First commit
squash 310154e Second commit
squash a5f4a0d Third commit
```

#### Merge Strategies
```bash
# Merge with specific strategy
git merge --strategy-option=theirs feature-branch

# Resolve conflicts using specific tool
git mergetool --tool=vimdiff

# Abort merge
git merge --abort
```

### 5. Git Submodules and Subtrees

#### Submodules
```bash
# Add submodule
git submodule add https://github.com/username/repo.git

# Initialize submodules
git submodule init
git submodule update

# Update submodules
git submodule update --remote
```

#### Subtrees
```bash
# Add subtree
git subtree add --prefix=lib/feature https://github.com/username/repo.git main

# Push changes to subtree
git subtree push --prefix=lib/feature https://github.com/username/repo.git main
```

### 6. Advanced Git Configuration

#### Git Aliases
```bash
# Add aliases to .gitconfig
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
```

#### Git Attributes
```bash
# .gitattributes
*.js    diff=javascript
*.css   diff=css
*.html  diff=html
*.md    diff=markdown
```

### 7. Advanced Logging and History

#### Custom Log Formats
```bash
# Custom log format
git log --pretty=format:"%h - %an, %ar : %s"

# Log with graph
git log --graph --oneline --decorate --all

# Log with patches
git log -p
```

#### Git Bisect
```bash
# Start bisect
git bisect start

# Mark good commit
git bisect good v1.0.0

# Mark bad commit
git bisect bad HEAD

# Run bisect automatically
git bisect run npm test
```

### 8. Advanced Stashing

#### Stash with Message
```bash
# Stash with description
git stash save "WIP: Working on feature"

# List stashes
git stash list

# Apply specific stash
git stash apply stash@{2}
```

#### Stash Branch
```bash
# Create branch from stash
git stash branch new-branch stash@{0}

# Drop specific stash
git stash drop stash@{1}
```

## Best Practices for Advanced Features

1. **Hooks**
   - Keep hooks simple and fast
   - Document hook requirements
   - Test hooks before deployment

2. **Workflows**
   - Choose workflow based on team size
   - Document workflow rules
   - Use automation where possible

3. **Branching**
   - Use meaningful branch names
   - Keep branches short-lived
   - Regular cleanup of old branches

4. **Merging**
   - Use appropriate merge strategy
   - Resolve conflicts carefully
   - Test after merging

## Common Advanced Scenarios

### Scenario 1: Complex Merge Resolution
```bash
# Start merge
git merge feature-branch

# Resolve conflicts
git mergetool

# Continue merge
git merge --continue

# Verify merge
git log --graph --oneline
```

### Scenario 2: Recovering Lost Commits
```bash
# Find lost commit
git reflog

# Recover commit
git checkout -b recovery-branch commit-hash

# Cherry-pick to main
git checkout main
git cherry-pick commit-hash
```

### Scenario 3: Large File Handling
```bash
# Track large files with Git LFS
git lfs install
git lfs track "*.psd"
git lfs track "*.zip"

# Commit LFS configuration
git add .gitattributes
git commit -m "Configure Git LFS"
```

## Additional Resources

- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Git Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows)
- [Git Hooks Documentation](https://git-scm.com/docs/githooks)
- [Git LFS Documentation](https://git-lfs.github.com) 