---
title: Git for beginners
date: "2021-06-02T22:12:03.284Z"
description: "Basic Git commands every developer should know..."
---

Hi everyone,
This is my second blog. And in this I will be sharing my knowledge of Git, which is a distributed version control system. Git is an important part of our daily programming (especially if we're working with a team) and is widely used in the software industry.

Mastering git takes time and trust me, I've switched from SVN to git. So, I know the hurdles a beginner would face. I've seen many people who are not comfortable using git or doesn't use git properly.

There are so many commands we can use, but some commands are used more frequently(some daily). So in this post, I will share and explain the commands which every developer should know.

## 1. Git Clone ➿

Git clone is a command for downloading existing source code from a remote repository (like GitHub, for example). In other words, Git clone basically makes an identical copy of the latest version of a project in a repository and saves it to our computer.

There are a couple of ways to download the source code, but mostly I prefer the clone with https way:

```
git clone <https://name-of-the-repository-link>
```

For example, if we want to download a project from GitHub, all we need to do is click on the green button (clone or download), copy the URL in the box and paste it after the git clone command that I've shown right above.
![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/98xwuzwsqpdiu8sxnemi.png)

<figcaption>One of my repo's source code example.</figcaption>
This will make a copy of the project to your local workspace so you can start working with it.

## 2. Git Branch 🌿

Branches are highly important in the git universe. With the help of branches, several developers are able to work in parallel on the same project simultaneously. We can use the git branch for listing, creating and deleting branches.

#### Let's see first, how to create branch:

```
git branch <branch-name>
```

This command will create a new branch in local. To push this new branch to remote repo, we need to use the following command:

```
git push -u <remote> <branch-name>
```

#### To view the branches

```
git branch or git branch --list
```

#### To delete a branch

```
git branch -d <branch-name>
```

## 3. Git Checkout ✅

This command is also used very much. To work in a branch, we need to switch to it first. We use this command mostly for switching from one branch to another. We can use this branch also for checking out files and commits.

```
git checkout <branch-name>
```

Actually there are few steps which we need to follow for successfully switching between branches.

- The changes in our current branch must be committed or stashed.
- The branch we want to checkout must be in our local.

**There is also a shortcut command that allows us to create and switch to a branch at the same time:**

```
git checkout -b <branch-name>
```

This command creates a new branch in our local and switch to it after creating.

## 4. Git status 🗽

The status command we can run when we want to check the status of our current branch, like what all files have been modified, created or deleted or if there are files which are staged, unstaged or untracked or whether there is anything to commit, push or pull.

```
git status
```

## 5. Git add ➕

Whenever we create, modify or delete a file, these changes will be there in our local but won't reflect in the remote repository and it won't be included in next commit unless we modify the configurations.
We need to execute this command to include the changes of a file into our next commit.

```
git add <file>
```

The above command is used to add a single file.

```
git add .
```

The above command we can used to add all the altered files at once.

## 6. Git commit 💞

This command is also highly used in development. Suppose, you're working on some task and after some times you think that this changes should be saved. So, Git commit is like setting a checkpoint in the development process which you can go back to later if needed.
We also need to write a short message to explain what we have changed in the source code or what we have developed.

```
git commit -m "any commit message"
```

## 7. Git push ⬆

After committing the changes, the next process we need to do is send our changes to the remote server. Git push uploads our commits to the remote repository.

```
git push <remote> <branch-name>
```

However, if our branch is newly created, then we also need to upload the branch with the following command:

```
git push -u origin <branch-name>
```

## 8. Git pull ⬇

The **git pull** command is used to get the latest changes from the remote repo. This command is a combination of git fetch and git merge which means that, when we use **git pull**, it gets the updates from remote repository **(git fetch)** and immediately applies the latest changes in your local **(git merge)**.

```
git pull <remote>
```

Note:- This command can create conflict which we need to solve manually.

## 9. Git reset hard 🔙

When working on a team project, it is quite common for developers to create branches, add files and stage them for commits when they are ready.
However, in some cases, you might realize that the changes that you made were not that good.
You modified some files, added and deleted a lot of lines from your files, but you want to go back.
In short, you want to revert the changes that you just made and go back to the files that you had.
This technique is called “reset to HEAD” and it is quite a powerful tool for developers to use.

```
git reset --hard
```

## 10. Git rebase ⏸

The primary reason for rebasing a branch is to maintain a linear project history. For example, consider a situation where the master branch has progressed since you started working on a feature branch. You want to get the latest updates to the master branch in your feature branch, but you want to keep your branch's history clean so it appears as if you've been working off the latest master branch. This gives the later benefit of a clean merge of your feature branch back into the master branch.

To perform this command, we first need to checkout to the branch we want to rebase with our **main** branch.

```
git checkout <branch name we want to rebase>
git fetch origin
git rebase origin/<branch we want to rebase with>
```

That's it for this blog. There are still so many things to learn about git. Do checkout the [official doc](https://git-scm.com/doc).
