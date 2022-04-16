# Using GitHub Actions to push changes

We can use [GitHub Actions](https://docs.github.com/en/actions) to push a new commit each time there is a new change detected. 

I've recently had to do this to automate updating `README.md` with a listing of the repository files each time a new push has been detected. The GitHub workflow is found [here](https://github.com/petermekhaeil/til/blob/master/.github/workflows/update.yml).

Here are the learnings that may come useful to others:

## Using bash to clear file content

```bash
cat /dev/null > README.md
```
`/dev/null` is a pseudo file in Linux that has no output so we can override a file with this empty content.

## Using bash to echo a string with new line

```bash
echo -e '# Today I Learned\n' > README.md
```

`-e` is required to escape backslashes. This allows us to print new line (`\n`) when outputting to a file.

## Using bash to read the first line of a file

```bash
head -n 1 $filename
```

## Using bash to remove characters from a string

```bash
echo '# Title' | sed 's/# //'
```

`sed` is short for `Stream EDitor` and one of its common uses is pattern replacement. The above will remove `# ` from the string (by replacing it with an empty string).

## Using bash to append string to file

```bash
echo 'My string' >> README.md
```

The `>>` operator is used to append to a file (or create the file if it does not exist).

## Using GitHub Actions to push changes to a repository

[actions/checkout](https://github.com/actions/checkout) is an offical GitHub Action that can checkout a repository. We can also use this to [push changes back](https://github.com/actions/checkout#Push-a-commit-using-the-built-in-token).

```yml
on: push
jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: |
          # Clear README.md
          cat /dev/null > README.md

          # Add Title
          echo -e '# Today I Learned\n' > README.md

          # Loop through all TILs and add to README.md
          dir=./learnings
          for filename in "$dir"/*
          do
            title=$(head -n 1 $filename | sed 's/# //')
            echo "- [$title](https://github.com/petermekhaeil/til/blob/master/$filename)" >> README.md
          done

          # Push changes
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add README.md
          git commit -m "Update README.md"
          git push
```
