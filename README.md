## ___Git -&nbsp;Ultimate&nbsp;Reference&nbsp;Guide&nbsp;-___
---
By&nbsp;Martin&nbsp;Czerwinski [CMQ&nbsp;Nordic&nbsp;AB](www.cmq.se "www.cmq.se (Martin Czerwinski @ CMQ Nordic AB)")®&nbsp;March&nbsp;2020&nbsp;

---

This is a __short tutorial__,  __reference document__, a or a __look-up cheatsheet__ that gets you started really quickly with Git. It answer most common questions and provides information and solutions to common problems. Bookmark this page, share it and feel free to [reach out to us](www.cmq.se "Contact us!") with questions, comments or requests for assignments!

_Audience: beginner to advanced_<br>
_Prerequisites: none_

---

#### __TABLE OF CONTENT__

- __GIT and Command Line__
  - [__What is GIT and why from command line?__](#what-is-git) 
  - [__Git expressions__](#common-git-expressions):<br> 
  - [__Repository__](#repository)
  -  ◦ [Type of files in Git](#files-in-git) ◦ [Cloning](#cloning-in-git) ◦ [Check-out & change branches](#check-out-change-branches) ◦ [Working directory](#working-directory) ◦ [Clean working directory](#clean-working-directory) ◦ [Stage](#stage) ◦ [Commit](#commit) ◦ [Commit Hash & Tag](#commit-hash-tag) ◦ [Stashing files](#stashing-files) ◦ [Working tree](#working-tree) ◦ [Stage or Index](#stage-or-index) ◦ [Repo history](#repo-history) ◦ [Remote](#remote) ◦ [Git Branch](#git-branch) ◦ [Tracking relationship](#tracking-relationship) ◦ [Local&nbsp;branch&nbsp;& Tracking&nbsp;branch&nbsp;& Remote&#8209;tracking&nbsp;branch](#local-branch) ◦ [Remote & Upstream branch](#remote-branch) ◦ [HEAD](#head) ◦ [Detached HEAD](#detached-head) ◦ [Merge & Rebase](#merge-rebase) ◦ [Fetch & Pull](#fetch-pull) ◦ [Push](#push) ◦ [Merge Conflicts](#merge-conflict) ◦ [Unrelated Histories errors](#unrelated-histories-error)
  - [__Useful Git commands__](#useful-git-commands-m):<br> 
	  [HELP COMMANDS](#help-commands) ◦ [INFO & STATUS COMMANDS](#info-status-commands) ◦ [CONFIGURATION COMMANDS](#configuration-commands) ◦ [CREATE NEW REPOSITORY](#create-new-repo-commands) ◦ [CREATE NEW BRANCH](#create-new-branch-commands) ◦ [CHECK OUT BRANCH](#check-out-branch-commands) ◦ [SYNCHRONIZE WITH REMOTE](#synchronize-with-remote-command) ◦ [STAGE & COMMIT](#stage-commit-commands) ◦ [MERGE & REBASE](#merge-rebase-commands) ◦ [DIFF & LOGS](#diff-logs-commands) ◦ [UNDO & CORRECT](#undo-correct-commands) ◦ [CONFLICTS](#conflicts-commands)
  - [__Useful Cmd commands__](#useful-cmd-commands-m)
  - [__.gitignore file__](#git-ignore-file-m)

<br>

---

<p align=right><a id="what-is-vscode" align=right href="#table-of-content">↩ Back To Top</a></p>

## __Git and Command Line__

__What is Git and why use it from command line?__

[__Git__](https://git-scm.com/) is the most popular version control system (VCS) for tracking changes in source code during software development. It is a distributed system - meaning that our local repository have exactly the same features as the central repository. You can work with your own repo on your local machine even without internet access. When you have a connection again, you can push your changes to any other git repository (i.e. central repository). VSCode has integrated graphical interface for GIT but we still recommend to get familiar with and memorize most commonly used expressions and commands. At workplaces around the world you will be often forced to run git commands directly from a command line window. 

_Good Git tutorials can be found [here](https://www.youtube.com/watch?v=uR6G2v_WsRA "30 min, Core concepts"), [here](https://www.youtube.com/watch?v=FyAAIHHClqI&t=1233s "30 min, Branch & merges") and [here](https://www.youtube.com/watch?v=Gg4bLk8cGNo&t=7s "30 min , Remotes").<br> Good article explaining merging and rebasing can be found [here](https://www.atlassian.com/git/tutorials/merging-vs-rebasing "Merging And Rebasing explained")._

<p align=right><a id="what-is-git" align=right href="#table-of-content">↩ Back To Top</a></p>

### [__Common Git expressions__]()
    
  [Repository](#repository) ◦ [Cloning](#cloning-in-git) ◦ [Working directory](#working-directory) ◦ [Check-out a branch](#check-out-change-branches) ◦ [Filetypes](#files-in-git) ◦ [Stage](#stage) ◦ [Commit](#commit) ◦ [Commit Hash & Tag](#commit-hash-tag) ◦ [Stashing files](#stashing-files) ◦ [Working tree](#working-tree) ◦ [Stage or Index](#stage-or-index) ◦ [Repo history](#repo-history) ◦ [Remote](#remote) ◦ [Git Branch](#git-branch) ◦ [Tracking relationship](#tracking-relationship) ◦ [Local&nbsp;branch&nbsp;& Tracking&nbsp;branch&nbsp;& Remote&#8209;tracking&nbsp;branch](#local-branch) ◦ [Remote & Upstream branch](#remote-branch) ◦ [HEAD](#head) ◦ [Detached HEAD](#detached-head) ◦ [Merge & Rebase](#merge-rebase) ◦ [Fetch & Pull](#fetch-pull) ◦ [Push](#push) ◦ [Merge Conflicts](#merge-conflict) ◦ [Unrelated Histories errors](#unrelated-histories-error)


|<a id="repository">Repository</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|A Git repository, or just simply _a repo_, is a folder location in which Git tracks changes to files and folders. Git stores historical versions of all tracked files there. It's folder named ".git" in its root directory. By deleting this folder all historical versions are lost and Git stops tracking changes to content in that directory. We have access to a remote repo and can clone it from a hosting services like [GitHub](https://github.com/) or [Bitbucket](https://bitbucket.org/) to our local machine. You can change the name of a local repo simply by renaming the folder on your hard drive. But when changing name of a remote repo on i.e. GitHub may affect persons who already use the old name as part of the URL in their configurations.<br><br>|

|<a id="working-directory">Working directory</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|In Git world expression "working directory" refers to a folder location where our local repo exists and where a single version of the project is checked out - the files are stored in it. It is an "umbrella" term for all files and folders that git traces and that we can currently view and edit.<br><br>Clean Working Directory<br>Expression "clean working directory" is widely used in Git documentation. A working directory is clean when there are not any uncommitted changes in the working tree nor index. If you are in progress of working and do not feel ready to [stage](#stage) nor [commit](#commit) your modifications before checking out something else, then you can also [_stash_](#stash-files) the changes to temporally clean up your working directory.<br><br>|

|<a id="commit">Commit</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|When we commit a changes in Git we permanently save modified file(s) to local repo´s history and label all the committed files with an unique hash-id, description and name of the committer. The word "commit" also often refers to a unique labeled "snapshot" of files and directories at a certain moment. A commit operation can be manually triggered with a `git commit` command but can also be a background job as part of a `git merge` operation.<br><br>|

|<a id="head">HEAD</a><a href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|HEAD in Git is a movable pointer always pointing to a commit that we currently have checked out in our working directory. In normal cases it always point to a branch and therefore when branch moves to point to the latest commit then automatically our HEAD does as well. Branch and HEAD pointers are in such a case "attached". When we check out a branch then Git always automatically let HEAD pointer to point to branch and as it always checks out latest commit. But note that there are cases when we need to check out a specific commit ot tag and not a branch! Then the HEAD points directly to this specific commit/tag and not the branch. This scenario is called [detached HEAD](#detached-head).<br><br>|

|<a id="check-out-change-branches">Check-out a branch</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|Checking out a branch (also called _changing branch_) is loading of a new specific group of files and folders into our working directory. Git overwrites all current files and folders in our working directory with the ones that we are checking out. By doing this we can view and edit those new versions of the checked-out files. We can check out a _branch_, a specific a _commit hash_ or a _tag_. See check-out commands [here](#check-out-branch-commands). Additionally our local HEAD pointer is moved to point toward the [_commit_](#commit) that is checked out. It is recommended to have a [_clean_](clean-working-director) working directory when checking out.<br><br> What happens to [_uncommitted_](#files-in-git) changes?<br> If we try to check out our current working directory having uncommitted changes in index or working directory, then sometimes the checkout will fail. Git never overwrites your modification if there is risk to lose the modification. Therefore if "parent" of any modified file differs in any way from same file in the commit we aim to check out from, then Git abort the check out process. To perform a check out in such a case you must either [_commit_](#commit), restore or [_stash_](#stash-files) your changes.<br><br>Note that if we check out a specific commit instead of a branch then we check out the working directory in [_detached HEAD_](#detached-head) state.<br><br>|

|<a id="cloning-in-git">Clone a branch</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|Cloning is simply making a copy of a whole repo and saving it to another location. It is done with a `git clone` command that automatically checks out that branch that is in remote marked with HEAD. Usually it is a _"master"_ branch and therefore when we clone a remote repo then locally a branch called "`master`" is automatically created and checked out in our working directory.<br><br>|

|<a id="files-in-git">Filetypes</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|There exist 4 types of files in Git:<br><br> ⋅ _Untracked:_ Newly added files.<br> ⋅ _Modified:_ Existing files changed and saved in working tree.<br> ⋅ _Staged:_ Added to our staging area.<br> ⋅ _Committed:_ Saved in the repo history.<br><br>_Untracked files_ are basically files that Git do not have any previous version of in its history. Files that are newly added to your project get the status _untracked_. Those are added to the working tree but in order to become tracked and get a first initial version they must be either [_staged_](#stage) or [_committed_](#commit). Many Git commands like `git reset` or `git revert `do not affect untracked files and there is a special `git clear` command to remove those files from the project.<br><br>|

|<a id="working-tree">Working tree</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|Term working tree refers to an "area" where changes to files in your working directory are stored. At same moment a change in your working directory is saved - the is added to working tree. This is the "first level" of tracking of our change, but notice that changes saved here can not be restored if accidentally deleted.<br><br>|

|<a id="stage-or-index">Stage or Index</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Staging area is in Git documentation shortly called "index" and refers to an area within Git where modifications are saved before a _commit_. From here a change can for example be restored if it for example have been accidentally changed in your working directory. Here we do inspect the files and from here we usually commit if we are satisfied with the changes.<br><br>Note that there is a possibility in Git to commit directly from working three and omit the staging area, with help of `-a` flag.<br><br>|

![Git commands](./app/assets/images/GIT_structure.JPG)

|<a id="stage">Stage</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|Staging is saving changes to the staging area in your local repo. The staging are is also often called _index_. From there we can can take decision if file shall be _restored_ or finally _committed_ to repo history.<br><br>|

|<a id="commit-hash-tag">Commit Hash & Tag</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|A commit _hash_ is an unique unchangeable 40 characters long SHA-1 hash that is created as unique identification for each commit of files to a repo. Example of a commit hash is `4c511f16ef2644854d04cabebfcecc82be0eb04f`. Normally only 7 first characters are enough to identify a commit within a normal project and therefore short "7-chars-version" can be used to refer to a commit.<br><br>A commit _tag_ is a label/stamp that can be manually added to a commit to mark a particular commit with a human readable label. Example: rel-v.1.8.5.<br><br>|

|<a id="stashing-files">Stashing files</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Stashing takes the "dirty" state of your working directory — your modified files in working tree and index - and save those on a "stash-stack" of unfinished changes that you can reapply at any time later. Note! By default Git do not stash [untracked](#files-in-git) files therefore to handle those use "-u" flag.<br><br> The command `git stash -u` will add all changes as an object on top of the stash stack.<br><br> Later to get back to stashed changes simply run `git stash pop` command and your latest stashed changes will be reverted to current working directory and the stashed object removed from stash-stack. To list all stashed objects in stack run `git stash list` command.<br><br>|

|<a id="repo-history">Repo history</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|When we commit a change then it is automatically added to our repo history, also called shortly "history". All commits with their hashes, descriptions and tags are stored in our local repo history.<br><br>|

|<a id="remote">Remote</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Expression "remote" is widely used in Git documentation and it usually refers to a remote repository or a remote branch, depending on the context.<br><br> A `remote` command in Git provides functionality for connecting of a local repo to with a remote repo. Such a  __remote connection__ can be created in any local repo and given a name (alias) and a remote URL. In Git we refer to a connection to remote by its name.<br><br> Git automatically creates a remote connection when cloning a remote repo to a local destination and names it "origin". A widely used expression "fetching data from remote" means we download data from remote repo, usually for a single branch, from url that our remote connection has saved.<br><br>|

|<a id="git-branch">Git Branch</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Consider a chain of objects connected to each other. Each object (blob) contains a version of code labeled with an unique id. There is a start and end of this chain. The latest object is on the end, the tip of the chain. Such a chain with connected commits is a "git branch". A branch  start from a certain commit from another branch. Then it branches out from it and defines it starting point. Using expression branch we often mean a movable pointer that points to latest object in this chain of commits. Every time you commit something to a branch then this branch pointer moves automatically forward to point this latest commit.<br><br> Usually when we work on a new feature we "branch out" - spawn a new branch - from the latest commit of "parent" branch, and give that new branch a special name i.e. "feat-x-branch". This because we want to encapsulate our changes while working and committing without affecting the parent branch. Finally when we are satisfied with work on our isolated feature branch we can update the "parent" branch. This can be done by pushing to or [pulling](#fetch-&-pull) from parent with help of merge/rebase commands - see [Merge & Rebase](#merge-&-rebase)<br><br> In more complex projects we can have hundreds of commits on dozen of branches i.e. dev-, release- or feature- branches of all kinds. Note that the first by git automatically created branch when new repo is created is by default called `master`.<br><br>|

|<a id="tracking-relationship">Tracking relationship</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Understanding and making use of tracking relationships in Git makes version control a whole lot easier. Very often we work on a local copy of a project that is hosted in a central remote repo. This means that our local branch have a "sibling" branch, a copy of itself, with the same name in the remote repo. This remote branch can be updated by others independently as we commit to our corresponding local branch.<br><br> Very often we want to know how our local branch differ from its "_remote sibling_". We want to know if any commits were made to same branch in remote by other developers while we were working on a local copy. Here is where "tracking" and "upstream" branches described in detail below help us. When a local branch is turned into a [_tracking branch_](#local-branch) then it automatically tracks its [_upstream branch_](#remote-branch) (its "sibling" in remote) through a [_remote-tracking branch_](#local-branch). <br><br>__Local branch__ (local, _i.e. master_) __-->__ __Remote-tracking branch__ (local, _i.e. origin/master_) __-->__ __Upstream branch__ (remote, _i.e. master_)<br><br>|

|<a id="remote-and-upstream-branches-in-git">Local&nbsp;branch&nbsp;& Tracking&nbsp;branch&nbsp;& Remote&#8209;tracking&nbsp;branch</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|There are several types of _local branches_ and it's important to get familiar with the terminology used in order to follow Git documentations.<br><br>__Local branch__ is simply a branch that exists on your local machine, in your local repo and can be named as "master", "dev" or "feature-x-branch".<br><br>__Tracking branch__ is a type of local branch that is connected to and "tracks" its counterpart "_sibling_" in remote. It tracks the other branches updates and compares difference in number of commits between them. Usually connecting a local branch to track its remote "sibling" is called "[_setting upstream_](#upstream) _for a local branch_" and is what makes a simple local branch to become a tracking branch.<br><br> __Remote-tracking branch__ is a special local branch that is in some cases created automatically in the background by Git. Its name always consists of two parts - `<remote-alias>/<remote-connection-name>` for example "origin/master" och "origin-repo-x/feat-x-branch". Its only purpose is to mirror corresponding remote branch that has same name in remote. This local branch is always automatically created or updated in the background whenever any network communication toward corresponding remote branch is made. For example when a push/pull/fetch is performed to a remote branch then corresponding remote-tracking branch is created locally in the background. All existing _remote-tracking branches_ in our local repo can be listed with a `git branch -r` command.<br><br>To list all local "non-tracking branches", "tracking branches" and "remote-tracking branches" run `git branch -a -vv` command. The result can look something like this:<br><br> _* master&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;33f45fe&nbsp;&nbsp;[origin/master: ahead 1, behind 2]&nbsp;&nbsp;Added print.<br>&nbsp;&nbsp;feature-x-branch&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;09c51c6&nbsp;&nbsp;Merge from master branch.<br>&nbsp;&nbsp;remotes/origin/master&nbsp;&nbsp;&nbsp;a9a5bfc&nbsp;&nbsp;Added special character._<br><br>What does above mean?<br>▸ Branch _* master_ - as marked with "*" is our currently checked out branch. It tracks an upstream branch in remote named "master" through its connection to a local "remote-tracking branch" named "origin/master". Due to this we know it is also a tracking branch and simple pull/push without parameters will work here (read more [here](#upstream)). When this "remote-tracking branch" "origin/master" was synched last time then "master" in remote had 1 new commit not included in our local "master" branch, and our local "master" had 2 new commits not included in "remote master".<br>▸ Branch _feature-x-branch_ - is a normal non-tracking local branch with its last commit labeled 09c51c6.<br>▸ Branch _origin/master_ - is a remote-tracking branch that refers and mirrors corresponding upstream branch named "master" in remote.<br><br> |

|<a id="remote-branch">Remote&nbsp;&&nbsp;Upstream&nbsp;branch</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|__Remote branch__ is a branch that exists in a remote repository, usually on an online git-hosting service like GitHub. A remote branch that is connected/referenced from a local system is in this context also called being an "upstream branch". You can often see expression that a "local branch tracks its upstream". It means the local version is somehow connected to its "sibling in remote" and tries to know everything that happens to him. Procedure of connecting a local branch with its corresponding branch in remote is in Git documentation often called as "setting [upstream](#upstream) for a local branch".<br><br> __How to set upstream for a local branch?__ It can be done in two ways:<br><br>▸ Manually: Only if there already exists a "remote-tracking branch" on the local system then any local branches upstream can be set with command `git branch --set-upstream-to [name of "remote-tracking branch"]`.<br><br>▸ Automatic: Whenever you run any first push/pull/fetch command to corresponding remote branch add `-u` flag like `git fetch -u [remote-connection][local-branch]`. This will not only create a remote-tracking branch (named <remote-connection>/<local-branch>) but also connect it (set as upstream) for our local branch.<br><br>Note! When cloning a repo from a remote then Git automatically checks out a default local branch and automatically make it a "tracking branch" by setting its upstream in the background. Therefore in most common cases after cloning from a remote we end up with two local branches, "master" and "origin/master", and we can run git `Git pull & push` commands without any additional parameter straight out of the box for this checkout branch.<br><br>|

|<a id="detached-head">Detached HEAD</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Detached HEAD means that our [HEAD](#head) pointer do not point to a branch pointer but points to a specific commit hash or tag. This happens when we check out a specific commit, check out a [_remote-tracking branch_](#local-branch) or sometimes this also might happen when a rebase fails and leave us "hanging" in an unfinished state. Simple `git status` command will inform you that you are in this special state. In this state you can look around at code, edit files and even commit your changes as usual but be aware that you will not be able to push/pull from/to this "detached workspace" and your precious work with commits or staged changes will eventually be lost when you check out something else. This because internally in detached state Git creates a branch without any starting point (unreferenced branch) and after a week or so Git garbage collector will deletes unreferenced branches from the memory!<br><br> Usual procedure to save you staged changes and commits that you have done in a "detached mode" is simply to create new branch when in a detached working directory and commit you changes to this new branch. Following will do the trick:<br><br> `git checkout -b temp-branch-from-detached`<br> `git commit -am "Committing changes done in detached HEAD state."` <br><br>|


|<a id="merge-rebase">Merge & Rebase</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>|
|:---|
|There are two ways in Git to integrate changes from one branch into another one - merge or rebase. Both have their advantages and disadvantages.<br><br> __MERGE:__ Can be performed in two ways and it is important to understand how both work, specially if you want to merge your feature into a branch that many other persons work on.<br> __1. Fast-forward merge:__ Is possible only if the point where the both branches diverge from has not forked, meaning only the branch that we merge from received any new commits. When we run `git merge` command this type of merge is performed if possible by default. In a case when Git has possibility to do a fast-forward merge then the branch pointer of the branch we merge into (here called parent) is simply moved to point to same commit/branch that we merge from. This results in that ALL commits in our "feature-branch" are now "added" to the tip of the parent me merged to. It this desirable? Sometimes yes but consider a situation when feature you worked on contains of many many minor commits on your "feature-branch". In case of a fast-forward merge ALL the commits with with their descriptions and hashes will be visible as part of parent branch. This can often be a disadvantage as it is much clearer from the point of reviewer to be able to see only one single commit telling when "feature-x" was delivered instead of "15 commits" with comments you made originally working on your privater feature branch. Also in case of reverting the feature it is impossible to see from Git history which of the commit objects in parent really implement the feature. You would have to manually read all the log messages making reverting such a feature added in this way a true headache.<br> __2. Non fast-forward merge:__ Sometimes done by git automatically when commits do not fullfil criteria for fast-forward merge - but it can be forced by adding `--no-ff` flag to the git merge command. Then git will never do fast-forward merge and add our committed feature in ONE new commit on the parent. Note, merge do not rewrite any history of already existing commits on the destination branch witch is regarded as more safe than rebase.<br><br>__REBASE:__ This is changing the base of your "feature-branch" to tip of the branch making appear as if you'd created your "feature" branch from latest commit. As a result we get a linear succession of commits. It differs from merge by rewriting the commit history of already existing commits on the destination (parent) branch. Usage: If you want to get the latest updates from parent (= the branch you branched from) into your "feature-branch", but you want to keep your branch's history clean so it appears as if you've been working off the latest commit. This gives you also later the benefit of a clean merge of your feature branch back into parent! Usually you rebase toward your own "feature" branch that you are in full control of and can afford messing up and take time to solve if something goes wrong, and you do a merge back to master or dev-branch or whatever you branched from.<br><br> |

|<a id="fetch-pull">Fetch & Pull</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Synchronizing data between your local machine and remote is an essential step in our daily work as the data we locally look at is just a "snapshot" and up-to-date only as the last time we explicitly downloaded fresh data from the remote with a fetch or pull command.<br><br>▸ __Fetch__ downloads commits on all branches in a remote repository and stores all in local repo's  corresponding [_remote-tracking branches_](#local-branch) but DO NOT integrate any of this new data into files in our currently working directory. To integrate the any commits into currently checked out branch we have to run a `git merge` command toward the corresponding the [_remote-tracking branch_](#local-branch). <br><br>▸ __Pull__ on the other hand not only downloads all remote branches but also updates our files current working directory (=checked out branch) with the downloaded changes by making a merge. Since "pull" in background always by default tries perform to merge changes from remote into our local ones, a so-called [_merge conflict_](#merge-conflict) can occur. `Git pull` can also be flagged to do a [rebase](#merge-&-rebase) instead of a background merge with help of `--rebase` flag. There are many opinions on whether or not preferably use pull with rebase option but as long as you pull to your private feature branch that only you work on, then this is our recommendation. Like for many other actions it's highly recommended to start a pull only with a [_clean working directory_](#clean-working-director).<br><br> |

|<a id="push">Push</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|With `git push` we upload commits from our local branch to corresponding remote branch. When we execute the command while having checked out a local branch that is a [_tracking branch_](#local-branch), then a simple `git push` command will instruct Git to take changes only from the branch we currently are on and update corresponding "upstream branch" in remote. On the other hand if the current local branches not a "tracking branch" then we must give `git push` command additional instructions in order for Git to know the destination. Then the same command looks like `git push <remote-connection>`. Git will then connect to remote repo´s url specified in "remote connection" i.e. "origin", take changes in the branch we are on and copy those commits to remote branch that is named same. <br><br> |

|<a id="merge-conflict">Merge Conflicts</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|A merge conflicts arise when two commits that we are merging together have changed in the same parts of code and Git do not know how to solve this. For example when one developer deleted a file in master while another developer on his feature-branch was modifying same file. In such cases Git will mark the file as being conflicted and halt the merging process with terminal output "Automatic merge failed - fix conflicts and then commit the result" and it is developers' responsibility to resolve the conflict. Code from both files are then checked out in the working directory and separated with string "`=============`". The files must be manually edit and saved and manually committed in order for the merge to finalize.<br><br> |

|<a id="unrelated-histories-error">Unrelated Histories errors</a><a align=left href="#common-git-expressions">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>| 
|:---|
|Sometimes our local .git directory with its history get deleted or corrupted. This leads Git to be unaware of the local history and will throw this error when you try to clone/fetch/push from remote. This will also happen when a new remote repo is created (i.e. on GitHub) with README file as initial commit. Then this repo will get its own history due to the first commit. If you simultaneously create new local repo and commit a single change then your local repo also gets a history created. In this case trying to clone one to another will fail with this error as both already got their own histories on their own. This can be solved using `--allow-unrelated-histories` flag on the command that fails. |

<br>
<p align=right><a id="useful-git-commands-m" align=right href="#table-of-content">↩ Back To Top</a></p>

<br>

## [__Useful Git commands__](#) 

---

Some common and very useful git commands tp know. Note that in VSCode you can open 'Command palette' (`CTRL-SHIFT-P`) where you can run git commands by choosing from a list instead of typing them into the terminal window.

 - [Help commands](#help-commands) - _git & command help_
 - [Info & Status](#info-status-commands) - _get status & system info_
 - [Initial configuration](#configuration-commands) - _configure your git_
 - [Copy external repo](#clone-external-repo) - _copy remote repo as our own_
 - [Create new repo](#create-new-repo-commands) - _create a local repo_
 - [Create new branch](#create-new-branch-commands) - _create a new branch_
 - [Check-out](#check-out-branch-commands) - _checking out a branch or file_
 - [Remote connections](#remote-connections-in-git) - _connect to remote_
 - [STAGE & COMMIT](#stage-commit-commands) ◦ <br>
 - [MERGE & REBASE](#merge-rebase-commands) ◦ <br>
 - [DIFF & LOGS](#diff-logs-commands) ◦ <br>
 - [UNDO & CORRECT](#undo-correct-commands) ◦ <br>
 - [CONFLICTS](#conflicts-commands) ◦ <br>
 

![Git commands](./app/assets/images/git-commands.png)


|Help&nbsp;commands&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|<a id="help-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
|`git`| Lists all git commands with short descriptions. |
|`git`&nbsp;`<command> -h`| Short help about a specific command. |
|`git`&nbsp;`<command> --help`| Extensive help about a specific command (online in new window).|

<br>

|Initial&nbsp;configuration|<a id="configuration-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
|`git`&nbsp;`config --global user.name <your-name>`|Set desired name used to be in commits (shown to others)|
|`git`&nbsp;`config --global user.email <your-email>`|Set desired email used in commits (shown to others)|

<br>

|Info&nbsp;&&nbsp;Status&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|<a id="info-status-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
|`git`&nbsp;`--version`| Prints current git version.|
|`git`&nbsp;`status`| Prints current repo status:<br>Current branch, changes in w-tree/index, errors, conflicts and info.|
|`git`&nbsp;`config --list`| Prints current configuration info.|
|`git`&nbsp;`log --graph --oneline -5`| Prints 5 last commits from HEAD down, each commit on each line. Use `--all` instead of `-5` to list all. |
|`git`&nbsp;`branch -a -vv`| Prints all local and remote-tracking branches with corresponding upstream status.|
|`git`&nbsp;`remote -v`| Prints all set remote connections: name and url |



<br>

|Create&nbsp;a&nbsp;local&nbsp;repo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a id="clone-external-repo" href="#useful-git-commands-m" title="Back to top">↩</a>||
|:--|---|
|Copy from existing: | _Copy from existing to your local machine_
|`git clone`<br>`<remote-url>`| Creates new folder in local location named same as remote repo and codownload whole remote repo into this newly created directory. A remote connection is created in background pointing out the cloned URL and can be checked with `git remote -v`.|
|Link to existing: | _Link existing local repo to external empty shell_ |
|`git init`| If the local project is brant new it must first be initiated so that .`git` folder is added to its root. |
|`git remote -v`| check if there exists a connection already (i.e. origin) that we can reuse, then use `git remote set-url` to change the url to point to desired url. If no connection exist then new one must be added. |
|`git remote add`<br>`<connection-name> <our-remote-url>` | Adds new remote and sets it url |
|`git remote set-url`<br>`<connection-name> <our-remote-url>`| Change URL cor existing connection to URL pointing to desired (empty) remote repo. |
|`git push -u`<br>`<remote-connection-name> <branch-to-push>`| Push (upload) all local files to remote repo. The `-u` flag shall be used first time to force git not only to create a remote-tracking branch but also connect an upstream. Read more [here](#remote-and-upstream-branches-in-git)  |
|`git branch -a -vv`| Check that branches exist and that origin in synch with upstream as expected. |

<br>

|Create&nbsp;a&nbsp;new&nbsp;repo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|<a id="create-new-repo-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
||There are _two ways_ of creating a repo on your local machine. Either create a new repo from scratch or create one by coping an already existing one.|
|`git init`| Creates a new empty local repo from scratch in the current folder. To create the repo with different name (in a new sub-folder) use `git`&nbsp;`init`&nbsp;`<folder`&#8209;`name>`|
||_When cloning existing repo_<br>Common is that Git automatically, in background, creates a remote connection named "_origin_" pointing to remote url we clone from. Also a local "_remote-tracking branch_" (usually called "origin/master") is created in background and is used on the local _master_ branch as its "upstream". If not differently instructed by default clone command will check-out that branch which in remote is marked with HEAD - usually named _master_. If different branch is desired to be checked out after a clone then add `-b <branch-name-to-check-out>`|
|`git`&nbsp;`clone`&nbsp;`<remote-url>`|Clones remote repo into a newly created directory named same as remote repo. Copies the whole repo, with all its branches from the given url. Creates remote-tracking branches for each branch. If different directory is desired add `<new-local-repo-name>` at the end.|
|`git clone`&nbsp;&#8209;&#8209;`single-branch`&nbsp;&#8209;`b`&nbsp;<br>`<remote-branch-name> <remote-url> <new-local-repo-name>` |Clones from url only one branch "remote-branch-name" from a remote repo into a newly created directory named "new-local-repo-name". Creates remote-tracking branches for the cloned branch. Checks out the cloned branch.|

<br>

|Create&nbsp;a&nbsp;new&nbsp;branch|<a id="create-new-branch-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
|`git branch <new-branch-name>`| Creates new branch originating from HEAD on branch we are on. Does NOT CHECK OUT the branch.|
|`git branch <new-branch-name> <hash-or-tag>`| Creates new branch originating from a specific hash or tag. Does NOT CHECK OUT the branch.|
|`git checkout -b <new-branch-name>`| Creates new branch originating from HEAD on branch we are on and CHECKS OUT the new branch. If desired to checkout based not on current HEAD but another branch then add <branch-name-to-checkout-from>|

<br>

|Check&nbsp;-&nbsp;out&nbsp;a&nbsp;branch&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|<a id="check-out-branch-commands" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|:--|
||_General for checkout commands_<br>If there are uncommitted modification and a risk that checkout command overwrite those then checkout will abort. Plain checkout command switches the content we have in our working directory but with `-b` flag it also creates a new branch.<br><br>By default git checkout will base the new-branch off the current HEAD.  If <branch-name-to-checkout-from> is added in the end then checkout bases new-branch off of existing-branch instead of the current HEAD.|
| `git checkout .` |Overwrites all files that are not staged with the versions pointed out by current HEAD. Can be ued to clear or reset the working directory. stage files remain untouched. |
|`git checkout <other-local-branch>`|Checks out a defined branch.|
|`git checkout -- <file-name>`|checks out a defined filename (`--` used to mark start of file name) |
|`git checkout <hash or tag>`|Checks out a defined hash or tag.|
|`git checkout HEAD~2 --<file-name>`| Drops all modifications of <file-name> and replaces the file with its version from HEAD~2 = two commits before the current. |
|`git checkout HEAD^`| Checks out previous commit from the one we point to in [Detached Head State](#detached-head) |
|`git checkout <other-local-branch> -- <file-name>`|  Drops all modifications of <file-name> by replacing it by onother version of file from diffrent branch |
|`git checkout -b <new-local-branch>`|Creates & checks out new branch originating from current HEAD (= tip of the branch we are currently on).|
|`git checkout -b <new-local-branch> <from-local-branch>`| Creates & checks out new branch originating from another local branch.|

<br>

|Remote&nbsp;connections|<a id="remote-connections-in-git" href="#useful-git-commands-m" title="Back to top">↩</a>|
|:--|---|---|---|
|`git`&nbsp;`remote -v`| List all remote connections |||
|`git`&nbsp;`remote remove <connection-name>`| Delete a  remote connection |||
|`git`&nbsp;`remote`&nbsp;`add`<br>`<connection-name> <remote-url>`| Add new remote connection with given name and url. First delete one existing with same name. |||
|`git remote set-url`<br>`<connection-name> <remote-url>`| Changes url in existing remote connection |||
|`TODO`| set upstream |||

<br>

|SYNCHRONIZE&nbsp;WITH&nbsp;REMOTE<a id="synchronize-with-remote-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
||Commands `fetch`, `pull` and `push` are used for synchronizing with remote. Fetch is part of pull but pull additionally merges the __TODO__ When time to push changes in your local repo to remote then first fetch from from remote and merge  or rebase locally. This because there might be changes on remote conflicting with your changes. Solve all those conflicts and test locally before finally uploading (pushing) the result to remote repo.<br><br>Note! "Git pull" run two different git commands for you. You're better off, until you are 		well-experienced with Git, using separate "git fetch" and "git merge" commands. But this may 	Cause Conflicts to occur, so it’s recommended to use Git Pull with a clean copy. Note that "git pull --rebase" switches the second command to git rebase, but we won't get into details here.<br><br>Write something about --allow-unrelated-histories TODO  `--allow-unrelated-histories` forces to accept files that are not related to the project i.e. when merging 2 different projects. <br><br>__Note!__ If a branch with same name that the one we push from do not exist in remote repo then such a branch is then created in remote.<br><br> __Note!__ It is important to understand that if in remote branch that we try to push to exist changes/commits that we do not have in our local branch then the push will fail. This because push command to not perform any background merge! In such cases we first must update out lo
  Download a complete list with all git commands [HERE](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf).|||
|`git push <remote-connection-name> <branch-to-push-from>`|  If pushing from other branch than our checked out one i.e. `git push origin master`|||
|`git git push <remote-connection-name> --all`| If pushing all existing local branches i.e. `git push origin -all` |||
| `git push -u URL-to-REMOTE TEST`| Fetches all remote branches from remote connection with name... |||
| `git push -u <remote-name>`| Fetches all remote branches from defined remote connection. Due to flag `-u` an "upstream" is set for each of the local branches. |||
| `git fetch`| Fetch all branches from remote  __TODO__  |||

<br>

|STAGE&nbsp;&&nbsp;COMMIT<a id="stage-commit-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
| `git add <.> or <file> ` |  Stages all files (or defined file) from working tree to index |||
| `git commit <.> or <file>`<br>`-m <"description">` |  Commits all files (or defined one) from index to commit history. |||
| `git commit <.> or <file>`<br>`-am <"description">` |  Commits all files (or defined one) from __both__ working tree and index to commit history. |||

<br>

|MERGE&nbsp;&&nbsp;REBASE<a id="merge-rebase-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
||Both of these commands are designed to integrate changes from one branch into another branch—they just do it in very different ways. When rebasing you move the base of the change ending point. Merging adds a new commit to your history. Merge preserves history whereas rebase rewrites it. Rebase will present conflicts one commit at a time whereas merge will present them all at once. It is better and much easier to handle the conflicts but you shouldn’t forget that reverting a rebase is much more difficult than reverting a merge if there are many conflicts. The golden rule of git rebase is to never use it on public branches. The first step in any workflow that leverages git rebase is to create a dedicated branch for each feature. This gives you the necessary branch structure to safely utilize rebasing.  If you would prefer a clean, linear history free of unnecessary merge commits, you should reach for git rebase instead of git merge when integrating changes from another branch.<br><br>On the other hand, if you want to preserve the complete history of your project and avoid the risk of re-writing public commits, you can stick with git merge. Either option is perfectly valid, but at least now you have the option of leveraging the benefits of git rebase.  <br><br> |||
| `git merge <remote-name>/<remote-tracking-branch>`| Merges changes from a connected remote-tracking branch to the branch we  have checked out. Usually done after fetch have updated the remote-tracking branch. __TODO__ |||
| `git rebase ...` | add good example __TODO__|||

<br>

|DIFF & LOGS<a id="diff-logs-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
||It is easier to use graphical tools or VSCode plugins to show diffs but here are some command to use in command window.|||
| `git log -4 --oneline` | Shows last 4 commits for current branch, each on one line, nicely printed.  |||
| `git log --all --oneline -- <file-name>` | Shows all commits for given file, each on one line.  |||
| `git diff -- <file-name>` __TODO__ do we need --| Show changes for a file:. __working tree__ vs __index__ |||
| `git diff --staged -- <file-name>` __TODO__ do we need --| Show changes for a file: __index__ vs __committed__ |||

<br>

|UNDO&nbsp;&&nbsp;CORRECT<a id="undo-correct-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
||There are different ways to "undo" saved, staged or committed modification. Note! Newly added files and folders are untracked before staged and therefore removed in slightly different way.|||
| `git reset HEAD^` | __Roll back latest commit.__ Undoes last commit and moves all files back to staging area. |||
| `git reset -- . or [-- <file-name>]` |__Roll back staged files.__ Moves all files (or defined one) from staging area to working tree.<br> Note! Risk to loose staged change if staged is at same time modified in working tree! |||
| `git checkout -- . [or -- <file-name>]`|__Delete unstaged files.__ Permanently removes all changed files (or defined one) from working tree. Files in index remains untouched. |||
| `git reset --hard ` |__Delete all uncommited files.__ Remove all uncommitted files. Clears both staging area and working tree. Files in ".gitignore" and "untracked" remain untouched. |||
| `git clean -fd -- . [or -- <file-name>]`|__Delete all untracked files.__  Permanently remove all newly added "untracked" files from working tree and filesystem.  |||
| `git commit --amend -m "Corrected message"` __TODO__ testa |  Correct the commit message on latest commit.  |||
| `git commit --amend s1e"` __TODO__ testa |  Add additional modification to last commit.|||
| ` git rm <file-name>` __TODO__ testa |  Delete a file in working tree & stages this change. You need to committed in order to remove the file in repo.  |||

<br>

|CONFLICTS<a id="conflicts-commands" align=left href="#useful-git-commands-m" title="go to top">&nbsp;&nbsp;&nbsp;&nbsp;↩&nbsp;&nbsp;&nbsp;</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||||
|:--|---|---|---|
||We get merging conflicts when we a merge/rebase need our intervention. Also when pulling from remote sometimes an internal merge can fail due to conflicts. Then the pull is aborted and conflicted files are added to "working tree" and must be resolved and committed to fullfil the merge. We recommend always to start a pull/merge/rebase with empty "working tree" and "index"<br><br> |||
| `Fix the conflict` | First show files with git status. Then edit all conflicted files in your in i.e. VSCode. Git adds line `=======` in each "center" of the conflict. Above we find code we merge from (origin). Below is the code we merge to (local). Remove unwanted code, make sure file looks as expected, test and save. Finally commit with "`git commit`" and the merging operation will finnish.|||

<br>
<p align=right><a id="useful-git-aliases-m" align=right href="#table-of-content">↩ Back To Top</a></p>

### [__Useful Git Aliases__](#)
Copy those aliases to command prompt. Those are used often. Timesaver.


All commits in a graph<br>
`alias gra="
echo '___________________________________________' &&
echo '> git log -all --decorate --oneline --graph' &&
echo ' ' &&
git log --all --decorate --oneline --graph
"`

Current status<br>
`alias sta="
echo '____________' &&
echo '> git status' &&
echo ' ' &&
git status
"`

Prints common status information<br>
`alias status="
echo '_________________________________________' &&
echo '> git log -4 --decorate --oneline --graph --first-parent' &&
echo ' ' &&
git log -4 --decorate --oneline --graph --first-parent &&
echo ' ' &&
git remote -v &&
echo ' ' &&
echo '>>> git branch -a -v' &&
echo ' ' &&
git branch -a -v && 
echo ' ' &&
echo '>>> git status' &&
echo ' ' &&
git status 
"`

<br>
<p align=right><a id="useful-cmd-commands-m" align=right href="#table-of-content">↩ Back To Top</a></p>

### [__Useful Cmd Commands:__](#)

It is good to know and memorize those basic command that are often used:

|Cmd&nbsp;command|Description|
|:---|:---|
|`pwd`| Print Working Directory. Writes out full path of currently executing folder. |
|`ls -force` \| `dir -force` <br> `ls -a` \| `dir -a`|List all content (including hidden files) in current working directory. <br> "- force" for VSCode terminal /powershell) and "-a". for Git Bash. |
|`cd [path]` <br> `cd ..`|Change location to path or back|
|`mkdir [dirName]`|Creates a new directory in current location|
|`rm [dirName]`|Deletes a directory|
|touch [fileName]|Creates a new file in current location|
|cat [fileName]|Prints content of a file in terminal window|
|ipconfig|detailed information about your current network adapter connection including current IP address|
|copy [soure] [dest]|Copies a source file to destination|
|`cls` or `clear`|Clear the command screen|

<br>
<p align=right><a id="git-ignore-file-m" align=right href="#table-of-content">↩ Back To Top</a></p>

### [__.gitignore file__](#)

Gitignore file is a file in root of your project which tells Git which files not to track. #todo who creates it?.<br> 
A gitignore file may look like following:

```
# Numerous always-ignore extensions
*.diff
*.err
*.orig
*.log
*~
*.sass-cache
node_modules/
.tmp/

# OS or Editor folders
.DS_Store
Thumbs.db
.cache
.__project__
.settings

...
```
