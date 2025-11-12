
# 01 — Setup & Basics (Command Line)

## Install Git
- Windows: Git for Windows
- macOS: `brew install git`
- Linux: `sudo apt-get install git`

## First Repo
```bash
mkdir lab-docs && cd lab-docs
git init
echo "# Lab Protocols" > README.md
git add README.md
git commit -m "Initial commit: add README"
```

## Remote (SSH)
```bash
git remote add origin git@github.com:org/lab-docs.git
git branch -M main
git push -u origin main
```
---
**Author:** Dr. Nuha BinTayyash — 2025  

