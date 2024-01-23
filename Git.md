# Git

### Check Version
```sh
➜  git --version
git version 2.32.0 (Apple Git-132)
```
### Initialize a file as Git repository
```sh
➜  git init
```
### Get updated on Git
```sh
➜  git status

On branch master
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	FileName.txt

nothing added to commit but untracked files present (use "git add" to track)
```
### Tell Git which lifes to track
```sh
➜  git add .
➜  git status

On branch master
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   FileName.txt
```
### commit to Git
```sh
➜  git commit -m "Commit Progress Text"
[master (root-commit) d43b07b] Commit Progress Text
 1 file changed, 1 insertion(+)
 create mode 100644 FileName.txt
```
### See commit versions
```sh
➜  git log

commit e65f9833ca8ee366d0d9c1676a91b1a977dab441 (HEAD -> master)
Author: Kele
Date:   Tue Jan 23 23:32:22 2024 -0700

    changed greeting to reflect the present mood

commit d43b07b8890f52defb31507211ba78785bf6dccf
Author: Kele
Date:   Tue Jan 23 23:29:11 2024 -0700

    initial draft
```
### Switch commit versions to previous
```sh
➜  git checkout d43b07b8890f

Note: switching to 'd43b07b8890f'.
HEAD is now at d43b07b initial draft
```
### Switch to top version
```sh
➜  git checkout master
Previous HEAD position was d43b07b initial draft
Switched to branch 'master'
```
### Compare previous with current
- Use the ~# to compare different commit versions
```sh
➜  git diff HEAD HEAD~1

diff --git a/hello.txt b/hello.txt
index 3b18e51..eeee2af 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1 @@
-hello world
+goodbye world
```
### Clone a Repository
```
git clone https://github.com/YOURACCOUNT/YOURREPO.git

Cloning into 'YOURREPO'...
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
```


### Resources
  - [BYU CS 240](https://learn.cs260.click/page/essentials/git/git_md)
  - [BYU CS 260](https://learn.cs260.click/page/essentials/gitHub/gitHub_md)
  - [BYU CS 260](https://github.com/softwareconstruction240/softwareconstruction/blob/main/instruction/git/git.md)
