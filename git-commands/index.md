# git commands

Most useful git commands.
<!--more-->
# intro
Here i summarises the all git commands which is used frequently.
It helps developers manage and track changes in their projects.

```bash
# Initializes a new Git repository in the current directory.
git init
```

```bash
# To configure the the email id in local git repo.
git config --global user.email "your_email_id"
```

```bash
# To configure the username in the local git repo.
git config --global user.name "your-user-name"
```

```bash
# To check the user email in git local repo.
git config --global user.email
```

```bash
# Adds a file or directory to the staging area, preparing it to be committed.
git add .
```

```bash
# to commmit all the changes.
git commit -m "commit_message"
```

```bash
# Uploads local repository changes to the remote repository.
git push -u origin main
```

```bash
echo "# test" >> README.md
```

```bash
git add README.md

```
```bash
git branch -M main
```

```bash
git remote add origin https://github.com/sumit2011/test.git
```

```bash
git clone <repo_link>
```
```bash
git add <file_name>
```

```bash
git status
```
```bash
git config
```
```bash
git pull
```
```bash
git config
```
```bash
# To show the details of the commits.
git log

git rm --cached filename

git diff
```

```bash
git remote -v
```

```bash
```

### Tagging

ex: git tag   
to check  all  the tags

ex: git tag -a v1.0 -m "message"
to add a tag

ex: git push origin v1.0
push the tag separately

ex: git show tag_name

### Branching

ex: git checkout -b feature1
ex: git switch -c feature2
to create a new branch

ex: git branch
ex: git branch --all
to check how many branch are available

ex: git log

ex: git switch main
to switch to the main brach

ex: git switch -
to switch to the prev branch

ex: git branch -d branch_name
to delete the branch

ex: git push origin feature1
to push feature1 branch to github

ex: git merge feature1
merge feature1 to main branch

ex: git pull origin main
first pull -> merge -> then push

ex: git log --graph

ex: git rebase branch_name


ex: git checkout commit_id
go back to prev commit

ex: git stash
want to save the code without committing

ex: git stash list
show all the stash list

ex: git stash apply
to apply the stash 


