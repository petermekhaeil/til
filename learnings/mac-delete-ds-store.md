# Recursively delete .DS_Store

Delete all `.DS_Store` found within a directory recursively:

```bash
find . -name '.DS_Store' -type f -delete -print
```

`-print` will also print the path of the file when deleting.
