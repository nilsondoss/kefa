# Git Quick Reference for KEFA Technology Solutions

Quick command reference for uploading and managing your website on GitHub.

---

## 🚀 First Time Setup (One-Time Only)

### Step 1: Create GitHub Repository

1. Go to https://github.com and log in
2. Click "+" → "New repository"
3. Name: `kefa-technology-solutions`
4. Description: `Official website for KEFA Technology Solutions`
5. Choose Public or Private
6. **DO NOT** check "Initialize with README"
7. Click "Create repository"

### Step 2: Initialize and Push

```bash
# Navigate to your project folder
cd path/to/kefa-technology-solutions

# Initialize Git
git init

# Add all files
git add .

# First commit
git commit -m "Initial commit: KEFA Technology Solutions website"

# Connect to GitHub (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/kefa-technology-solutions.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**If prompted for password:** Use a Personal Access Token (see GITHUB_SETUP.md)

---

## 📝 Daily Workflow (Making Changes)

### Making Updates

```bash
# 1. Check what files changed
git status

# 2. Add all changed files
git add .

# OR add specific files
git add src/pages/home.tsx

# 3. Commit with a message
git commit -m "Update home page content"

# 4. Push to GitHub
git push
```

### Common Commit Messages

```bash
git commit -m "Add new service page"
git commit -m "Update contact information"
git commit -m "Fix navigation menu bug"
git commit -m "Improve mobile responsiveness"
git commit -m "Add client testimonials"
git commit -m "Update product catalog"
```

---

## 🔄 Syncing Changes

### Pull Latest Changes (Before Making Edits)

```bash
# Get latest changes from GitHub
git pull origin main
```

### Check Status

```bash
# See what files changed
git status

# See detailed changes
git diff

# See commit history
git log --oneline -10
```

---

## 🌿 Working with Branches (Advanced)

### Create Feature Branch

```bash
# Create and switch to new branch
git checkout -b feature/new-contact-form

# Make changes, then commit
git add .
git commit -m "Add new contact form"

# Push branch to GitHub
git push -u origin feature/new-contact-form

# Switch back to main
git checkout main

# Merge feature into main
git merge feature/new-contact-form

# Push updated main
git push
```

---

## 🆘 Common Issues & Fixes

### Issue: "Authentication failed"

**Solution:** Use Personal Access Token instead of password

1. Go to https://github.com/settings/tokens
2. Generate new token (classic)
3. Check "repo" scope
4. Copy token
5. Use token as password when pushing

### Issue: "Updates were rejected"

**Solution:** Pull first, then push

```bash
git pull origin main --rebase
git push origin main
```

### Issue: "Remote origin already exists"

**Solution:** Remove and re-add remote

```bash
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/kefa-technology-solutions.git
```

### Issue: "Large files warning"

**Solution:** Make sure node_modules is in .gitignore

```bash
# Check .gitignore includes:
node_modules/
dist/
.env
```

### Issue: "Merge conflict"

**Solution:** Resolve conflicts manually

```bash
# 1. Open conflicted files
# 2. Look for <<<<<<< HEAD markers
# 3. Choose which version to keep
# 4. Remove conflict markers
# 5. Add and commit
git add .
git commit -m "Resolve merge conflict"
git push
```

---

## 🔐 Personal Access Token Setup

### Create Token (One-Time)

1. Go to: https://github.com/settings/tokens
2. Click "Generate new token" → "Generate new token (classic)"
3. Note: "KEFA Website Access"
4. Expiration: 90 days
5. Scopes: Check "repo"
6. Click "Generate token"
7. **COPY THE TOKEN** (you won't see it again!)

### Use Token

```bash
# When prompted for password, paste your token
Username: your-github-username
Password: ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### Save Token (Optional)

```bash
# Cache credentials for 1 hour
git config --global credential.helper 'cache --timeout=3600'

# OR store permanently (less secure)
git config --global credential.helper store
```

---

## 📊 Useful Commands

### View Changes

```bash
# See what changed
git status

# See detailed changes
git diff

# See changes in specific file
git diff src/pages/home.tsx

# See commit history
git log

# See recent commits (short)
git log --oneline -10
```

### Undo Changes

```bash
# Undo changes to a file (before commit)
git checkout -- src/pages/home.tsx

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1
```

### Clean Up

```bash
# Remove untracked files
git clean -fd

# Remove ignored files
git clean -fdx
```

---

## 🎯 Best Practices

### ✅ DO:

- ✅ Commit often with clear messages
- ✅ Pull before pushing
- ✅ Use branches for new features
- ✅ Review changes with `git status` before committing
- ✅ Keep .gitignore updated
- ✅ Write descriptive commit messages

### ❌ DON'T:

- ❌ Commit node_modules/ (use .gitignore)
- ❌ Commit .env files (keep secrets out)
- ❌ Force push to main branch
- ❌ Commit large binary files
- ❌ Use vague commit messages ("fix", "update")

---

## 📋 Checklist for First Upload

- [ ] Create GitHub repository
- [ ] Initialize Git in project folder
- [ ] Add all files with `git add .`
- [ ] Create first commit
- [ ] Connect to GitHub remote
- [ ] Push to GitHub
- [ ] Verify files on GitHub
- [ ] Add .gitignore file
- [ ] Add README.md file
- [ ] Set up Personal Access Token

---

## 🔗 Helpful Links

- **GitHub Docs:** https://docs.github.com
- **Git Docs:** https://git-scm.com/doc
- **Git Cheat Sheet:** https://education.github.com/git-cheat-sheet-education.pdf
- **Personal Access Tokens:** https://github.com/settings/tokens

---

## 💡 Pro Tips

### Commit Message Format

```bash
# Good commit messages:
git commit -m "Add contact form validation"
git commit -m "Fix mobile menu toggle bug"
git commit -m "Update product pricing"
git commit -m "Improve page load performance"

# Bad commit messages:
git commit -m "fix"
git commit -m "update"
git commit -m "changes"
```

### Check Before Committing

```bash
# Always check what you're committing
git status
git diff

# Then commit
git add .
git commit -m "Your message"
```

### Regular Backups

```bash
# Push to GitHub regularly (daily or after major changes)
git add .
git commit -m "Daily backup: [date]"
git push
```

---

**Need more help? See GITHUB_SETUP.md for detailed instructions!**
