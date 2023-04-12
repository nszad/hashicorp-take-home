# Git Basics

## Push, Pull, Fetch, and Merge

At first glance, these Git commands may appear similar and therefore confusing. Let's start with brief definitions, then describe how to use these commands to get started with version control using Git.

- `git push` - Send changes from a local branch to a branch in a remote repository.

- `git fetch` - Retrieve changes from a remote branch and store in a tracking branch (see below section) in a local repository.

- `git merge` - Update a local branch with any new changes from a tracking branch, usually directly following `git fetch`.

- `git pull` - Retrieve changes from a remote branch and store in a tracking branch, then merge these changes into a local branch. (You can think of this command as a combination of the two above commands: `git fetch` then `git merge`.)


### Understanding the difference between Push, Pull, Fetch, and Merge

Now, let's describe each command step by step to better grasp the unique function of each. This section assumes that you have cloned a repository and have begun to make changes to a branch locally.

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. `git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
