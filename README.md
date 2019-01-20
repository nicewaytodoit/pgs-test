# pgs-test
GitHub Pages Test

- let's now try to create orphan branch in two ways 
- and also gh-pages deploy script 
- what is the minium package.json again ?

- Before --
λ git log --oneline --graph
* 934c3ca (HEAD -> master) before creating orpah branch gh-pages
* 56fe189 (origin/master, origin/HEAD) Create Index.html
* e69718a Initial commit

## method one 

### Actions 

```bash
λ git log --oneline --graph
λ git status
λ git checkout master
λ git ls-files
λ git checkout --orphan myorphantest1
λ git log --oneline
λ git status
λ git rm -rf .
λ echo "# My orphan ReadMe" > ReadMe.md
λ git add ReadMe.md
λ git commit -a -m "Initial commit"
λ git status
λ git log --oneline --graph
λ git checkout master
λ git log --oneline --graph
```

### Action Results
```bash
(master -> origin)
λ git log --oneline --graph
* d0ccf28 (HEAD -> master) before creating orpah branch gh-pages
* 56fe189 (origin/master, origin/HEAD) Create Index.html
* e69718a Initial commit

(master -> origin)
λ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

(master -> origin)
λ ll
total 22
drwxr-xr-x 1 mind 197121    0 Jan 20 08:30 .
drwxr-xr-x 1 mind 197121    0 Jan 20 08:30 ..
drwxr-xr-x 1 mind 197121    0 Jan 20 08:36 .git
-rw-r--r-- 1 mind 197121  914 Jan 20 08:30 .gitignore
-rw-r--r-- 1 mind 197121  183 Jan 20 08:30 index.html
-rw-r--r-- 1 mind 197121 1077 Jan 20 08:30 LICENSE
-rw-r--r-- 1 mind 197121  353 Jan 20 08:34 README.md

(master -> origin)
λ git checkout master
Already on 'master'
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

(master -> origin)
λ git ls-files
.gitignore
LICENSE
README.md
index.html

(master -> origin)
λ git checkout --orphan myorphantest1
Switched to a new branch 'myorphantest1'

(myorphantest1 -> origin)
λ git log --oneline
fatal: your current branch 'myorphantest1' does not have any commits yet

(myorphantest1 -> origin)
λ git status
On branch myorphantest1

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   .gitignore
        new file:   LICENSE
        new file:   README.md
        new file:   index.html


(myorphantest1 -> origin)
λ git rm -rf .
rm '.gitignore'
rm 'LICENSE'
rm 'README.md'
rm 'index.html'

(myorphantest1 -> origin)
λ echo "# My orphan ReadMe" > ReadMe.md

(myorphantest1 -> origin)
λ git add ReadMe.md

(myorphantest1 -> origin)
λ git commit -a -m "Initial commit"
[myorphantest1 (root-commit) 4080957] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 ReadMe.md

(myorphantest1 -> origin)
λ git status
On branch myorphantest1
nothing to commit, working tree clean

(myorphantest1 -> origin)
λ git log --oneline --graph
* 4080957 (HEAD -> myorphantest1) Initial commit

(myorphantest1 -> origin)
λ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

(master -> origin)
λ git log --oneline --graph
* d0ccf28 (HEAD -> master) before creating orpah branch gh-pages
* 56fe189 (origin/master, origin/HEAD) Create Index.html
* e69718a Initial commit

## Pushing branches and change to GitHub

λ git status
(master -> origin) λ git push
λ git checkout myorphantest1
(myorphantest1 -> origin) λ git status

(myorphantest1 -> origin) λ git push
fatal: The current branch myorphantest1 has no upstream branch.

(myorphantest1 -> origin) λ git push --set-upstream origin myorphantest1
λ git branch -avv
λ git log --oneline
λ git status

(master -> origin) λ git checkout master
λ git log --oneline
λ git status

```
