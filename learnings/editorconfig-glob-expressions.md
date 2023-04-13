# EditorConfig Glob Expressions

The sections in `.editorconfig` are filepath globs. They can be used to define config for certain files and directories:

```ini
root = true

[*]
indent_style = tab
indent_size = 2
insert_final_newline = true

# Match exact file package.json
[package.json]
indent_style = space

# Match .css files under test directory
[test/**/*.css]
insert_final_newline = false
```
