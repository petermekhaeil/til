# Replace a Git Repository with a New One

Sometimes you need to reset a remote Git repository while keeping your local history intact. Here's how:

**1. Add the Remote:**
```bash
git remote add origin <remote-url>
```

Links your local repo to the remote.

**2. Force Push to Overwrite Remote History:**
```bash
git push --force --set-upstream origin main
```

Replaces the remote history with your local history.


