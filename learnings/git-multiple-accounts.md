# Git: Work with multiple accounts

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

Use the new host:

```
git remote add origin git@github.com-work:username/repo.git
```
