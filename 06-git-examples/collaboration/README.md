# Git Collaboration

This directory contains examples and best practices for collaborating with Git in team environments. Learn how to work effectively with others using Git.

## Team Collaboration Workflows

### 1. Pull Request Workflow

#### Creating a Pull Request
```bash
# Create feature branch
git checkout -b feature/new-feature

# Make changes and commit
git add .
git commit -m "Add new feature"

# Push to remote
git push -u origin feature/new-feature

# Create pull request on GitHub/GitLab
# 1. Go to repository website
# 2. Click "New Pull Request"
# 3. Select base and compare branches
# 4. Add description and reviewers
```

#### Reviewing a Pull Request
```bash
# Fetch pull request
git fetch origin pull/123/head:pr-123

# Checkout PR branch
git checkout pr-123

# Review changes
git diff main...pr-123

# Add review comments
# 1. Go to PR on website
# 2. Click "Files changed"
# 3. Add comments on specific lines
```

### 2. Code Review Best Practices

#### Before Submitting
```bash
# Update with latest changes
git checkout main
git pull origin main
git checkout feature-branch
git rebase main

# Run tests
npm test

# Check formatting
npm run lint

# Squash commits if needed
git rebase -i HEAD~3
```

#### Review Checklist
- [ ] Code follows style guide
- [ ] Tests are included
- [ ] Documentation is updated
- [ ] No sensitive data
- [ ] No console.log statements
- [ ] No commented-out code

### 3. Team Branching Strategies

#### Feature Branch Workflow
```bash
# Start new feature
git checkout -b feature/user-auth

# Keep feature branch updated
git checkout feature/user-auth
git rebase main

# Complete feature
git checkout main
git merge --no-ff feature/user-auth
git push origin main
```

#### Release Branch Workflow
```bash
# Create release branch
git checkout -b release/1.0.0

# Make release-specific changes
git commit -m "Update version to 1.0.0"

# Merge to main
git checkout main
git merge --no-ff release/1.0.0
git tag -a v1.0.0 -m "Version 1.0.0"

# Merge to develop
git checkout develop
git merge --no-ff release/1.0.0
```

### 4. Conflict Resolution

#### Common Conflict Scenarios
```bash
# Pull with rebase
git pull --rebase origin main

# Resolve conflicts
git status  # Check conflicted files
# Edit files to resolve conflicts
git add .   # Mark as resolved
git rebase --continue

# If rebase gets too complicated
git rebase --abort
```

#### Merge Conflict Resolution
```bash
# Start merge
git merge feature-branch

# Resolve conflicts
# 1. Open conflicted files
# 2. Look for conflict markers (<<<<<<, =======, >>>>>>>)
# 3. Choose which changes to keep
# 4. Save files

# Complete merge
git add .
git commit -m "Resolve merge conflicts"
```

### 5. Team Communication

#### Commit Message Guidelines
```
type(scope): subject

body

footer
```

Types:
- feat: New feature
- fix: Bug fix
- docs: Documentation
- style: Formatting
- refactor: Code restructuring
- test: Adding tests
- chore: Maintenance

#### Pull Request Template
```markdown
## Description
[Describe your changes here]

## Related Issues
[Link to related issues]

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Checklist
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] Code follows style guide
- [ ] Self-reviewed
```

### 6. Team Repository Management

#### Branch Protection Rules
```bash
# Protect main branch
git config branch.main.protect true

# Require pull request reviews
git config branch.main.requireReviews true

# Require status checks
git config branch.main.requireStatusChecks true
```

#### Repository Settings
- Enable branch protection
- Set up required reviewers
- Configure status checks
- Set up automated testing
- Configure merge strategies

### 7. Continuous Integration

#### GitHub Actions Example
```yaml
# .github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
      - name: Lint
        run: npm run lint
```

#### GitLab CI Example
```yaml
# .gitlab-ci.yml
stages:
  - test
  - lint
  - build

test:
  stage: test
  script:
    - npm install
    - npm test

lint:
  stage: lint
  script:
    - npm run lint

build:
  stage: build
  script:
    - npm run build
```

### 8. Team Best Practices

#### Code Review Guidelines
1. **Before Review**
   - Self-review your changes
   - Update with latest main
   - Run tests locally
   - Check formatting

2. **During Review**
   - Be constructive
   - Explain reasoning
   - Suggest improvements
   - Check for security issues

3. **After Review**
   - Address all comments
   - Update documentation
   - Squash commits if needed
   - Keep PR up to date

#### Communication Guidelines
1. **Pull Requests**
   - Clear description
   - Link related issues
   - Tag relevant reviewers
   - Respond to comments

2. **Commit Messages**
   - Follow convention
   - Be descriptive
   - Reference issues
   - Keep it concise

3. **Team Meetings**
   - Regular sync-ups
   - Share knowledge
   - Discuss blockers
   - Plan next steps

## Common Collaboration Scenarios

### Scenario 1: Code Review Process
```bash
# Create feature branch
git checkout -b feature/login

# Make changes
git commit -m "feat(auth): add login form"

# Push and create PR
git push -u origin feature/login

# Address review comments
git commit -m "fix(auth): address review comments"

# Update PR
git push origin feature/login
```

### Scenario 2: Hotfix Process
```bash
# Create hotfix branch
git checkout -b hotfix/security-patch

# Make changes
git commit -m "fix(security): patch vulnerability"

# Create PR
git push -u origin hotfix/security-patch

# After approval
git checkout main
git merge --no-ff hotfix/security-patch
git tag -a v1.0.1 -m "Security patch"
```

### Scenario 3: Team Sync
```bash
# Update local main
git checkout main
git pull origin main

# Update feature branch
git checkout feature/new-feature
git rebase main

# Resolve conflicts
git add .
git rebase --continue

# Push changes
git push -f origin feature/new-feature
```

## Additional Resources

- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)
- [Code Review Best Practices](https://google.github.io/eng-practices/review/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [GitLab CI/CD Documentation](https://docs.gitlab.com/ee/ci/) 