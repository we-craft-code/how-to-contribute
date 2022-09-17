# Doing your first Pull Request (PR) 🚀

## 00. TABLE OF CONTENTS
- [Doing your first Pull Request (PR) 🚀](#doing-your-first-pull-request-pr-)
  - [00. TABLE OF CONTENTS](#00-table-of-contents)
  - [01. INTRODUCTION](#01-introduction)
  - [02. REQUIREMENTS](#02-requirements)
  - [03. FORK THE REPO](#03-fork-the-repo)
  - [04. CLONE THE FORKED REPO INTO YOUR MACHINE](#04-clone-the-forked-repo-into-your-machine)
  - [05. CREATING A BRANCH](#05-creating-a-branch)
  - [06. DOING A TINY CHANGE](#06-doing-a-tiny-change)
  - [07. GIT ADD, COMMIT AND PUSH](#07-git-add-commit-and-push)



## 01. INTRODUCTION

This guide has the purpose to help you getting your feet wet on how to contribute to OSS.

Usually when you work on your own repo, or inside a team, in a company, you can just `git clone` the repo and start working on it. But when we talk about OSS, it's usually a bit different, as you don't have permissions to do it directly.

Here we'll guide you from A to Z, so that you can open your first Pull Request (PR) successfully.

Let's go! 🚀

## 02. REQUIREMENTS

To follow this guide it would be good for you to have a minimal knowledge of git, and also to have a GitHub account.

If you don't have a GitHub account, here's an [explanation](https://learn.microsoft.com/en-us/visualstudio/version-control/git-create-github-account?view=vs-2022) on how to do it.

You'll also find in the link above, another links which teach you the basics of GIT. Feel free to stop and read it for a while, till you grok the basics.

## 03. FORK THE REPO

Because usually you don't have permissions to contribute directly to an open source project, you need to fork the repo. Forking is useful for this situation but not also. Imagine that you have different ideas for a OSS that people don't agree with. You can always fork the repo and drive it in your own direction. Of course, at your own risk.

In this particular situation, it works the same way. When you fork it, you're able to promote the changes you want. The only difference is that in the end, you don't want to drive away from the main or original repo, you want to add your contributions to it.

So, let's say we want to contribute to the we-craft-code repo. Link is [here](https://github.com/we-craft-code/we-craft-code).

First thing you need to do is click on the fork button.

![fork the repo](/images/01.png?raw=true "Fork the Repo")

Cool, so at this point, if you go to your repositories, you'll find the fork of we-craft-code.

If you're not finding it, just use the URL highlighted on the image below and change my github account handler 'evedes' by yours.

![your own repo fork](/images/02.png?raw=true "Your own Repo Fork")

Cool, repo forked successfuly! 🌈
It's time for you to grab a cup of tea (or coffee), as we're going to open a terminal and do some weird stuff there! 😅

## 04. CLONE THE FORKED REPO INTO YOUR MACHINE

Okay, so at this point, we already have a "copy" of we-craft-code repo living in our GitHub account.

The next challenge is to clone it.

To clone a repo into your machine it's necessary that you have git installed. Usually most OS come with a version of git.

To check if git is installed, open a terminal window and type:

```
git -v
```

In case it's installed you'll see something similar to this:

![git version](/images/03.png?raw=true "Git Version")

In case it's not installed, please search google in order to learn how to install it for your OS.

Go, I'll wait a bit! ☕

Okay, cool! Now everyone has git installed, and we're ready to clone our repo!

Position yourself in a folder where you are willing for our repo to be cloned.
I use to create a parent folder for each subject. In this case I've created a folder called WeCraftCode, but feel free to do as you think it's best for you.

To clone the repo, we first need to copy it's address. Please check the image below. Note: in case SSH won't work for you, switch to HTTP for now.

![repo address](/images/04.png?raw=true "Repo Address")

Okay, so just click on the icon shown in the image and let's get back to the terminal again.

![git clone](/images/05.png?raw=true "Git Clone")

Let's do:

```
git clone <repo address>
```

NOTE: my address is different from yours, so make sure you grab the address from your own forked repo!

After `git clone` finishes you can type `ls` to list what's in your folder, and if everything went well, you'll find a _we-craft-code_ folder.

Cool! So we're ready to do a few changes!

## 05. CREATING A BRANCH

So, at this point we're willing to do a tiny change somwewhere. Let's say we want to clean the README.md file and leave it blank.

But first, we need to create our own branch. It's not good to work directly on the main branch.

To do it we're going to create a branch by doing:

```
git checkout -b <branch name>
```

NOTE: Brackets here mean text to insert, they're not to be typed! 🔍

So, I'd to something like:

```
git checkout -b clean-readme
```

![create a new branch](/images/06.png?raw=true "Create a new Branch")

Cool! At this point my prompt tells me I'm in the clean-readme branch! Maybe your shell is not configured to do so. In that case you can do:

```
git branch --show-current
```

 to know in which branch are you working currently.

If you use VS Code, you'll see the current branch name on the bottom-left part.

This might seem a bit magic 🪄. How does VS Code knows we've switched branches? At least for me it was, in the beginning.

So, locally, git operates by storing all the changes in an hidden folder called .git, inside the repo folder. VS Code simply knows how to read it and update accordingly.

🦄 Cool! Let's change our code!

## 06. DOING A TINY CHANGE

Okay, we just want to clean README.md, so simply remove all text that exists there.

If you're using VS Code and you want to see changes you've made, just click on the "Source Control" icon on the left-side. IT will show you a list of the changed files. Next click README.md, and you'll see something similar to the image below 👇.

On the left side you see in red what you removed. On the right side, you see in green what you added.

![check the diff](/images/08.png?raw=true "Check the Diff")

## 07. GIT ADD, COMMIT AND PUSH

Okay folks, we've did a small change, and now we're ready to propose to add it to the original repo (the one that lives in the we-craft-code account).

But how to do it?

First we go back to our terminal and type 

```
git status
```

Git will tell us the status of our branch.

![git status](/images/09.png?raw=true "Git Status")

Git is telling us that there is one change, not staged, which is the README.md.
It seems all is good, but we need to add it so that Git knows what we want to commit.

So, we just type 

```
git add .
``` 

which means add everything that was changed here (`note that . means on this precise path or point`). 

🪄 **NOTE:** you also get changes from subfolders, so they'll be taken into account also.

After adding you can type 

```
git status
``` 

again and see git new status.

![git add + status](/images/10.png?raw=true "Git Add + Git Status")

Cool, so at this point we're ready to commit our changes!

Let's do it by typing:

```
git commit -m "chore: clean readme"
```

and 

```
git status
```

to check the current status.

🪄 NOTE: I've used chore as a common type to represent what I'm doing. This is a convention we often use in the industry provided by [commitlint](https://github.com/conventional-changelog/commitlint). Please check the link to know more. Among the different types one can find: build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test.

🪄 TIP: Get used to read what git tells you. At a first glance it might sound weird, but it usually tells you in plain english at what point you are and what are your options from there.

![git commit + status](/images/11.png?raw=true "Git Commit + Git Status")

Cool, so at this point, we're done with our changes. And they're commited.
So now, how do we make it go straight to where we want?

People are used to do `git push` and push the changes to their own repo. But in this case, we want our changes to go to the original repo we've forked.

This means we need to have that original repo as an upstream.

Go back to your terminal and type 

```
git remote -v
```

This will list all the remotes to which your local branch is connected. Origin contains the address of your forked repo.

This means we need to tell locally, to our git: "Hey, there's an upstream repo, from where I've forked this repo, and I want my changes to go there".

![git commit + status](/images/12.png?raw=true "Git Commit + Git Status")

So first we need the address of our upstream. We need to get back to the original repo, where we forked ours.

![get original repo address](/images/13.png?raw=true "Get the original Repo Address")

And then, we need to get back to our terimnal to add it.

We shall type: 

```
git remote add upstream git@github.com:we-craft-code/we-craft-code.git
```

And then, 

```
git remote -v
```

to check it was added correctly.

Please check the image below 👇

![add remote upstream](/images/14.png?raw=true "Add Remote Upstream")

Cool! So now we're ready to push our changes.
But we'll push it to our origin, as if remote upstream doesn't exist!

We'll type 

```
git push origin clean-readme
```

This means we want our changes to go to `origin`, to the branch called `clean-readme`.

![git push](/images/15.png?raw=true "Git Push")

At this point, if you go to we-craft-code GitHub repo, you'll see a warning telling you that there are recent pushes and asking you if you want to Pull Request them.

![Compare And PR](/images/16.png?raw=true "Compare And PR")

So, let's click on the Compare & Pull request button!

"Et voila!"

![Compare And PR](/images/17.png?raw=true "Compare And PR")

So, I just want you to pay attention to the highlighted box in the last image.

It's saying. "Hey! I'm requesting a change! This change, or changes, were made on a head repository, called evedes/we-craft-code, and we want to merge it to your base (original) repository, to the base (or branch) main.

Changes will be compared and added to main when someone approves your merge request, but for now you can only open the pull request by clicking Create pull request button.

It's good to add a description and maybe some images about what change you're proposing. No one in the Open Source community will take care to understand you if you don't try to explain it at first.

And here it is, your PR open and ready for someone to review.
Check how other PRs are made. Possibly people want you to fulfill the fields about: reviewers, assignees, labels, projects, milestone, etc.

Profit! We're done! Congratulations on opening your first Pull Request!
From this point on, possibly the reviewer will request a few changes, so you can do the changes in VSCode, and commit + push again! Check steps above on how to do it! 🎉🌈🦄

![Profit](/images/18.png?raw=true "Profit!")
