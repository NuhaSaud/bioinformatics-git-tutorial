
# Universal Troubleshooting

- **Permission denied (publickey):** Ensure SSH remote + key added; run `ssh -T git@github.com`
- **remote origin already exists:** `git remote set-url origin git@github.com:org/repo.git`
- **Merge conflicts:** Coordinate; resolve via your tool's merge UI or edit markers; commit
- **Accidentally tracked big files:** `git rm --cached <file>` then commit; avoid committing raw data
---

