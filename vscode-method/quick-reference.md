
# Quick Reference — VSCode
### VSCode Git Cheat Sheet

#### 🎯 Essential VSCode Git Shortcuts

| Action | Shortcut | Alternative Method |
|--------|----------|-------------------|
| **Open Source Control** | `Ctrl+Shift+G` | Activity Bar → Source Control icon |
| **Command Palette** | `Ctrl+Shift+P` | View → Command Palette |
| **Quick Open** | `Ctrl+P` | File → Quick Open |
| **Git Commands** | `Ctrl+Shift+P` → "Git:" | Source Control → "..." menu |
| **Stage All Changes** | `Ctrl+Shift+A` | Source Control → "+" next to Changes |
| **Commit** | `Ctrl+Enter` | Source Control → ✓ checkmark |
| **Push/Pull** | `Ctrl+Shift+P` → "Git: Push/Pull" | Status bar sync button |


#### 📱 VSCode Git Status Indicators

| Indicator | Meaning | Location |
|-----------|---------|----------|
| **M** | Modified file | File Explorer |
| **U** | Untracked file | File Explorer |
| **D** | Deleted file | File Explorer |
| **A** | Added file | File Explorer |
| **C** | Conflicted file | Source Control |
| **!** | Ignored file | File Explorer |
| **Number badge** | Pending changes count | Activity Bar icon |


#### 📁 VSCode Panel Navigation

| Panel | Shortcut | Usage |
|--------|----------|-------|
| **Explorer** | `Ctrl+Shift+E` | File and folder management |
| **Search** | `Ctrl+Shift+F` | Find across all files |
| **Source Control** | `Ctrl+Shift+G` | Git operations |
| **Extensions** | `Ctrl+Shift+X` | Install/manage extensions |
| **Terminal** | `Ctrl+Shift+`` | Command line access |

#### 🔄 Git Workflow in VSCode

| Task | VSCode Method | Command |
|------|---------------|---------|
| **Initialize Repository** | Command Palette → "Git: Initialize Repository" | `git init` |
| **Clone Repository** | Command Palette → "Git: Clone" | `git clone [url]` |
| **Create Branch** | Status bar branch → "Create new branch" | `git checkout -b [name]` |
| **Switch Branch** | Status bar branch → Select branch | `git checkout [branch]` |
| **Stage Changes** | Source Control → Click `+` | `git add [file]` |
| **Unstage Changes** | Source Control → Click `-` | `git reset [file]` |
| **Commit Changes** | Source Control → Write message + `Ctrl+Enter` | `git commit -m "message"` |
| **Push Changes** | Source Control → "Sync Changes" | `git push` |
| **Pull Changes** | Source Control → "..." → "Pull" | `git pull` |

#### 🔍 Viewing Git Information

| Information | VSCode Location | Description |
|-------------|-----------------|-------------|
| **Current Branch** | Status bar (bottom-left) | Shows active branch name |
| **File Status** | Explorer panel | M=Modified, U=Untracked, D=Deleted |
| **Pending Changes** | Source Control badge | Number of uncommitted changes |
| **Git History** | GitLens → File History | Commit history for current file |
| **Blame Information** | GitLens inline annotations | Who changed each line |
| **Repository Status** | Source Control panel | All changed files |

#### 📝 Markdown Features for Documentation

| Feature | Shortcut | Usage |
|---------|----------|-------|
| **Preview Markdown** | `Ctrl+Shift+V` | View formatted version |
| **Side-by-side Preview** | `Ctrl+K V` | Edit and preview simultaneously |
| **Document Outline** | `Ctrl+Shift+O` | Navigate to sections quickly |
| **Bold Text** | `Ctrl+B` | **Bold formatting** |
| **Italic Text** | `Ctrl+I` | *Italic formatting* |
| **Insert Link** | `Ctrl+K` | [Link text](URL) |

#### 📊 GitHub Integration (Extension)

| Feature | Access Method | Description |
|---------|---------------|-------------|
| **View Pull Requests** | Activity Bar → GitHub icon | See open PRs |
| **Create Pull Request** | Source Control → "Create Pull Request" | Direct PR creation |
| **Review Changes** | GitHub panel → Select PR | Review and comment |
| **View Issues** | GitHub panel → Issues tab | See assigned issues |
| **Merge PR** | GitHub panel → Merge button | Complete PR workflow |

#### 🔍 Advanced Search and Navigation

| Feature | Shortcut | Usage |
|---------|----------|-------|
| **Search in Files** | `Ctrl+Shift+F` | Find text across repository |
| **Go to File** | `Ctrl+P` | Quick file opening |
| **Go to Symbol** | `Ctrl+Shift+O` | Navigate to headings in markdown |
| **Go to Line** | `Ctrl+G` | Jump to specific line number |
| **Find and Replace** | `Ctrl+H` | Replace text in current file |

