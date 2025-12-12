# GitHub Setup Guide for KEFA Technology Solutions

This guide will help you upload your KEFA Technology Solutions website to GitHub.

---

## Prerequisites

- GitHub account (create one at https://github.com/signup if you don't have one)
- Git installed on your computer (download from https://git-scm.com/downloads)
- Your website files downloaded and extracted

---

## Step 1: Create a New GitHub Repository

1. **Go to GitHub** and log in to your account
2. **Click the "+" icon** in the top-right corner
3. **Select "New repository"**
4. **Fill in the repository details:**
   - **Repository name:** `kefa-technology-solutions`
   - **Description:** `Official website for KEFA Technology Solutions - Technology, HR, and Training Services`
   - **Visibility:** Choose "Public" (free) or "Private" (requires paid plan)
   - **DO NOT** initialize with README, .gitignore, or license (we'll add these)
5. **Click "Create repository"**

---

## Step 2: Initialize Git in Your Project

Open your terminal/command prompt and navigate to your project folder:

```bash
# Navigate to your project directory
cd path/to/kefa-technology-solutions

# Initialize Git repository
git init

# Add all files to staging
git add .

# Create your first commit
git commit -m "Initial commit: KEFA Technology Solutions website"
```

---

## Step 3: Connect to GitHub and Push

Replace `YOUR_USERNAME` with your actual GitHub username:

```bash
# Add GitHub repository as remote origin
git remote add origin https://github.com/YOUR_USERNAME/kefa-technology-solutions.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

**If prompted for credentials:**
- Username: Your GitHub username
- Password: Use a Personal Access Token (not your GitHub password)

---

## Step 4: Create a Personal Access Token (if needed)

GitHub no longer accepts passwords for Git operations. You need a Personal Access Token:

1. **Go to GitHub Settings:** https://github.com/settings/tokens
2. **Click "Generate new token"** → "Generate new token (classic)"
3. **Fill in details:**
   - **Note:** "KEFA Website Repository Access"
   - **Expiration:** Choose duration (90 days recommended)
   - **Scopes:** Check "repo" (full control of private repositories)
4. **Click "Generate token"**
5. **COPY THE TOKEN** (you won't see it again!)
6. **Use this token as your password** when pushing to GitHub

---

## Step 5: Verify Upload

1. **Go to your GitHub repository:** `https://github.com/YOUR_USERNAME/kefa-technology-solutions`
2. **You should see all your files:**
   - src/ directory
   - public/ directory
   - package.json
   - vite.config.ts
   - README.md
   - And all other project files

---

## Step 6: Add a .gitignore File (Important!)

Create a `.gitignore` file in your project root to exclude unnecessary files:

```bash
# Create .gitignore file
touch .gitignore
```

Add this content to `.gitignore`:

```
# Dependencies
node_modules/
package-lock.json

# Build outputs
dist/
build/
.vite/

# Environment variables
.env
.env.local
.env.production

# Logs
logs/
*.log
npm-debug.log*

# OS files
.DS_Store
Thumbs.db

# IDE files
.vscode/
.idea/
*.swp
*.swo

# Testing
coverage/
.nyc_output/

# Temporary files
*.tmp
*.temp
.cache/
```

Then commit and push:

```bash
git add .gitignore
git commit -m "Add .gitignore file"
git push
```

---

## Step 7: Create a README.md (Optional but Recommended)

Create a `README.md` file in your project root:

```markdown
# KEFA Technology Solutions

Official website for KEFA Technology Solutions - Your trusted partner for Technology, HR, and Training Services.

## 🌟 Features

- **12 Complete Pages** - Home, About, Services, Products, Clients, Partners, Careers, Contact, and more
- **3 Core Services:**
  - Technology Solutions
  - HR Consultancy
  - Training & Development
- **Interactive Features** - Contact forms, quote requests, job applications
- **Responsive Design** - Mobile, tablet, and desktop optimized
- **Modern Tech Stack** - React 19, TypeScript, Vite, Tailwind CSS, shadcn UI

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm 9+

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/kefa-technology-solutions.git
   cd kefa-technology-solutions
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start development server:
   ```bash
   npm run dev
   ```

4. Open your browser and visit: `http://localhost:5173`

## 📦 Build for Production

```bash
npm run build
```

The production-ready files will be in the `dist/` directory.

## 🛠️ Tech Stack

- **Frontend:** React 19, TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **UI Components:** shadcn UI
- **Icons:** Lucide React
- **Routing:** React Router v6
- **Forms:** React Hook Form

## 📄 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint
- `npm run type-check` - Run TypeScript type checking

## 📞 Contact

- **Phone:** +91 444 862 2011
- **Email:** support@kefatech.in
- **Website:** [KEFA Technology Solutions](https://kefatech.in)

## 📝 License

Copyright © 2025 KEFA Technology Solutions. All rights reserved.
```

Commit and push:

```bash
git add README.md
git commit -m "Add README documentation"
git push
```

---

## Common Git Commands for Future Updates

### Making Changes

```bash
# Check status of your files
git status

# Add specific file
git add src/pages/home.tsx

# Add all changed files
git add .

# Commit changes
git commit -m "Update home page content"

# Push to GitHub
git push
```

### Viewing History

```bash
# View commit history
git log

# View recent commits (short)
git log --oneline -10
```

### Branching (for new features)

```bash
# Create new branch
git checkout -b feature/new-service-page

# Make changes and commit
git add .
git commit -m "Add new service page"

# Push branch to GitHub
git push -u origin feature/new-service-page

# Switch back to main branch
git checkout main

# Merge feature branch
git merge feature/new-service-page
```

### Pulling Latest Changes

```bash
# Pull latest changes from GitHub
git pull origin main
```

---

## Troubleshooting

### Issue: "fatal: remote origin already exists"

```bash
# Remove existing remote
git remote remove origin

# Add correct remote
git remote add origin https://github.com/YOUR_USERNAME/kefa-technology-solutions.git
```

### Issue: "Authentication failed"

- Make sure you're using a Personal Access Token, not your password
- Generate a new token if the old one expired

### Issue: "Updates were rejected"

```bash
# Pull latest changes first
git pull origin main --rebase

# Then push
git push origin main
```

### Issue: "Large files warning"

- Make sure node_modules/ is in .gitignore
- Never commit node_modules/ to Git
- Users should run `npm install` after cloning

---

## Best Practices

1. ✅ **Commit Often** - Make small, focused commits
2. ✅ **Write Clear Messages** - Describe what changed and why
3. ✅ **Use Branches** - Create branches for new features
4. ✅ **Pull Before Push** - Always pull latest changes before pushing
5. ✅ **Never Commit Secrets** - Keep .env files out of Git
6. ✅ **Review Changes** - Use `git status` and `git diff` before committing

---

## GitHub Repository Settings (Optional)

### Enable GitHub Pages (Free Hosting)

1. Go to repository **Settings** → **Pages**
2. **Source:** Deploy from a branch
3. **Branch:** Select `main` and `/dist` folder
4. **Click Save**
5. Your site will be live at: `https://YOUR_USERNAME.github.io/kefa-technology-solutions`

**Note:** You'll need to build your project first:
```bash
npm run build
git add dist/
git commit -m "Add production build"
git push
```

### Add Topics (for discoverability)

1. Go to your repository
2. Click the gear icon next to "About"
3. Add topics: `react`, `typescript`, `vite`, `tailwindcss`, `website`, `business`

### Add Description

1. Click the gear icon next to "About"
2. Add description: "Official website for KEFA Technology Solutions - Technology, HR, and Training Services"
3. Add website URL if you have one

---

## Next Steps

1. ✅ Upload your code to GitHub (follow steps above)
2. ✅ Add README.md with project documentation
3. ✅ Set up .gitignore to exclude unnecessary files
4. ✅ Consider enabling GitHub Pages for free hosting
5. ✅ Share your repository URL with team members
6. ✅ Set up GitHub Actions for automated deployments (advanced)

---

## Support

If you encounter any issues:

1. Check GitHub's documentation: https://docs.github.com
2. Search for solutions on Stack Overflow
3. Review Git documentation: https://git-scm.com/doc

---

**Your KEFA Technology Solutions website is now ready to be version-controlled with Git and hosted on GitHub!** 🚀
