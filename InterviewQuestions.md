# Questions from the interviewer 
## swift
## what is the difference between a struct and an enum?

### what is copy on write?


## combine

### what is `zip`?

### what is the difference between `flatMap` for an array and `flatMap` in combine?


## git
### What is the difference between `merge` and `rebase`?
Merge lets you merge different Git branches. Rebase allows you to integrate the changes from one branch into another. Merge logs show you the complete history of commit merging. Rebase logs are linear.

How rebase works:
We are on branch-A and want to reabase the branch-B into branch-A. We are calling `git rebase branch-B`.


1. The commits on branch-A until the common ancestor with branch-B are removed and temporarly "parked".

![Screenshot 2023-04-27 at 09 51 24](https://user-images.githubusercontent.com/34369988/234896435-c19c9962-2192-4aba-a7ed-dbb3e1df5a51.png)
  
2. The commits from branch-B are are added to branch-B.

![Screenshot 2023-04-27 at 09 51 08](https://user-images.githubusercontent.com/34369988/234903311-4f5ada49-0d07-49c1-9047-06f5d7657688.png)

4. The "parked" commits from branch-A are added on top. The history is rewritten now and one line.

![Screenshot 2023-04-27 at 09 50 55](https://user-images.githubusercontent.com/34369988/234903121-fa2edfc3-5d30-4819-8886-fe61a78497ae.png)

Do NOT use REbase on commits that you've already pushed/shared on a remote repository!
Instead, us it for cleaning up your local commit history before merging it into a shared team branch.

# Questions to the interviewer 

- What would be your expectations to make the hiring a success?
- For what are you looking for in a team mate?
