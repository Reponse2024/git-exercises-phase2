# Advanced Git Challenges
## Part 1
### Getting started
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main (root-commit) 881e61d] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main 2efcd2f] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main 4f8b9d0] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
```
### Challenge 1
``` bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log
commit 4f8b9d0b5580a6e745eb97ccf7bd697591c61be2 (HEAD -> main)
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:58 2025 +0200

    chore: Create third and fourth files

commit 2efcd2f43c620e3ebda3e0519e9a92712bf4ae93
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:57 2025 +0200

    chore: Create another file

commit 881e61dcd186252c5df451e3779ba30632b9f6e5
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:56 2025 +0200

    chore: Create initial file

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add 'test4.md'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit --amend -m "Create third and fourth file"
[main 593eebd] Create third and fourth file
 Date: Tue Jul 22 14:53:58 2025 +0200
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
 create mode 100644 test3.md
 create mode 100644 test4.md
```
### Challenge 2
``` bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log --oneline
593eebd (HEAD -> main) Create third and fourth file
2efcd2f chore: Create another file
881e61d chore: Create initial file

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git rebase -i 881e61d
Stopped at 2efcd2f...  # chore: Create another file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|REBASE 1/2)
$ git commit --amend
[detached HEAD 9cb2302] chore: Create second file
 Date: Tue Jul 22 14:53:57 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|REBASE 1/2)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.
```
### Challenge 3
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log
commit 78e6a28aca50c9d8915ac937a3bed8d7ec4a2246 (HEAD -> main)
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:58 2025 +0200

    Create third and fourth file

commit 9cb2302b784c47d00dabef4cc6c4089a9940deb2
Author: Reponse <reponse.iduha2023@kepler.org>
pick 9cb2302 # chore: Create second file
pick 78e6a28 # Create third and fourth file

# Rebase 881e61d..78e6a28 onto 881e61d (2 commands)     
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending  
# s, squash <commit> = use commit, but meld into previous commit# f, fixup [-C | -c] <commit> = @@@                             <unix] (15:08 22/07/2025)1,1 Top<" [unix] 33L, 1566B
#         message (or the oneline, if no original merge commit was
#         specified); use -c <commit> to reword the commit message
# u, update-ref <ref> = track a placeholder for the <ref> to be updated
#                       to this position in the new commits. The <ref> is
#                       updated at the end of the rebase#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.   
#
# However, if you remove everything, the rebase will be aborted.
#
```
### Challenge 4
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git reset HEAD~1

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add test3.md

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "chore: Create third file"
[main d59f741] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add test4.md
#         message (or the oneline, if no original merge 
#

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "chore: Create fourth file"
[main 0ac1e72] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)        
 create mode 100644 test4.md
```
### Challenge 5
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git rebase -i HEAD~2
[detached HEAD b0ec138] chore: Create third file
 Date: Tue Jul 22 15:30:05 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)       
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.       

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
```
### Challenge 6
``` bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ touch unwanted.txt

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-pha
#         message (or the oneline, if no original merge se2 (main)
$ echo "This has to be deleted"> unwanted.txt

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
#         message (or the oneline, if no original merge $ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the next time Git touches it        

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "Unwanted commit"
[main 5003c85] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.       

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.       

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log
commit b0ec138c3c5d405f47eb65397bd3962f9aec9019 (HEAD ->
 main)
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 15:30:05 2025 +0200

    chore: Create third file

    chore: Create fourth file

commit 9cb2302b784c47d00dabef4cc6c4089a9940deb2
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:57 2025 +0200

    chore: Create second file

#         message (or the oneline, if no original merge commit 881e61dcd186252c5df451e3779ba30632b9f6e5
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:56 2025 +0200


User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "Drop an unwanted commit"
[main fa663ae] Drop an unwanted commit
 1 file changed, 205 insertions(+)
 create mode 100644 README.md
```
### Challenge 7
```bash
#         message (or the oneline, if no original merge 

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log --oneline
fa663ae (HEAD -> main) Drop an unwanted commit
b0ec138 chore: Create third file
9cb2302 chore: Create second file
881e61d chore: Create initial file

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.       

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
```
### Challenge 8
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/branch)
$ touch 'test5.md'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/branch)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch 3daee78] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 3 and 3 different commits each, respectively.  
  (use "git pull" if you want to integrate the remote branch with yours)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log ft/branch
commit 3daee78e5cb45a11b38074de9048549adf753931 (ft/branch)
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Wed Jul 23 16:09:21 2025 +0200

    Implemented test 5

commit dfbfc4844ef1de9ad2691165579534fbc8c47f55 (HEAD ->
 main)
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 14:53:57 2025 +0200

    chore: Create second file

commit 3a03e27c1bd6ae5d8829eda61444df8b32446efe
Author: Reponse <reponse.iduha2023@kepler.org>
Date:   Tue Jul 22 15:49:42 2025 +0200

    Drop an unwanted commit

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git cherry-pick 3daee78e5cb45a11b38074de9048549adf753931
[main 04add2c] Implemented test 5
 Date: Wed Jul 23 16:09:21 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2
```
### Challenge 9
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log --graph
* commit 04add2c1c2235afd8bb8ea5e7ee3bd45a39495e6 (HEAD -> main)
| Author: Reponse <reponse.iduha2023@kepler.org>
| Date:   Wed Jul 23 16:09:21 2025 +0200
| 
|     Implemented test 5
| 
* commit dfbfc4844ef1de9ad2691165579534fbc8c47f55
| Author: Reponse <reponse.iduha2023@kepler.org>
| Date:   Tue Jul 22 14:53:57 2025 +0200
| 
|     chore: Create second file
| 
* commit 3a03e27c1bd6ae5d8829eda61444df8b32446efe
| Author: Reponse <reponse.iduha2023@kepler.org>
| Date:   Tue Jul 22 15:49:42 2025 +0200
|
|     Drop an unwanted commit
```
### Challenge 10
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git reflog
04add2c (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
dfbfc48 HEAD@{1}: checkout: moving from ft/branch to main
3daee78 (ft/branch) HEAD@{2}: commit: Implemented test 5
dfbfc48 HEAD@{3}: checkout: moving from main to ft/branch
dfbfc48 HEAD@{4}: rebase (finish): returning to refs/heads/main
dfbfc48 HEAD@{5}: rebase (pick): chore: Create second file
3a03e27 HEAD@{6}: rebase (pick): Drop an unwanted commit
be0700a HEAD@{7}: rebase (pick): chore: Create third file
881e61d HEAD@{8}: rebase (start): checkout HEAD~3       
fa663ae HEAD@{9}: rebase (abort): returning to refs/heads/main
911ffa8 (origin/main) HEAD@{10}: rebase (start): checkout refs/remotes/origin/main
:
```
## Part 2
### Challenge 1
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-feature)
$ 
```
### Challenge 2
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-feature)
$ echo "This is a new feature." > feature.txt
git add feature.txt
git commit -m "feat: Implemented core functionality for new featuree"
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it
[ft/new-feature b6316f1] feat: Implemented core functionality for new featuree
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
 ```
 ### Challenge 3
 ``` bash
 User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-feature)
$ git checkout main
echo "Welcome to the project!" > readme.txt
git add readme.txt
git commit -m "docs: Updated project readme"
M       README.md
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 5 and 7 different commits each, respectively.  
  (use "git pull" if you want to integrate the remote branch with yours)
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
[main ef036ac] docs: Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
 ```
 ### Challenge 4
 ```bash
 User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git push origin ft/new-feature
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 2 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (9/9), 2.24 KiB | 382.00 KiB/s, done.
Merge branch 'ft/new-feature' of https://github.com/RepoTotal 9 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/Reponse2024/git-exercises-phase2/pull/new/ft/new-feature
remote:
To https://github.com/Reponse2024/git-exercises-phase2.git
 * [new branch]      ft/new-feature -> ft/new-feature   

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git pull origin ft/new-feature
From https://github.com/Reponse2024/git-exercises-phase2
 * branch            ft/new-feature -> FETCH_HEAD       
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
 ```
 ### challenge 5
 ``` bash
 User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was b6316f1).
```
### Challenge 6
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log --oneline
e94ac91 (HEAD -> main) Merge branch 'ft/new-feature' of https://github.com/Reponse2024/git-exercises-phase2     
ef036ac docs: Updated project readme
b6316f1 (origin/ft/new-feature) feat: Implemented core functionality for new featuree
d8ef7d5 Solved all challenges in part 1
04add2c Implemented test 5
dfbfc48 chore: Create second file
3a03e27 Drop an unwanted commit
be0700a chore: Create third file
881e61d chore: Create initial file

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout -b ft/new-branch-from-commit ef036ac
M       README.md
Switched to a new branch 'ft/new-branch-from-commit'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$
```
### Challenge 7
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 8 and 7 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git merge ft/new-branch-from-commit
Merge made by the 'ort' strategy.
 README.md | 96 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 96 insertions(+)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .
```
### Challenge 8
```bash

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout ft/new-branch-from-commit
M       README.md
Switched to branch 'ft/new-branch-from-commit'
Your branch is up to date with 'origin/ft/new-branch-from-commit'.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$ git commit -m "Added challenge 7 in readme file"
[ft/new-branch-from-commit ab3311d] Added challenge 7 in readme file
 1 file changed, 18 insertions(+)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)
$
```
### Challenge 9
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/new-branch-from-commit)

$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)
$ git branch
  ft/branch
* ft/improved-branch-name
  main

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)  
$
```
### Challenge 10
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)
$ git commit -m "Saved cahnges before checking out has commit"
[ft/improved-branch-name 92fd334] Saved cahnges before checking out has commit
 1 file changed, 40 insertions(+)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)
$ git log --online
fatal: unrecognized argument: --online

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)
$ git log --oneline
92fd334 (HEAD -> ft/improved-branch-name) Saved cahnges before checking out has commit
29aa7c0 Added challenge 7 in readme file
ffb33e2 (main) Merge branch 'ft/new-branch-from-commit'
fe456fd (origin/ft/new-branch-from-commit) Created new branch from commit
e94ac91 Merge branch 'ft/new-feature' of https://github.com/Reponse2024/git-exercises-phase2
ef036ac docs: Updated project readme
b6316f1 (origin/ft/new-feature) feat: Implemented core functionality for new featuree  
d8ef7d5 Solved all challenges in part 1
04add2c Implemented test 5
dfbfc48 chore: Create second file
3a03e27 Drop an unwanted commit
be0700a chore: Create third file
881e61d chore: Create initial file

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/improved-branch-name)  
$ git checkout 04add2
Note: switching to '04add2'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 04add2c Implemented test 5

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 ((04add2c...))
$ git checkout -b temp-branch
Switched to a new branch 'temp-branch'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (temp-branch)
$
```
## Part 3
### Challenge 1
```bash
### Challenge 1
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash
Saved working directory and index state WIP on main: 43459ee Resolved conflicts

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash list
stash@{0}: WIP on main: 43459ee Resolved conflicts
```
### Challenge 2
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash pop
On branch main
Your branch and 'origin/main' have diverged,
and have 12 and 7 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (e0879e2b0c1e4db923bae254199d5419a1fb5ebd)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash apply
No stash entries found.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
### Challenge 3
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ echo "Original line" > conflict.txt
git add conflict.txt
git commit -m "chore: Add conflict.txt to main"
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it
[main e30871d] chore: Add conflict.txt to main
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout -b ft/conflict
Switched to a new branch 'ft/conflict'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/conflict)
$ echo "Change from feature branch" > conflict.txt
git add conflict.txt
git commit -m "feat: Update conflict.txt in feature branch"
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it        
[ft/conflict 49a9b2c] feat: Update conflict.txt in feature branch
 1 file changed, 1 insertion(+), 1 deletion(-)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (ft/conflict)
$ git checkout main
echo "Change from main branch" > conflict.txt
git add conflict.txt
git commit -m "fix: Update conflict.txt in main"        
M       README.md
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 13 and 7 different commits each, respectively. 
  (use "git pull" if you want to integrate the remote branch with yours)
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it        
[main 12362c5] fix: Update conflict.txt in main
 1 file changed, 1 insertion(+), 1 deletion(-)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git merge ft/conflict
Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt      
Automatic merge failed; fix conflicts and then commit the result.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|MERGING)
$ git merge ft/conflict
```
### Challenge 4
```bash
ser@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|MERGING)
$ git merge ft/conflict
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.       

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|MERGING)
$ git add conflict.txt
git commit
[main 43140e6] Merge branch 'ft/conflict'

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
### Challenge 5
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git log --oneline
43140e6 (HEAD -> main) Merge branch 'ft/conflict'
12362c5 fix: Update conflict.txt in main
43140e6 (HEAD -> main) Merge branch 'ft/conflict'       
12362c5 fix: Update conflict.txt in main
49a9b2c (ft/conflict) feat: Update conflict.txt in feature branch
e30871d chore: Add conflict.txt to main
43459ee Resolved conflicts
63c768f Modified challenge 1 of part
ffb33e2 Merge branch 'ft/new-branch-from-commit'        
fe456fd (origin/ft/new-branch-from-commit) Created new branch from commit
e94ac91 Merge branch 'ft/new-feature' of https://github.com/Reponse2024/git-exercises-phase2
ef036ac docs: Updated project readme
b6316f1 (origin/ft/new-feature) feat: Implemented core functionality for new featuree
d8ef7d5 Solved all challenges in part 1
04add2c (temp-branch) Implemented test 5
dfbfc48 chore: Create second file
3a03e27 Drop an unwanted commit

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout 04add2c      
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m 'Modifies readme file"
> git commit -m 'Modifies readme file'
> git commit -m 'Modifies readme file"
git commit -m "Modifies readme file"
> ^C

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "Modifies readme file"
[main 5b8a8db] Modifies readme file
 1 file changed, 79 insertions(+), 11 deletions(-)      

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git checkout 04add2c      
Note: switching to '04add2c'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 04add2c Implemented test 5

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 ((04add2c...))
$ git checkout main
Previous HEAD position was 04add2c Implemented test 5
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 17 and 7 different commits each, respectively. 
  (use "git pull" if you want to integrate the remote branch with yours)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
###  Challenge 6
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ echo "/tmp" >> .gitignore

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .gitignore
git commit -m "chore: Ignore temp files in /tmp"        
warning: in the working copy of '.gitignore', LF will be replaced by CRLF the next time Git touches it
[main 006fc86] chore: Ignore temp files in /tmp
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
### Challenge 7
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git tag v1.0

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git tag -a v1.0 -m "Release version 1.0"
fatal: tag 'v1.0' already exists

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
```
### Challenge 8
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git tag
v1.0

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 006fc86)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git push origin :refs/tags/v1.0
To https://github.com/Reponse2024/git-exercises-phase2.git
 - [deleted]         v1.0

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
### Challenge 9
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git commit -m "Added challenge 8"
[main a1a91ec] Added challenge 8
 1 file changed, 121 insertions(+)

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git pull
Auto-merging README.md
CONFLICT (add/add): Merge conflict in README.md       
Automatic merge failed; fix conflicts and then commit the result.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|MERGING)
$ git add .

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main|MERGING)
$ git commit -m "merged the changes by resolving the c
conflicts"
[main 2cf5242] merged the changes by resolving the cconflicts

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git push origin main
Enumerating objects: 39, done.
Counting objects: 100% (38/38), done.
Delta compression using up to 2 threads
Compressing objects: 100% (27/27), done.
Writing objects: 100% (31/31), 3.37 KiB | 215.00 KiB/s, done.
Total 31 (delta 15), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (15/15), completed with 1 local object.
To https://github.com/Reponse2024/git-exercises-phase2.git
   c069df6..2cf5242  main -> main

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```
### Challenge 10
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git pull origin main
From https://github.com/Reponse2024/git-exercises-phase2
 * branch            main       -> FETCH_HEAD
Already up to date.

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$
```








