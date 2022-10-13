### What is the difference between push, pull, and fetch?

- `git push` - sent changes from a local branch to a remote repo
- `git fetch` - get changes from a remote repo into your tracking branch
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. `git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.

---

# What Is the Difference Between Push, Pull, and Fetch?

- `git push` - Send changes from a local branch to a remote repository
- `git fetch` - Get changes from a remote repo into your tracking branch
- `git pull` - Gets changes from a remote branch into your tracking branch and merges them into a local branch

## Git Push

`git push`

Git push shares your local code with a remote repository. Git push works by taking your current branch and checking if there is a tracking branch for a remote repository connected to it. If a tracking branch is found, your changes are taken from your branch and pushed to the remote branch.

Git push can fail if the remote branch has diverged from the your local branch. You can fix a failure by using `git pull` or `git fetch` to get remote changes, then using `git merge` to merge them.

## Git Fetch

`git fetch`

Git fetch works by checking for a tracking branch. If a tracking branch is found, it looks for changes in the remote branch and pulls them into the tracking branch. Git fetch doesn't change your local branch. To add the remote changes, use `git merge origin main`, where main is the name of your branch.

## Git Pull

`git pull`

Git pull works by doing a `git fetch` and `git merge` in one command.  If you use git pull, remote changes are merged directly into your local branch. If you prefer to review changes, use `git fetch` with `git merge`.