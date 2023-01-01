# Restore a deleted file in Git

Find the commits that contain the file. Take note of the last commit that deleted the file:

```bash
git log --all --full-history --oneline -- <file-path>
```

- `--all`: Show commits in all branches, tags and refs.
- `--full-history`: Show full history of commits.
- `--oneline`: Pretty format because we only need the commit hash.

Restore the file by checking out the commit that happened before it was deleted:

```bash
git checkout <deleting-commit>^ -- <file-path>
```

The `^` means "parent of" - in the above example, it means checkout the parent commit of the deleting commit. This would contain the file and its content before it was deleted.
