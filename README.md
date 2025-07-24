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
92fd334 (HEAD -> ft/improved-branch-name) Saved cahnges before checking out has commit
29aa7c0 Added challenge 7 in readme file
ffb33e2 (main) Merge branch 'ft/new-branch-from-commit'
fe456fd (origin/ft/new-branch-from-commit) Created new branch from commit
e94ac91 Merge branch 'ft/new-feature' of https://github.com/Reponse2024/git-exercises-phase2
ef036ac docs: Updated project readme
b6316f1 (origin/ft/new-feature) feat: Implemented core functionality for new featuree  
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
## part 3
### Challenge 1
```bash
```
## Part 3
### Challenge 1
```bash
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash
Saved working directory and index state WIP on main: ffb33e2 Merge branch 'ft/new-branch-from-commit'

<<<<<<< Updated upstream
User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ git stash list
stash@{0}: WIP on main: ffb33e2 Merge branch 'ft/new-branch-from-commit'
stash@{1}: WIP on temp-branch: 04add2c Implemented test 5

User@DESKTOP-PQL5SE4 MINGW64 /c/TheGym/git-exercises-phase2 (main)
$ 
```

=======
>>>>>>> Stashed changes
