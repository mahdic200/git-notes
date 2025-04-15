# Pruning Branches

When you run:

```bash
git branch -a
```

You’re seeing both local (`assets`, `master`) and remote tracking branches (`remotes/origin/*`).

To **remove remote branches**, it depends on what you want:

---

### 🔥 Remove a remote branch from the actual remote (e.g., GitHub):

If you have permission and want to **delete the branch on the server**:

```bash
git push origin --delete <branch-name>
```

Example:

```bash
git push origin --delete master-old
```

This will delete `origin/master-old` from the remote.

---

### 🧹 Clean up local references to deleted remote branches:

If a branch was already deleted on the remote, but you're still seeing it locally under `remotes/origin/*`, run:

```bash
git remote prune origin
```

That will clean up any stale branches locally that no longer exist remotely.

---

Let me know if you're trying to _just clean your local view_, or if you want to _actually remove branches from the server_.

