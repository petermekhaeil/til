# Show contents of Git stash

To show list of files in the most recent Git stash:

```bash
git stash show
```

To show the diff:

```bash
git stash show -p
```

To show content of nth most recent stash:

```bash
git stash show -p stash@{n}
```
