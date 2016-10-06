# Git Branching

## Learning Objectives

- Explain what a branch is in git
- Create, merge and delete branches on local and remote repositories
- Describe how branching and merging allows for collaboration during development

## Review (5 min)

Quickly review the basics of git:

<details>
<summary>1. What is the purpose of git? How does it differ from github?</summary>
  ```
  Git is a version control system allowing us to easily track files, manage changes, and move between versions. Github is a web application that hosts remote repositories and allows developers to easily host and share code.
  ```
</details>

<details>
<summary>2. What command is used to start tracking a directory? What commands record the changes that occurred in the tracked directory?</summary>
  <br>
  ```
  1. $ git init - create empty Git repo
  2. $ git add <file-name> - stage file(s) for commit
  3. $ git commit -m "commit message" - commit staged files
  ```
</details>

<details>
<summary>3. What's the difference between a fork and a clone?</summary>

  ```
  A fork is a copy of a repository on github, a clone is a copy of a remote available locally.
  ```

</details>

<details>
<summary>4. What commands are used to share changes (commits) between local and remote repos?</summary>
  <br>
  ```
  1. $ git remote add <remote_name> <repo_url> - add remote repo
  2. $ git push origin master - sync remote repo with local
  3. $ git pull origin master - sync local repo with remote
  ```
</details>


## Framing - Why Branch? (5 min)

> Say you are working on a paper. You’ve gotten a first draft out, submitted for review. You then get a new batch of data, and you’re in the process of integrating it into the paper. Halfway in, however, the review committee calls you up and tells you that you need to change some of your section headings to conform to format specifications. What do you do? [1](http://www.sbf5.com/~cduan/technical/git/git-2.shtml)

### Think/Pair/Share -1/2/2: What can you do? (5 min)

Take a minute to brainstorm some options for what could be done here, then share with your neighbor, and we'll share what we feel is important.

## How Git Branching Works (10 min)

In Git, branches are a part of your everyday development process. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes. This makes sure that unstable code is never committed to the main code base, and it gives you the chance to clean up your feature’s history before merging it into the main branch [2](https://www.atlassian.com/git/tutorials/using-branches).

Branches are incredibly lightweight "movable pointers" that help us as developers make experimental changes! A branch in git is just a label or pointer to a particular commit in a repository, along with all of it's history (parent commits).

What makes a branch special in git, is that we're always *on* a specific branch, and when we commit, the current branch HEAD moves forward to the new commit. Another way to say that is the HEAD always stays at the tip of the branch.

**Terminology:** HEAD is simply a reference to the current or most recent commit!

![Git Branch Diagram](branching.png)

> The diagram above visualizes a repository with multiple lines of development, one is the master branch, and the others are feature branches. By developing in branches, it’s not only possible to work on branches in parallel, but it also keeps the main master branch free from questionable code.

---

## Why Branch (5 mins)

<details>
<summary>Q. Why is branching an important part of git?</summary>
<br>

> Branches are useful for many reasons, but some of the most common ones:

> 1. To allow experimentation. By switching to a new branch, we can experiment,
and if the experiment fails, we can delete it and easily switch back to master
(or another branch of our choice). If it succeeds, we can merge those changes
into master.
2. To allow work to proceed on multiple features (or by multiple people) without
interfering. When a feature is complete, it can be merged back into master.
3. To allow easy bug fixes on a stable version while features are being developed.
4. "Branch Early, Branch Often": Branches are lightweight, there is no additional overhead associated with branches, so it can be a great way to organize our workflow

</details>

---

## Merging (5 min)

Now imagine that we have completed our awesome feature on its own branch and we want to bring those changes back into `master`, we now need a way to consolidate these two versions of our code base. The easiest way to do this is by  **merging** the feature branch into the master branch.

Let's see what this process looks like visually:

![before-merge](merging.png)

***Locally***, all we need to do is check out the master branch and then run the git merge command to integrate our feature branch:

```
$ git merge <feature_branch_name>

```
Once merged, you can delete the branch:

```
$ git branch -d <feature_branch_name>

```
***Remotely***, we could easily merge our branch back into master through a PR and delete the branch on Github.

### You Do: Branching Exercise (15 min)

We are going to complete a [brief tutorial](http://learngitbranching.js.org/).  This is an introduction to branching.

- Do Levels 1-3.  Stop at 4: "Rebase Introduction".
- Take your time:
  - Read all the dialogs.  They are part of the tutorial.
  - Think about what you want to achieve
  - Think about the results you expect *before* you press enter.
- Whenever you see/type `git commit`, it may help to assume changes have been made and staged.  Why else would you "commit"?

> Please run this exercise using Chrome. It will not work propertly in Safari or Firefox.

## Common Commands for Managing Branches (5 min)

* `git branch <new_branch_name>` - create a new branch
* ⭐`git checkout <branch_name>` - switch to a specific branch (checks out tip commit and makes branch active)
* ⭐`git checkout -b <new_branch_name>` - create a new branch and check it out in one step
* `git branch` - list local branches
* `git branch -r` list remote branches
* `git branch -a` list both remote & local branches
* `git branch -d <branch_to_delete>` - delete a branch
  * will not let you delete if branch isn't merged into another branch (i.e. would cause data loss)
  * `git branch -D <branch_to_delete>` - over-rides and deletes a non-merged branch - **be careful!**
* ⭐`git merge <branch_name>` - merges `<branch_name>` into the current branch, creating a new merge commit in the process

[My favorite cheat Sheet](http://ndpsoftware.com/git-cheatsheet.html)

## Bonus: [Create a repo for deploying your work to GitHub pages](https://pages.github.com/)

## Appendix
 [An Excellent Video Detailing the Steps of DeployingGH-Pages](https://www.youtube.com/watch?v=6Dp5vos4zGI&index=2&list=PLae1he6d1WIlAWnbAMIWFzL0ibaKr4q-P)

## Closing (5 min)
 We've learned best practices for adding new code! Preserving the master branch and using branches to add in new features allows us to safely add in new code. This is also great when we fork a repository and want to make changes. With homework, after forking, cloning, check out and create a new branch in the following way `git checkout -b firstname_lastname_solution`
