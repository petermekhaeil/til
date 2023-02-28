# Git: Work with multiple accounts

```bash
# Default GitHub account
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  
Host github.com-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_work
```

Use the new host:

```
git remote add origin git@github.com-work:username/repo.git
```
