# Using the `tar` command

## Create a compressed tar archive

```bash
$ tar -czvf archive.tar.gz ./directory
```

- `-c`: Create archive.
- `-z`: Compress using `gzip` algorithm.
- `-f`: Specify filename of archive.
- `-v`: Verbose (show progress).

## Uncompress a tar archive

```bash
$ tar -xvf archive.tar.gz
```

- `-x`: Extract from archive.
- `-f`: Specify filename of archive.
- `-v`: Verbose (show progress).

## Extract tar archive to a different directory

```bash
$ tar -xvf archive.tar.gz -C ./another-directory
```

- `-C`: Changes the directory.

## Extract specific files from tar archive

```bash
$ tar -xvf archive.tar.gz file1 file2 file3
```

## Extract specific files from tar archive using wildcard

```bash
$ tar -xvf archive.tar.gz --wildcards '*.js'
```

## List the content of tar archive

```bash
$ tar -tf archive.tar.gz
```

- `-t`: List the content.

