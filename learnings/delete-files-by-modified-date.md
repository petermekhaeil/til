# Delete files by modified date

```bash
find ./my-folder -mtime +10 -type f -delete
```

- `-mtime +10`: Filter files that have a last modified date 10 days ago.
- `-type f`: Filter files only.
- `-delete`: Delete files matching the filters.
