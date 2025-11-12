
# 05 — Troubleshooting (VSCode)

#### 🚨 Git Problem Solving in VSCode

| Problem | VSCode Solution | Command Alternative |
|---------|-----------------|-------------------|
| **Authentication Failed** | Command Palette → "Git: Clone" → Enter credentials | Set up SSH keys |
| **Merge Conflicts** | Click conflicted file → Use merge editor | Manual editing |
| **Uncommitted Changes** | Source Control → Stash changes | `git stash` |
| **Wrong Branch** | Status bar → Switch branch | `git checkout [branch]` |
| **Undo Last Commit** | Command Palette → "Git: Undo Last Commit" | `git reset --soft HEAD~1` |
| **Discard Changes** | Source Control → Right-click file → "Discard Changes" | `git checkout -- [file]` |
### Problem 1: VSCode Not Showing Git Changes

#### Symptoms:
- Source Control panel empty
- No file modification indicators
- Git operations not working

#### VSCode-Specific Solutions:

**Check Git Repository Status:**
1. **Command Palette** (`Ctrl+Shift+P`) → "Git: Show Git Output"
2. Look for error messages in Git output panel

**Reinitialize Git in VSCode:**
```bash
# In VSCode terminal (Ctrl+`)
cd your-project-folder
git status  # Check if in Git repo
ls -la      # Look for .git folder
```

**VSCode Settings Check:**
1. **File** → **Preferences** → **Settings**
2. Search for "git.enabled" 
3. Ensure it's set to `true`
4. Check "git.path" points to correct Git installation

**Quick Fixes:**
```json
// In .vscode/settings.json
{
    "git.enabled": true,
    "git.decorations.enabled": true,
    "git.autorefresh": true
}
```

### Problem 2: Authentication Issues in VSCode

#### HTTPS Token Problems:

**VSCode Credential Manager:**
1. **Command Palette** → "Git: Clone"
2. When prompted for credentials:
   - Username: Your GitHub username
   - Password: Personal Access Token (not your password!)

**Update Stored Credentials:**
1. **Windows**: Control Panel → Credential Manager → Windows Credentials
2. **Mac**: Keychain Access → GitHub entries → Update
3. **Linux**: 
   ```bash
   git config --global credential.helper store
   ```

#### SSH Setup for VSCode:

**Test SSH in VSCode Terminal:**
```bash
# Open terminal in VSCode (Ctrl+`)
ssh -T git@github.com
```

**Convert Repository to SSH:**
1. **Command Palette** → "Git: Remote Set URL"
2. Enter SSH URL: `git@github.com:username/repo.git`
3. **Or use terminal:**
   ```bash
   git remote set-url origin git@github.com:username/repo.git
   ```

### Problem 3: Merge Conflicts in VSCode

#### VSCode Merge Conflict Interface:

**Visual Conflict Resolution:**
1. **Conflicted files** show with `!C` indicator
2. **Click the file** to open merge editor
3. **VSCode shows**:
   - **Current Change** (your changes)
   - **Incoming Change** (others' changes)  
   - **Result** (combined result)

**Resolution Options:**
- **Accept Current Change**
- **Accept Incoming Change**  
- **Accept Both Changes**
- **Ignore**
- **Edit manually**

**Step-by-Step Resolution:**
```markdown
## In conflict file, you'll see:
<<<<<<< HEAD
Your version of the text
=======
Their version of the text  
>>>>>>> branch-name

## VSCode provides clickable options above each section:
Accept Current Change | Accept Incoming Change | Accept Both Changes...
```

**After Resolving:**
1. **Stage resolved files**: Click `+` in Source Control
2. **Commit**: Write merge commit message
3. **Push**: Sync changes

#### Advanced Merge Tools in VSCode:

**Install GitLens for Better Conflict Resolution:**
1. **Extensions** → Search "GitLens"
2. **Features unlocked**:
   - Line-by-line history
   - Blame annotations  
   - Better diff views
   - File history comparison

### Problem 4: Large Files and Performance

#### .gitignore Configuration in VSCode:

**Create .gitignore:**
1. **Right-click** in Explorer → **New File** → `.gitignore`
2. **Use template** for bioinformatics projects:

```bash
# .gitignore for Bioinformatics Projects

## Large Data Files
*.fastq
*.fastq.gz
*.fasta.gz
*.fasta
*.fa
*.bam
*.sam
*.vcf
*.vcf.gz
*.bcf

## Analysis Output
results/
output/
temp/
tmp/
cache/

## Sequence Analysis
*.blast
*.blastx
*.blastn
*.psi
*.phi

## R/Statistical Analysis
.Rhistory
.RData
.Rproj.user/
*.Rproj

## Python
__pycache__/
*.pyc
*.pyo
.env

## IDEs and Editors
.vscode/launch.json
.vscode/tasks.json
*.swp
*.swo
*~

## OS Generated
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

## Personal Notes
personal-notes.md
TODO.md
scratch.md

## Credentials and Keys
*.key
*.pem
api-keys.txt
passwords.txt
.env.local
.secrets

## Large Reference Files
reference-genomes/
databases/
*.gb
*.gbk
*.gff
*.gtf

## Temporary Analysis Files
*.tmp
*.temp
*.log
analysis_*.txt
temp_analysis/

## Compressed Archives (if large)
*.tar.gz
*.tar.bz2  
*.zip
*.7z

## Jupyter Notebooks (checkpoints)
.ipynb_checkpoints/

## Documentation builds
docs/_build/
site/
```

**VSCode Features for .gitignore:**
1. **File Association**: VSCode recognizes `.gitignore` syntax
2. **IntelliSense**: Autocomplete for common patterns
3. **Extensions**: "gitignore" extension provides templates

#### Git LFS Integration in VSCode:

**For Large Files That Must Be Tracked:**
```bash
# Install Git LFS
git lfs install

# Track specific file types
git lfs track "*.fastq.gz"
git lfs track "*.bam"

# Add .gitattributes to repository
git add .gitattributes
git commit -m "Configure Git LFS for large files"
```

### Problem 5: Branch Management Issues

#### VSCode Branch Operations:

**Branch Switching Problems:**
1. **Uncommitted changes**: 
   - VSCode prompts to commit or stash
   - **Stash**: `Ctrl+Shift+P` → "Git: Stash"
   - **Commit**: Stage and commit in Source Control

2. **Branch not appearing**:
   - **Fetch**: `Ctrl+Shift+P` → "Git: Fetch"  
   - **Refresh**: `Ctrl+Shift+P` → "Git: Refresh"

**Create Branch from Specific Commit:**
1. **GitLens Graph View**: Shows visual commit history
2. **Right-click commit** → "Create Branch from Commit"
3. **Or Command Palette**: "Git: Create Branch From..."

### Problem 6: VSCode Git Extension Issues

#### Reset Git Extensions:

**Disable/Re-enable Git:**
1. **Command Palette** → "Developer: Reload Window"
2. **Extensions** → Find Git-related extensions
3. **Disable** → **Enable** → **Reload**

**Check Git Path:**
```json
// Settings.json
{
    "git.path": "/usr/bin/git",  // Linux/Mac
    "git.path": "C:\\Program Files\\Git\\bin\\git.exe"  // Windows
}
```

#### Common Extension Conflicts:

**Conflicting Extensions:**
- Multiple Git extensions can conflict
- **Disable unnecessary ones**:
  - Git History vs GitLens (choose one)
  - Multiple GitHub extensions

**Reset VSCode Git State:**
```bash
# Close VSCode completely
# Delete VSCode workspace settings
rm -rf .vscode/
# Reopen and reconfigure
```

### Problem 7: Performance Issues with Large Repositories

#### VSCode Optimization for Large Repos:

```json
// .vscode/settings.json for performance
{
    "git.decorations.enabled": false,
    "git.autorefresh": false,  
    "search.useIgnoreFiles": true,
    "search.exclude": {
        "**/data/**": true,
        "**/results/**": true,
        "**/*.fastq": true,
        "**/*.bam": true
    },
    "files.watcherExclude": {
        "**/data/**": true,
        "**/results/**": true
    }
}
```

**Exclude Large Directories from VSCode:**
1. **Settings** → **Files: Watcher Exclude**
2. **Add patterns** for data directories
3. **Restart VSCode** for changes to take effect
