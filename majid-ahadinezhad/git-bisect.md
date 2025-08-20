# Git Bisect

Git Bisect is used to find the commit that introduced a bug using binary search.  

## Workflow Example

1. **Create a file and commit it**
```bash
echo "Hello World" > f1.txt
git add f1.txt
git commit -m "Add f1.txt with hello message"
```

2. **Make a second commit**
```bash
echo "Some content" > f2.txt
git add f2.txt
git commit -m "Add f2.txt"
```

3. **Introduce a bug**
```bash
echo "error" > f1.txt
git add f1.txt
git commit -m "Introduce bug in f1.txt"
```

4. **Start bisecting to find the bad commit**
```bash
git bisect start
git bisect bad       # Current commit has the bug
git bisect good HEAD~2  # The commit 2 steps back is good
```

5. **Test each suggested commit**
```bash
# If bug exists
git bisect bad

# If bug does not exist
git bisect good
```

6. **Finish bisect**
```bash
git bisect reset
```

Git will tell you which commit introduced the bug.

