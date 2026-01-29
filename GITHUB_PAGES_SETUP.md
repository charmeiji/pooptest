# GitHub Pages Setup Instructions

## Step 1: Update Git Configuration (Optional but Recommended)

Before pushing to GitHub, you may want to set your real name and email:

```bash
git config user.name "Your Real Name"
git config user.email "your-email@example.com"
```

Or set it globally for all repositories:
```bash
git config --global user.name "Your Real Name"
git config --global user.email "your-email@example.com"
```

## Step 2: Create a GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **"+"** icon in the top right corner
3. Select **"New repository"**
4. Fill in the repository details:
   - **Repository name**: `nekoweb1` (or any name you prefer)
   - **Description**: (optional) "My personal website"
   - **Visibility**: Choose **Public** (required for free GitHub Pages)
   - **DO NOT** initialize with README, .gitignore, or license (we already have files)
5. Click **"Create repository"**

## Step 3: Push Your Code to GitHub

**Have you created the GitHub repository yet?** If not, go back to Step 2 first!

After creating the repository, follow these steps:

### Option A: Using HTTPS (Recommended for beginners)

1. **Add the remote repository** (replace `YOUR_USERNAME` with your actual GitHub username):
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/nekoweb1.git
   ```
   ⚠️ **If you get an error "remote origin already exists"**, run this first:
   ```bash
   git remote remove origin
   ```
   Then try the command again.

2. **Rename your branch to 'main'** (GitHub's default):
   ```bash
   git branch -M main
   ```

3. **Push your code**:
   ```bash
   git push -u origin main
   ```

4. **When prompted**:
   - **Username**: Enter your GitHub username
   - **Password**: Enter your **Personal Access Token** (NOT your GitHub password)
     - See instructions below for creating a token

### Option B: Using GitHub CLI (if you have it installed)

If you have GitHub CLI installed, you can use:
```bash
gh repo create nekoweb1 --public --source=. --remote=origin --push
```

### Troubleshooting Common Issues

**Error: "remote origin already exists"**
```bash
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/nekoweb1.git
```

**Error: "authentication failed"**
- Make sure you're using a Personal Access Token, not your password
- See instructions below for creating a token

**Error: "repository not found"**
- Make sure you've created the repository on GitHub first
- Check that the repository name matches exactly
- Make sure the repository is set to Public (not Private)

### Creating a Personal Access Token

1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click **"Generate new token (classic)"**
3. Give it a name like "GitHub Pages"
4. Select scopes: check **"repo"** (this includes all repository permissions)
5. Click **"Generate token"**
6. **Copy the token immediately** (you won't see it again!)
7. Use this token as your password when pushing

## Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **"Settings"** (top menu)
3. Scroll down to **"Pages"** in the left sidebar
4. Under **"Source"**, select:
   - **Branch**: `main`
   - **Folder**: `/ (root)`
5. Click **"Save"**

## Step 5: Access Your Website

After a few minutes, your website will be live at:
```
https://YOUR_USERNAME.github.io/nekoweb1/
```

Replace `YOUR_USERNAME` with your actual GitHub username and `nekoweb1` with your repository name if different.

## Updating Your Website

Whenever you make changes to your website:

```bash
git add .
git commit -m "Description of your changes"
git push
```

Your changes will be live on GitHub Pages within a few minutes!
