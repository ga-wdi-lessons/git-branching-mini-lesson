# Git Branches and Deploying to GitHub Pages
Terms: Branches, Deploying, Pushing

## Lesson Objectives
By the end of this lesson, students will be able to:
1. Identify use cases for both checking out a branch and merging that branch into master
2. Create and check out a new branch
3. Merge a branch into master

## Review of Terms (10:00-10:10)

### Branches, Commit History, and the HEAD

* By default, the default branch is the master branch
* Each time we create a new branch, we are are splitting off from the master branch's commit history, and moving the HEAD from the most recent commit on the master branch to the new branch
* HEAD is simply a reference or pointer to the current or most recent commit

> What makes a branch special in git, is that we're always on a specific branch, and when we commit, the current branch HEAD moves forward to the new commit. Another way to say that is the HEAD always stays at the tip of the branch.

## Framing and the Philosophy of Branches (10:10-10:20)

1. Why we want to keep the master branch clean or pure
2. Why we want to create branches for adding new features
3. How and why we add this code back into the core codebase

### Description of the Branching and Merging Process

> Close your laptops and spend 30 seconds memorizing these steps. I will randomly call on students to recall the steps after they are removed from the projector.

1. **Create and switch** to a new branch
2. Create and/or change file(s)
3. With `git`, **add** *and* **commit** these files to the repo
4. **Switch back** to `master` branch
5. **Merge** in changes

## Demo: Now watch me `git` (10:20 - 10:30)

### Steps for Creating a New Branch and Merging Changes

1. `git checkout -b new_branch`
 * `new_branch` could be anything: `pizza_branch`, `nav_bar_branch`, `branch_dressing`, or whatever you'd like to name it
 * This creates a new branch and checks it out
2. Add or change files
 * any change to the working tree
3. `git add` the relevant files, then `git commit -m "` [insert commit message here]`"`  
  * This step involves 2 parts!!! `git add` & `git commit`. Never forgit.
4. `git checkout master`
5. `git merge new_branch`

### Guide the Instructor

Let's say that I just merged my HEAD with a steel beam. Ouch. Now I forgot what I just taught you. Plz help.

1. I want to check out a new branch and switch to it.
  * How do I do this?
2. In my repo, I want to record the changes I've just made.
  * How do I do this?
3. I want to merge the changes I've just made with the master branch.
  * But how!?

## You Do (10:30-10:45)

0. Clone down this repo
1. What branches are in this repo? Maybe there are branches we don't even know about yet. How could we tell? Try the commands below in your CLI:
 - try `git branch`
 - then try `git branch -v`
 - also type `ls` to see what files are in your directory
2. See any other branches? if you see a branch try checking it out with `git checkout` <insert_branch_name_here>
 - note the difference between `git checkout` and `git checkout -b`
 -  `ls` again: what changed?
3. Make whatever changes you'd to any new files on the branch you've just checked out.
 - **Very Important**: add and commit these changes!
4. Switch back to `master` branch.
5. Merge the branches.

## Bonus 1: [Create a repo for deploying your work to GitHub pages](https://pages.github.com/)

## Bonus 2:
After finishing the 1st bonus, add a gh-pages branch to your Wendy Bite homework, or another repo. You can navigate to:
 your_username.github.io/name_of_the_repo_that_you_added_a_gh_pages_branch_to

## Appendix
 [An Excellent Video Detailing the Steps of DeployingGH-Pages](https://www.youtube.com/watch?v=6Dp5vos4zGI&index=2&list=PLae1he6d1WIlAWnbAMIWFzL0ibaKr4q-P)

## Closing (5 min)
 We've learned best practices for adding new code! Preserving the master branch and using branches to add in new features allows us to safely add in new code. This is also great when we fork a repository and want to make changes. With homework, after forking, cloning, check out and create a new branch in the following way `git checkout -b firstname_lastname_solution`
