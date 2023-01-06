# Delete lines in vi

You can delete a single or multiple lines in normal mode:

- **Delete a single line:** `dd`
- **Delete multiple lines:** `[n]dd` (n = number of lines)

You can delete a range of lines in command mode:

- **Delete range of lines:** `:[from],[to]d`

There is special characters you can use in the range:

- `.`: The current line.
- `$`: The last line.
- `%`: All lines.

Examples on using the range:

- `:5,10d`: Delete lines from 5 to 10.
- `:.,$d`: Delete from the current line to the end of file.
- `:.,1d`: Delete from the current line to the beginning of file.
- `:5,$d`: Delete from line 5 to end of file.
- `:%d`: Delete all lines.
