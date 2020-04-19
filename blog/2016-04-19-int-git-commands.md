---
title: Intermediate git and the 2 commands that saved me.
summary: "I explain some intermediate git commands, git flow and 2 important commands that can save you in a bind."
date: 2016-04-19
tags: ['git', 'sourcecontrol']
---
I just moved from a project that was on SVN to git. Having not much git experience or command line experience, this was a little stressful. Especially since this project was using a form of git workflow called "git flow". More about `git flow` <a href="https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow" target="_blank">here</a>.
Oh and this all goes on top of the everyday stress I always get thinking “Do I know how to build this? “or “ What if I can’t build it in time?” <strong>The answer is mostly yes. It just takes time.</strong>
 
 
 
So here is what happened. I made my changes in my feature branch but forgot to keep them up to date with the develop branch. I did `git pull origin develop` to try and update my changes and followed a rebase tutorial and ended up with the dreaded “develop branch and “origin/develop” have diverged. I somehow was 12 commits behind and 5 ahead. I really messed up and had no idea how to fix it. The first thing I thought was okay, don’t panic this is only on your local machine, it’s not like you pushed any changes up (even if I did, it’s easy to roll back changes).
<figure>
<img src="\images\gitflow-overview.PNG" alt="Git Flow Demonstration">
<figcaption>An example of Git Flow. I was the bottom green one all sorts of behind from the purple develop branch.</figcaption>
</figure>
 
 
## Command  #1: `git reflog`
Many people know about the `git log` command but a really handy one is `git reflog`. I could see where I wanted to roll back my changes to, essentially as if they never existed. There were two options.

1. `git revert` Which undoes a committed snapshot by undoing the changes introduced by the commit and appending a new commit with the resulting content.
2. `git reset` Which was a permanent undo. As if my mistake never existed, which is exactly what I wanted! Since it was only on my local branch I decided to go with this method. More on `git reset` <a href="https://www.atlassian.com/git/tutorials/undoing-changes/git-reset" target="_blank">here.</a>

<figure>
 <img src="\images\git-reflog.PNG" alt="Git reflog command line">
 <figcaption>What happens when you run the git reflog command</figcaption>
 </figure>
 
## Command #2: `git reset –hard HEAD@{4}:`
 
 I had to put the `HEAD@{4}` in single quotes for it to work. I ran the command and crossed my fingers and hoped that it would work. A few seconds later I’m back where I started whoohoo!
 
Next up I did 

* `git pull origin develop`
    * This brought my feature branch up to date with what I missed in the develop branch.

* I then fixed any merge conflicts manually. You can find them with conflict markers that start with  `<<<<<<<` and end with `>>>>>>>`
 
 Alright, things are looking hunky dory in my feature branch. Now to actually merge the changes into develop.
 
 * `git checkout develop`
    * This switches me from the feature branch I was on, to the develop branch.
 
* `git merge feature/yourfeaturebranchname`
    * This merges my feature changes to the develop branch. Since I already updated my feature branch with everything that had happened in develop with `git pull origin develop`, It only brings in the feature branch changes instead of bringing develop up to speed and also merging the feature branch.
 
 * `git push origin develop`
    * At last! I pushed up all of the changes from my feature into the develop branch. No merge conflicts or anything. I had a victory beer to celebrate (not really, it was 10:30am in the morning on a Wednesday...
 
I highly suggest that you use the command line if you currently use a GUI application. Its faster and much easier to troubleshoot when you can paste the exact error code you get into google.   What I did was run the command and then see how it updates in the GUI application, I used sourcetree. If you want an intro to what git is there is an excellent write up at Luke Towney’s blog <a href="http://www.luketwomey.com/blog/git-and-github-a-brief-introduction" target="_blank">here.</a> Please comment with any questions or comments, I'm still learning and their may be an even better way to do this. Thanks!