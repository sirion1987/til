# Sync repository

```
$ rsync -r --exclude '.git' <old_path> <new_path>
```

# Recover a commit

```
$ git reflog
```

Choose SHA1_ID

```
$ git cherry-pick <SHA1_ID>
```

Delete remote branch

```
$ git push origin --delete <branch_name>
```
