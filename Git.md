# Git

## 1. Look for deleted Files in a git repository

-   This command will look for deleted files and their associated `SHA`.

```bash
git log --all --stat --diff-filter=D --oneline
```

-   Add a `-p|--path` to see the content of deleted files/file

```bash
git log --all --stat --diff-filter=D -p
```
