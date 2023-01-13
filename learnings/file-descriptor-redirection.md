# Redirect stderr to stdout using 2>&1

`2>&1` is used to redirect standard error (`stderr`) to standard output (`stdout`). It allows you to capture and handle both types of output in the same way.

## File descriptors

There are 3 [file descriptors](http://en.wikipedia.org/wiki/File_descriptor), represented by numbers:

- `0` [stdin](https://en.wikipedia.org/wiki/Standard_streams#Standard_input_(stdin))
- `1` [stdout](https://en.wikipedia.org/wiki/Standard_streams#Standard_output_(stdout))
- `2` [stderr](https://en.wikipedia.org/wiki/Standard_streams#Standard_error_(stderr))

## Redirection

`>` is used to redirect the output of a command to something else. 

## File descriptor

`&` indicates that what follows is a file descriptor (in the context of a redirection). It is required otherwise it will interpret the `1` as a filename (eg `2>1` would mean "redirect stderr to a file named 1").

## Putting it together

`2>&1` indicates that file descriptor 2 (`stderr`) should be redirected to file descriptor 1 (`stdout`).

## Examples

```bash
command > /dev/null 2>&1
```

The stdout of `command` is redirected to `/dev/null` and stderr is redirected to stdout. Meaning everything is redirected to `/dev/null`.

```bash
cat file.txt > output.txt 2>&1
```

Send the content of `file.txt` to `output.txt`. If any errors (eg. file does not exist), send it to stdout which is also `output.txt`.

```bash
ls -l ./apps/ ./packages 2> /dev/null
```

List the content of `./apps` and `./packages`. If there was any errors (eg. directory does not exist), send stderr to `/dev/null`.
