# Contribute Edgeble AI

This tutorial contains information about contribution steps and rules for Edgeble AI projects

## Steps to contribute

Here are the steps to contribute [meta-ecm](https://github.com/edgeble/meta-ecm)

### I. Open an issue 

Issue can be raised by reseptive contributor or maintainer
   
### II. Send Pull request

#### add ssh-keys 
User need to create new pair of ssh keys and upload them to the github setting
```
URI: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh
```
#### install gh
```shell
sudo apt install gh
```
For more information check github cli interface.
```
* URI: https://cli.github.com/manual/
```
#### authenticate gh
user need to authenticate the user, select the github account, it will ask you to login 
to github using the local web browser. Once completed it will ask enter generated 
passphrase from the below command
```shell
$ gh auth login
? What account do you want to log into?  [Use arrows to move, type to filter]
> GitHub.com
  GitHub Enterprise Server
$ gh auth status
github.com
  ✓ Logged in to github.com as moonlinux (/home/amoon/.config/gh/hosts.yml)
  ✓ Git operations for github.com configured to use https protocol.
  ✓ Token: *******************
```
#### push changes
Fork a copy of a repository that you manage. Forks let you make changes to
a project without affecting the original repository. You can fetch updates
from or submit changes to the original repository with pull requests.

Open the github repository in your browser and click the fork icon.
Clone and push the changes to repository

Do local changes in the repository and verify the changes, so that they can be reviewed.
```shell
$ git clone git@github.com:username/meta-ecm.git
$ git add 	# modified the files
$ git commit -s	# add a suitable commit message to describe the changes
```
Verify the build and feature work correctly as per the requirement.
Add the new remote github username to the existing local branch
```shell
$ git remote add username git@github.com:username/meta-ecm.git
```
Verify the github username is added to remote repository
```shell
$ git remote -v
username     git@github.com:username/meta-ecm.git (fetch)
username     git@github.com:username/meta-ecm.git (push)
origin  git@github.com:edgeble/meta-ecm.git (fetch)
origin  git@github.com:edgeble/meta-ecm.git (push)
```
Push the changes to github repository. depending on the branch you need to update below.
use -f if we want to push multiple times based on previous pr review.
```shell
$ git push -f username kirkstone:kirkstone
```
#### Send a pull request
This pull request will asked send the changes to original repository via github
```shell
$ gh pr create --title "Suitable title" --body "describes the commit changes"
```
