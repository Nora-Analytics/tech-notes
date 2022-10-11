# rename Master to Main

```bash
# On local
git branch -m master main
```

```bash
#Remote
git push -u origin main
```

```bash
# If remote already have master branch
git push origin --delete master
```
