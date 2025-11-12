
# 05 — Troubleshooting (Command Line)

- origin exists → `git remote set-url origin git@github.com:org/repo.git`
- Permission denied → add SSH key; test `ssh -T git@github.com`
- Abort merge → `git merge --abort`
- Remove big file from history → prefer not needed for docs-only repos; otherwise consult filter-repo/BFG.
---


