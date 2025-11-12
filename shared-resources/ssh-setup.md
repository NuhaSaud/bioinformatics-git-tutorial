
# SSH Setup Guide (Recommended)

1. Generate key (Ed25519):
   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```
2. Copy `~/.ssh/id_ed25519.pub` and add it to **GitHub → Settings → SSH and GPG keys**.
3. Test:
   ```bash
   ssh -T git@github.com
   ```
4. Clone with SSH:
   ```bash
   git clone git@github.com:org/repo.git
   ```
---

