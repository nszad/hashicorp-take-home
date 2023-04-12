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

`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch.

#### Git merge

To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".

#### Git pull

`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.