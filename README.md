# Merge Conflicts

- The following is a guided project that will help you understand merge conflicts.

## Description

- Throughout your Lambda School experience thus far you have learned how to work with Git/GitHub and have had practice using the basic commands for staging, commiting, pushing and publishing your commits to a fork. Learning now, the rest of what you need in order to work as a productive member of a product organization will set you up for success not only in labs, but give you insight into what how the product teams work in the real world.

## Purpose

- Knowing how to resolve merge conflicts is absolutely vital for you to succeed as a tech professional. That is the purpose of this exercise.

## Objectives

- By the end of this guided project you will have demonstrated the following:
  - You will be able to create a _branch_ off of the **main** branch of a repository.
  - You will be able to _rebase_ the **main** branch onto your feature branch.
  - You will be able to resolve any _merge conflicts_ that come up.

## Introduction

The following is a list of steps and instructions on how to complete this guided project.

- **Step 1️⃣:** Fork this repo into your personal account, then clone this repository by clicking the green **Clone or Download** (or new **Code**) button in the top right.
  ![Clone/Download](https://tk-assets.lambdaschool.com/054e5ad4-75cd-4b98-b929-7bf453bc8263_ScreenShot2020-04-13at7.31.05AM.png)
- **Step 2️⃣:** CD into the repository and create a branch off of the main branch.
  - Name the branch **"feature/add-name"** `git checkout -b feature/add-name`
  - **note**: this is a common naming convention. In labs you will often use the Jira issue number in your branch.
  - Once the branch is created run `git status` to ensure that you've switched to the new branch. (You should be in the habit of doing this by the end of your first sprint in labs).
- **Step 3️⃣:** Now that you have created your branch you're ready to work on the repo. Our task for the day is to have you add your name to the list below (**note** the semantically chosen branch name you created coincides with the task at hand) the `### Your name` heading to the end of this README.md file.
- **Step 4️⃣:** Run your typical staging, commit and publish commands:
  - `git status` - should only show the one file as modified
  - `git add <file-name>` - try to practice only adding files that support your commit message
  - `git commit -m 'your message'`
  - 💥**note:** you're committing to your branch NOT to the main branch. (!!VERY IMPORTANT!!)💥
- **Step 5️⃣:** Now lets make a change on the main branch that represents the work from another developer
  - `git checkout main`, `git pull` will put us on the main branch and update it
  - Now lets add `### Space Ghost` to the end of this README.md file.
  - Once again, stage and commit this change
  - `git status` , `git add <file-name>` , `git commit -m 'your message'` , `git push`.
  - **note** this is a fork so you will be able to push to the main branch, typically this will not be allowed in production repos.
- **Step 6️⃣:** Pull down the main branch onto your new feature branch. The easiest way to do this is to simply run `git rebase origin/main` **but make sure you're on your branch first**.
  - `git status` or `git brach` - confirm you are on your feature branch
  - `git checkout feature/add-name` - switch to feature branch
  - `git rebase origin/main`
- **Step 7️⃣** Resolve any merge conflicts.
  - You should see a merge conflict that looks something like this:
    ![merge conflict](https://tk-assets.lambdaschool.com/dd45683f-788d-4bd9-832e-ed901151615f_ScreenShot2020-04-13at8.38.36AM.png)
  - To resolve this, you need to go into that file (could be many files depending on how active your team is in the repo) and remove the markers (`<<<<<<< HEAD`, `=======`, and `>>>>>>> commit id`) and decide which lines of code to remove/keep. In this exercise you can keep both lines.
  - `💡Pro Tip: Once you've done this a few times manually, VSCode has an amazing built in Merge Conflict extension that will step you through the process.`
  - **note**: At this point you have a _dirty_ rebase (merge) and you need to stage the changed files then resume your merge.
  - `git add <file-name>`
- **Step 8️⃣:** Continue the rebase merge
  - `git rebase --continue`
  - You will be presented with a commit message prompt in an editor. The commit message should be the message from the last commit on your branch. Save this file and close it. (In the vi editor simply hold shift and press zz [ZZ])
  - you should see the following message from git
```
> git rebase --continue
[detached HEAD 4b461e1] add my name
 1 file changed, 2 insertions(+), 1 deletion(-)
Successfully rebased and updated refs/heads/merge-conflict.
```

Nice job!! You've walked thru the process of dealing with a merge conlict. You can apply this process to all merges and the only difference will be that step 7 may have more lines of code or files to be resolved.

### Bernie Durfee
### Space Ghost
### Chris Burrows!!

