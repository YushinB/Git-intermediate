# Force push to a remote
## Reasons to Force Push
* Local version is better than the remote version
* Remote version went wrong and needs repair. 
* Version have diverged and merging is undersirable. <br>

```
git push -f
git push --force
```
after using ``` git push -f```, other user need to use command ``` git reset --hard orign/[branch name]``` to reflect change from remote branch. 

## when we user the force push remote. 
please see the below case. <br>

<img src="https://user-images.githubusercontent.com/34083808/184617110-d2f70333-6bd4-40be-afd2-0fe2970ba537.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />

We make a commit on our local branch and in the same time, other person make a change on our remote branch.

<img src="https://user-images.githubusercontent.com/34083808/184617731-3c462aec-cae9-4a54-b183-ac53b4f2bc2d.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />

normaly, we will fetch the change from remote repo to our local repo. 


<img src="https://user-images.githubusercontent.com/34083808/184617837-0f1f652c-9fde-474f-af27-d4e20d9714b0.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />

and merge to our branch.

<img src="https://user-images.githubusercontent.com/34083808/184618042-8a438210-f80d-4130-b8c0-0ec6707789ea.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />
     
then push to our remote repository.


<img src="https://user-images.githubusercontent.com/34083808/184618118-df23c1fe-8fd9-42f2-a110-6cc385cb62e4.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />
     
 > but with force push command, we force our local branch will be push to remote branch and replace remote branch with our local branch. It will look somthing like below. <br> 
 
 <img src="https://user-images.githubusercontent.com/34083808/184618662-a0f5b724-11f1-4c19-8444-7ea2186c516d.png"
     alt="Force Push 01"
     style="float: left; margin-right: 10px; width: 500px" />

> please use with extreme caution because it will anger your whole team, disruptive for other using the remote branch, commits will disappear and subsequent commits are orphaned. 

# Identify Merged Branches.
* List branches that have been merged into a branch.
* Useful for knowing what features have been incorporated. 
* Useful for cleanup after merging many features.

```
# check branch have been merge to current branch
git branch --merged

# check branch not yet been merge to current branch
git branch --no-merged

# r for remote branch
git branch -r --merged
```
