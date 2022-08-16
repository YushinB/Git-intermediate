# Interactive staging

- Stage changes interactively
- Allow staging portions of changed files
- Helps to make smaller, forcused commits.
- Feature of many GIT GUI tools

```
git add --interactive

git add -i
```

![image](https://user-images.githubusercontent.com/34083808/184797491-2af9bb47-f23c-452f-a3ed-3688c6a7ba7c.png)

# Patch mode

We can use this command to stash portion of file to be commit.

```
git add --patch
git add -p

git stash -p
git reset -p
git checkout -p
git commit -p
```
