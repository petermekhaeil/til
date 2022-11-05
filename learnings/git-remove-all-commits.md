# Git Remove All Commits

Clean up history from a repository by removing the git commits and replacing it with a new single commit.

1. Create a temporarily branch disconnected from all the other branches and commits:

```bash
git checkout --orphan temp_branch
```

2. Add the files to new temporarily branch:

```bash
git add -A
```

3. Commit the changes:

```bash
git commit -am "First commit"
```

4. Delete the main branch:

```bash
git branch -D master
```

5. Rename temporarily branch to the main branch:

```bash
git branch -m master
```

6. Force push the new main branch:

```bash
git push -f origin master
```
