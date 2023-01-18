# Checkout previous branch in Git

- `git checkout -` is a shorthand for `git checkout @{-1}`. It will checkout the last previous branch.
- `@{-1}` refers to the last branch that was checked. It can be used with `git checkout @{-1}` to checkout the previous branch.
- You can also checkout the N-th last branch using `git checkout @{-N}`.
