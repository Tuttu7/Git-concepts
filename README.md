

#### Install git and create folder name git-task and initialise it.
```

tuttu@Tuttu:~$ mkdir git-task


tuttu@Tuttu:~$ cd git-task/

tuttu@Tuttu:~/git-task$ git init
Initialized empty Git repository in /home/tuttu/git-task/.git/

tuttu@Tuttu:~/git-task$ ls
tuttu@Tuttu:~/git-task$ ls -al
total 12
drwxrwxr-x  3 tuttu tuttu 4096 Jun 16 12:13 .
drwxr-xr-x 30 tuttu tuttu 4096 Jun 16 12:12 ..
drwxrwxr-x  7 tuttu tuttu 4096 Jun 16 12:13 .git

tuttu@Tuttu:~/git-task$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```


#### Add file named "first.txt" and commit as "First commit"

````

tuttu@Tuttu:~/git-task$ touch first.txt
tuttu@Tuttu:~/git-task$ git add first.txt
tuttu@Tuttu:~/git-task$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   first.txt
  
tuttu@Tuttu:~/git-task$ git commit -m "First commit"
[master (root-commit) 0db7c2c] First commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 first.txt
 
 ````
 
#### Add 1 more file "second.txt" and commit as "Second commit"

````
tuttu@Tuttu:~/git-task$ touch second.txt
tuttu@Tuttu:~/git-task$ 
tuttu@Tuttu:~/git-task$ git add second.txt
tuttu@Tuttu:~/git-task$ git commit -m "second commit"
[master 77fb0bf] second commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 second.txt
````


#### Create a branch named "ffbranch" and switch to it

````
tuttu@Tuttu:~/git-task$ git branch ffbranch
tuttu@Tuttu:~/git-task$ git checkout ffbranch
Switched to branch 'ffbranch'
````

#### Edit both files add some small changes and commit as,

#### For first.txt "FF branch commit first.txt"

#### For second.txt "FF branch commit second.txt"

````

tuttu@Tuttu:~/git-task$ git add first.txt 
tuttu@Tuttu:~/git-task$ git commit -m "FF branch commit first.txt"
[ffbranch 1c3fb07] FF branch commit first.txt
 1 file changed, 1 insertion(+)
 
tuttu@Tuttu:~/git-task$ git add second.txt 
tuttu@Tuttu:~/git-task$ git commit -m "FF branch commit second.txt"
[ffbranch ef6a27b] FF branch commit second.txt
 1 file changed, 1 insertion(+)
````


#### Switch to master or main branch and merge FF branch to main.

````
 
 tuttu@Tuttu:~/git-task$ git checkout master
Switched to branch 'master'
tuttu@Tuttu:~/git-task$ git merge ffbranch
Updating 77fb0bf..ef6a27b
Fast-forward
 first.txt  | 1 +
 second.txt | 1 +
 2 files changed, 2 insertions(+)
 
 #### Edit the merge message and save as "First Merge from FF branch to main"
 
 ````
 
 tuttu@Tuttu:~/git-task$ git commit --amend -m "First Merge from FF branch to main"
[master 26c14a7] First Merge from FF branch to main
 Date: Fri Jun 17 11:02:24 2022 +0530
 1 file changed, 1 insertion(+)
 
 ````

 #### Create another branch named "dvbranch" and switch to it.
 
 ````
 
 tuttu@Tuttu:~/git-task$ git branch dvbranch
tuttu@Tuttu:~/git-task$ git checkout dvbranch
Switched to branch 'dvbranch'

````


#### Edit both files add some small changes and commit as,

#### For first.txt "DV branch commit first.txt"

#### For second.txt "DV branch commit second.txt"

````

tuttu@Tuttu:~/git-task$ vi first.txt 
tuttu@Tuttu:~/git-task$ vi second.txt 
tuttu@Tuttu:~/git-task$ git add first.txt 
tuttu@Tuttu:~/git-task$ git commit -m "DV branch commit first.txt"
[dvbranch 1ccb83a] DV branch commit first.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
tuttu@Tuttu:~/git-task$ git add second.txt 
tuttu@Tuttu:~/git-task$ git commit -m "DV branch commit second.txt"
[dvbranch 24ec557] DV branch commit second.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
````
 
 #### Switch to master or main branch and edit any of the file and commit
 
 ````
 tuttu@Tuttu:~/git-task$ git checkout master
Switched to branch 'master'

````

#### For first.txt "DV branch ready for conflict"

#### And now merge DV branch to main [conflict? solve it!]

````

tuttu@Tuttu:~/git-task$ vi first.txt 
tuttu@Tuttu:~/git-task$ git add first.txt 
tuttu@Tuttu:~/git-task$ git commit -m "DV branch ready for conflict"
[master 6630666] DV branch ready for conflict
 1 file changed, 1 insertion(+), 1 deletion(-)
tuttu@Tuttu:~/git-task$ git merge dvbranch
Auto-merging first.txt
CONFLICT (content): Merge conflict in first.txt
Automatic merge failed; fix conflicts and then commit the result.



tuttu@Tuttu:~/git-task$ git add first.txt 
tuttu@Tuttu:~/git-task$ git merge dvbranch
fatal: You have not concluded your merge (MERGE_HEAD exists).
Please, commit your changes before you merge.
tuttu@Tuttu:~/git-task$ git commit 
[master 67620c1] Merge branch 'dvbranch'
tuttu@Tuttu:~/git-task$ git commit -m "change"
On branch master
nothing to commit, working tree clean
tuttu@Tuttu:~/git-task$ git merge dvbranch
Already up to date.

````

#### Edit the merge message and save as "Second Merge almost killed me!"

````

tuttu@Tuttu:~/git-task$ git commit --amend -m "Second Merge almost killed me!"
[master 0b4b218] Second Merge almost killed me!
 Date: Fri Jun 17 11:21:58 2022 +0530
````



#### Create 2 branches called "stash-me" and "stash-fw" and switch to stash-me

````
 
 tuttu@Tuttu:~/git-task$ git branch stash-me
tuttu@Tuttu:~/git-task$ git branch stash-fw
tuttu@Tuttu:~/git-task$ git checkout stash-me 
Switched to branch 'stash-me'


````

#### Create a file stashme.txt and edit n paste the message "Not going to save here" [ IMP : Dont commit ]

````
tuttu@Tuttu:~/git-task$ touch stashme.txt
tuttu@Tuttu:~/git-task$ vi stashme.txt
````

#### Switch and Commit it to stash-fw branch.

````

tuttu@Tuttu:~/git-task$ git checkout stash-fw
Switched to branch 'stash-fw'
tuttu@Tuttu:~/git-task$ git commit -m "comit"
On branch stash-fw
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	stashme.txt

nothing added to commit but untracked files present (use "git add" to track)


tuttu@Tuttu:~/git-task$ git add stashme.txt

tuttu@Tuttu:~/git-task$ git commit -m "comit"
[stash-fw 86bfff7] comit
 1 file changed, 1 insertion(+)
 create mode 100644 stashme.txt
 
 ````
 
 #### Now switch to master and edit first.txt and add text "Stash sceneario 2" and commit as "Stash sceneario phase 2"
 
 ````
tuttu@Tuttu:~/git-task$ git checkout master
Switched to branch 'master'
tuttu@Tuttu:~/git-task$ vi first.txt 
tuttu@Tuttu:~/git-task$ git add first.txt 
tuttu@Tuttu:~/git-task$ git commit -m "Stash sceneario phase 2"
[master b8059dc] Stash sceneario phase 2
 1 file changed, 1 insertion(+)
 
 ````
 
 #### Switch to stash-fw and edit first.txt add message "No way back" [ IMP : Dont commit ]

````
tuttu@Tuttu:~/git-task$ git checkout stash-fw
Switched to branch 'stash-fw'
tuttu@Tuttu:~/git-task$ vi first.txt 
````

#### Now try to switch to main. Not able to switch ? Git wont let you do it.[ Conflict ?? Real use of stash ]

#### Stash and move on.

````
tuttu@Tuttu:~/git-task$ git checkout master
error: Your local changes to the following files would be overwritten by checkout:
	first.txt
Please commit your changes or stash them before you switch branches.
Aborting
`````


