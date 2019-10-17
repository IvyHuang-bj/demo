# First Time git user
## #Set up of your git account
If you’ve never used git or github before, there are a bunch of things that you need to do. It’s very well explained on github, but repeated here for completeness.

Get a github account.
Download and install git.
Set up git with your user name and email.

Open a terminal/shell and type:
```
$ git config --global user.name "Your name here"

$ git config --global user.email "your_email@example.com"
(Don’t type the $; that just indicates that you’re doing this at the command line.)
```
I also do:
```
$ git config --global color.ui true

$ git config --global core.editor emacs
The first of these will enable colored output in the terminal; the second tells git that you want to use emacs.
```
Set up ssh on your computer. I like Roger Peng’s guide to setting up password-less logins. Also see github’s guide to generating SSH keys.

Look to see if you have files ~/.ssh/id_rsa and ~/.ssh/id_rsa.pub.
If not, create such public/private keys: Open a terminal/shell and type:
```
$ ssh-keygen -t rsa -C "your_email@example.com"
Copy your public key (the contents of the newly-created id_rsa.pub file) into your clipboard. On a Mac, in the terminal/shell, type:

$ cat ~/.ssh/id_rsa.pub >> pbcopy
Paste your ssh public key into your github account settings.
```
Go to your github Account Settings
Click “SSH Keys” on the left.
Click “Add SSH Key” on the right.
Add a label (like “My laptop”) and paste the public key into the big text box.
In a terminal/shell, type the following to test it:
```
$ ssh -T git@github.com
```
If it says something like the following, it worked:

Hi username! You've successfully authenticated, but Github does
not provide shell access.

## When conflicts happens

拉取远端代码。存在冲突，会报错。  
此时我们需要将本地代码暂存起来 stash；  
更新本地代码，将本地代码版本更新和远端的代码一致即可；  
将暂存的代码合并到更新后的代码后，有冲突解决冲突(需要手动进行解决冲突)；  
提交解决冲突后的代码。

Assume the latest commit was already done
start working on the next patch, and discovered I was missing something
 
#stash away the current mess I made
```
$ git stash save
```
#some changes in the working dir
 
#and now add them to the last commit:
```
$ git add -u
$ git commit --ammend
 ```
#back to work!

## Misc
Ivy$ git status  
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

#if you need the changes, git push to publish the local commits
#if you don't need them, run $git reset --hard origin
```
$git reset --hard origin
```
