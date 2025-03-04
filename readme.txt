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
