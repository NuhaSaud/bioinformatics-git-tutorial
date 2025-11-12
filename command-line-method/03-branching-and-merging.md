
# 03 — Branching & Merging (Command Line)

```bash
git checkout -b protocol/improve-qc
# edit files...
git add .
git commit -m "sop: improve QC steps"
git push -u origin protocol/improve-qc
```
Merge:
```bash
git checkout main
git pull
git merge protocol/improve-qc
git push
```
Resolve conflicts by editing markers then:
```bash
git add <file>
git commit
```
---


