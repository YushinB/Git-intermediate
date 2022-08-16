# Create Tags

- Tags allow marking points in history as important
- A named reference to a commit
- Most often used to mark releases (v1.0, v1.1, v2.0)
- Can mark key features or changes (ecommerce redesign)
- Can mark points for team discussion (bug, issue 136)

```
# add lightweight tag
git tag issue136 655da716e7 <commit sha>

# add annotated tag (most common)
git tag -a v1.1 -m "version 1.0" <commit sha>

# combination
git tag -am <message> <tag name> <commit sha>
```
> if we not provide the commit sha, git will give head by default. 
