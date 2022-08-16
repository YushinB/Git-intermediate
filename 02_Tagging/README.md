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

# List tags

```
git tag
git tag --list
git tag -l

# List tags beginning with "v2"
git tag -l "v2*"

# list tags with annotations
git tag -l -n

# work with tags (like SHAs)
git show v1.1

git diff v1.0..v1.1
```

# Delete tags

```
git tag --delete v1.1
git tag -d v1.1
```

# push tags to a remote

- like branches tags are local unless shared to a remote
- **git push** dose not transder tags
- Tags mush be explicitly transferred.
- **git fetch** automatically retrieves shared tags

```
# push a tag to a remote server
git push origin v1.1

# Push all tags to a remote server
git push origin --tag

# fetch commits and tags
git fetch

# fetch only tags
git fetch --tag

# delte remote tags
git push origin :v1.1
git push --delete origin v1.1
git push -d origin v1.1
```

# Checking out tags

- Tags are not branches
- Tags can be checked out, just like any commit
- ` git checkout -b new_branch v1.1`
- ` git checkout v1.1`

![image](https://user-images.githubusercontent.com/34083808/184794173-1b9fcd8e-d7b8-4c6b-bc65-eff472d67915.png)

if we checkout the tag v1.1, I will move the head of directory back to the commit c69ba, we can checkout the master branch again to get back on the previous postion.

![image](https://user-images.githubusercontent.com/34083808/184794632-f80c52dd-b450-4c97-8ac9-386b13173596.png)

## Detached HEAD state

- Checking out a commit puts the local repository in a " detached HEAD state"
- like being on an unnamed branch
- New commits will not belong to any branch.
- Detached commits will be garbage collected (~ 2 weeks)

> if we move our head to v1.1 tag then make further development, it will be on the unnamed branch, which we don't know. after that we checkout the master branch, then there no easy way to git back to unnamed branch. That's the detached head state.

![image](https://user-images.githubusercontent.com/34083808/184796037-fc5a63ae-3f21-4cdf-b56f-74ce8a1b213c.png)

there are fews way that you can preserve that works

```
# tag the commit (HEAD detached)
git tag temp

# Create a branch (HEAD detached)
git branch temp_branch

# Create a branch and reattach HEAD
git checkout -b tem_branch
```
