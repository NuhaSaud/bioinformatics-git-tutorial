
# 02 — Daily Workflow (Command Line)

```bash
git status
git add <file>     # or: git add -p
git commit -m "docs: update SOP titles"
git push
```
Inspect:
```bash
git diff
git diff --staged
git log --oneline --graph --decorate --all
```
Undo:
```bash
git restore <file>
git restore --staged <file>
git reset --soft HEAD~1
```
---

