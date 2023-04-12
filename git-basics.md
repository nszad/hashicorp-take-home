# Git Basics

## Push, Pull, Fetch, and Merge

At first glance, these Git commands may appear similar and therefore confusing. Let's start with brief definitions, then describe how to use these commands to get started with version control using Git.

- `git push` - Send changes from a local branch to a branch in a remote repository.

- `git fetch` - Retrieve changes from a remote branch and store in a tracking branch (see below section) in a local repository.

- `git merge` - Update a local branch with any new changes from a tracking branch, usually directly following `git fetch`.

- `git pull` - Retrieve changes from a remote branch and store in a tracking branch, then merge these changes into a local branch. (You can think of this command as a combination of the two above commands: `git fetch` then `git merge`.)

### Understanding the difference between Push, Pull, Fetch, and Merge

Now, let's describe each command step by step to better grasp the unique function of each. This section assumes that you have cloned a repository and have begun to make changes to a branch locally.

#### Git push

Let's say you want to update the remote repository with your changes. When you run `git push`, Git first checks whether you have a tracking branch (a local reference to an upstream branch in a remote repository) associated with the local branch you are working on. Once located, Git "pushes" any changes you've made to the remote branch. The local branch and the remote branch now share those changes. In other words, `git push` makes the remote branch resemble your local branch. 

NOTE: This command will print an error message if the remote branch has diverged from your local branch. This means that the remote branch has changes that are not in your local branch. This brings us to `git fetch`, `git merge`, and `git pull`.

#### Git fetch

To synchronize your local branch with the remote branch, first run `git fetch` to update the tracking branch associated with your local branch with the changes from the remote branch. NOTE: This does not update your local branch. 

#### Git merge

To update your local branch with the newly fetched changes, run e.g. `git merge origin/main` to "merge" the changes from the tracking branch for `main` into your local branch (which in this case should also be called "main").

#### Git pull

`git pull` is the same as first running `git fetch`, then immediately running `git merge`. This can be more efficient, but you may prefer to run each command individually in sequence to make sure you understand the changes you are going to make to a branch before you execute the merge.