# Git Cherry-Pick

Git Cherry-Pick is used to apply a commit from one branch onto another branch.

## Workflow Example

1. **Start from main branch**
```bash
git checkout main
```

2. **Create a feature branch and make commits**
```bash
git checkout -b feature
echo "Feature 1" > f3.txt
git add f3.txt
git commit -m "Add f3.txt"

echo "Feature 2" > f4.txt
git add f4.txt
git commit -m "Add f4.txt"
```

3. **Go back to main and cherry-pick a commit**
```bash
git checkout main
git cherry-pick <commit-hash-of-f3.txt>
```

4. **Resolve conflicts if needed**
```bash
# Edit conflicting files
git add <file>
git cherry-pick --continue
```

5. **Result**
The changes from the feature branch are applied to main without merging the entire branch.

