# List the files with the most disk usage

```bash
du -h [DIRECTORY] | sort -hr | head -n 10
```

The `du` command returns the estimated disk usage used. 

- `-h`: Show sizes in human readable format (eg. 2K, 1G).

Use `sort` to organise the output:

- `-h`: Sort by human readable numbers (eg. 2K, 1G).
- `-r`: Reverse the output (so it is in descending order).

Show the top 10 items using `head`:

- `-[NUMBER]`: Number of lines to output (Default is 10).
