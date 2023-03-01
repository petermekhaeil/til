# Git: Work with multiple accounts

- Configure multiple host aliases in git configuration:

```bash
# ~/.gitconfig

Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  
Host github.com-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_work
```

- To use a different name and email, add [conditional includes](https://git-scm.com/docs/git-config#_conditional_includes) in git configuration to supply a different `.gitconfig` path based on working directory.

```
# ~/.gitconfig

[user]
    name = Default Name
    email = default.name@example.com

[includeIf "gitdir:~/work/"]
    path = ~/work/.gitconfig
```

```bash
# ~/work/.gitconfig

[user]
    name = Work Name
    email = work.email@example.com
```

- Use the new host alias as remote url:

```bash
git remote add origin git@github.com-work:username/repo.git
```
