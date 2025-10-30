# 🧩 Git & Version Control

🗓️ Date: October 28, 2025  
📘 Module: Git and Version Control  

---

## 🧠 Summary

### What I Learned
In this module, I learned about **Git**, a version control system that helps developers track changes to files and collaborate on projects.  
I now understand what **repositories**, **commits**, **branches**, and **merges** are, and how **GitHub** is used to store and share code online.  

### Why It Matters
Version control is essential in DevOps because many engineers work on the same projects.  
Git keeps everything organized, prevents overwriting, and allows rollback when mistakes happen.  
It also connects directly with CI/CD tools like **Jenkins** and **GitHub Actions**.

### What I Practiced
- Installed Git and set up my user info.  
- Created a local repository using `git init`.  
- Added and committed files using `git add` and `git commit`.  
- Pushed changes to GitHub with `git push`.  
- Created and merged branches to test new features.

---

## 💻 Useful Commands

### 🔹 Git Setup
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git --version
```
### 🔹 Start a New Repositoery
```bash
git init                        # Create a new Git repository
git status                      # Check the current repo status
git add .                       # Stage all changes
git commit -m "Initial commit"  # Save the changes
git push                        # Push cahnges to Github
```
### 🔹 Branching and Merging
```
git branch feature1             # Create a new branch
git checkout feature1           # Switch to branch
git checkout -b feature1        # Create branch and switch to branch
git merge feature1              # Merge branch into main
git branch -d feature1          # Delete the branch
```
## 🧩 GitLab SSH Setup & Repo Clone

✅ Successfully cloned `git@gitlab.com:mrefosa-group/test_project.git`  
🎯 Verified SSH connection worked  
🗂️ Repo files downloaded correctly
✅ Successfully made changes to file, and pushed it to gitlab 


**Useful commands used:**
```bash
ssh-keygen -t ed25519 -C "you@example.com"
ssh-add ~/.ssh/id_ed25519
ssh -T git@gitlab.com
git clone git@gitlab.com:mrefosa-group/test_project.git
