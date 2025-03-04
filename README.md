# Challenges:
## Part 1: Refining Git History (10 Challenges)

### 1. Missing File Fix:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main 5a77e9f] chore: Create initial file
 4 files changed, 42 deletions(-)
 delete mode 100644 README.md
 delete mode 100644 test2.md
 delete mode 100644 test3.md
 delete mode 100644 test4.md
[main 6a94024] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main bc3feb4] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add test4.md
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit --amend 
[main be53577] reword: Create third and fourth files
 Date: Wed Feb 26 12:27:39 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```

### 2. Editing Commit History:
```bash
git rebase -i HEAD~2
[detached HEAD 05abb2f] chore: Create second file
 Date: Wed Feb 26 12:27:38 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
```

### 3. Keeping History Tidy - Squashing Commits:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git rebase -i --root
[detached HEAD 481d287] chore: Create initial file
 Date: Wed Feb 26 12:27:38 2025 +0200
 3 files changed, 42 deletions(-)
 delete mode 100644 README.md
 delete mode 100644 test3.md
 delete mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

```

### 4. Splitting a Commit:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git reset HEAD~
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git status          
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add test3.md    
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit -m "Create third file"
[main 62e2fab] Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add test4.md                 
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit -m "Create fourth file"
[main adf15a6] Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
```

### 5. Advanced Squashing
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git rebase -i --root              
[detached HEAD 4957000] Create third file and fourth file
 Date: Wed Feb 26 12:45:33 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

### 6. Dropping a Commit:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % vi unwanted.txt
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add unwanted.txt  
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit -m "Unwanted commit"
[main baf8d36] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.
```

### 7. Reordering Commits:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git rebase -i --root
```

### 8. Cherry-Picking Commits:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git cherry-pick a66691850683301abab1014e38c6e60cf838ab92
[main 34b84ea] Implemented test 5
 Date: Mon Mar 3 09:56:04 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
```

### 9. Visualizing Commit History (Bonus):
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises %  git adog
* 34b84ea (HEAD -> main) Implemented test 5
* 4957000 Create third file and fourth file
* 481d287 chore: Create initial file
| * a666918 (ft/branch) Implemented test 5
|/  
* d2a1791 (origin/main, origin/HEAD) Read me file
* ed3c1e4 chore: Create third and fourth files
* 718cb94 chore: Create another file
* bd2f084 chore: Create initial file
* 39195db Initial commit
```

### 10. Understanding Reflogs (Bonus):
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git reflog 
34b84ea (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
```

## Part 2: Branching Basics (10 Challenges)
### 1. Feature Branch Creation:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout -b ft/
new-feature
Switched to a new branch 'ft/new-feature'
```

### 2. Working on the Feature Branch:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % vi feature.txt 
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add feature.txt

mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit -m "Implemented core functionality for new feature"
[ft/new-feature 72571d6] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

### 3. Switching Back and Making More Changes:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % vi readme.txt
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git add readme.txt
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git commit -m "Updated project readme"
[main 14785eb] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

### 4. Local vs. Remote Branches
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git push
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 908 bytes | 454.00 KiB/s, done.
Total 10 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/MizeroR/git-advanced-exercises.git
   d2a1791..14785eb  main -> main
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git branch
  ft/branch
  ft/new-feature
* main
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout ft/new
-feature
Switched to branch 'ft/new-feature'
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git push
fatal: The current branch ft/new-feature has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/new-feature

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git push --set-upstream origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 319 bytes | 319.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/MizeroR/git-advanced-exercises/pull/new/ft/new-feature
remote: 
To https://github.com/MizeroR/git-advanced-exercises.git
 * [new branch]      ft/new-feature -> ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.
```

### 5. Branch Deletion:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git pull
Updating 14785eb..6942144
Fast-forward
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git branch       
  ft/branch
  ft/new-feature
* main
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git branch -d ft/ne
w-feature
Deleted branch ft/new-feature (was 72571d6).
```

### 6. Creating a Branch from a Commit:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout -b ft/new-branch-from-commit HEAD~3
Switched to a new branch 'ft/new-branch-from-commit'
```

### 7. Branch Merging:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git branch
  ft/branch
  ft/new-branch-from-commit
* main
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git merge ft/new-branch-from-commit
Already up to date.
```

### 8. Branch Rebasing:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git rebase ft/new-branch-from-commit
Successfully rebased and updated refs/heads/main.
```

### 9. Renaming branches:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git branch -m ft/new-branch-from-commit ft/improved-branch-name
```

### 10. Checking Out Detached HEAD:
```bash
mizeroreine@Mizeros-MacBook-Air git-advanced-exercises % git checkout 34b84ea383bbf801b2bb41b8f3d86da191336725
Note: switching to '34b84ea383bbf801b2bb41b8f3d86da191336725'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 34b84ea Implemented test 5
```

## Part 3: Advanced Workflows (10+ Challenges)
```bash
1118  git log
1119  vi .gitignore
1120  ls
1121  git add .gitignore
1122  ls
1123  ls -a
1124  git commit -m "Git ignore file"
1125  git status
1126  git brnach
1127  git tag v1.0
1128  git adog
1129  git push
1130  git push origin v1.0
1131  git tag
1132  git tag -d v1.0
1133  git status
```
