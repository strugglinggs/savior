+++
title = "Git & GitHub/GitLab Basics"
date = 2019-02-26T13:03:26-05:00
weight = 3
enableEmoji = true
+++
{{% notice info %}} This page is a collection of resources and notes we've taken over the years.
{{% /notice%}}
![Forgetful](/savior/bash/forget.gif?classes=shadow)

## GITHUB

{{% notice warning %}} YOU HAVE TO CREATE A NEW REPO ON GITHUB FIRST!! can only push to repos that exist already and have an "origin" (I think this isnt true anymore / Always been possible on GitLab (see the official guide [here](https://docs.gitlab.com/ee/gitlab-basics/create-project.html)) 
{{% /notice%}} 

This can be done by using either SSH or HTTPS:

```
make repo on github
git remote add origin <link to online repo>
git push -u origin master (send this to specific branch (master) of specific repo (origin))
git checkout -b <name> creates a branch

git remote remove origin (so that origin doesn't point to multiple things)

git clone url.to.git.repo
to move stuff within git repo: git mv thing1 thing2
to remove stuff: git rm thing

git status (tells you what was done to a repo)

git pull (get the most recent copy from remote repo (url))
git commit path.to.files or -a for all files -m 'commit message' (commit = save)
git status (just to check)
git pull (to make sure nothing online has changed since you changed stuff)
git push (upload/distribute to remote repo)

git checkout -b nameofbranch (creates branch)

git log --oneline

git remote -v
``` 

git will automatically ignore empty directories so put something in them to be noticeable! ie touch dir/empty

pushes will fail if conflicts in remote repo
so always git pull; git push

put stuff in .gitignore that you don't want to share to repo and so that it never gets updated to repo

.md = markdown file (same as jupyter notebook or dropbox paper editing language)

## GitLab

### To create a repo from local machine

> When you create a new repo locally, instead of going to GitLab to manually create a new project and then push the repo, you can directly push it to GitLab to create the new project,  all without leaving your terminal. If you have access to that namespace, we will automatically create a new project under that GitLab namespace with its visibility set to Private by default (you can later change it in the project’s settings).

```bash
## Git push using SSH
git push --set-upstream git@gitlab.com:namespace/nonexistent-project.git master

## Git push using HTTPS
git push --set-upstream https://gitlab.com/namespace/nonexistent-project.git master
```