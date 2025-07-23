# Git Exercise
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

