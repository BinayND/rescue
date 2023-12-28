
# List of Command for ubuntu server used during website deployment

Major Command inclue git process, server level command


## Github setup

Config fot token creation and ssh machine

[Reference 1](https://stackoverflow.com/questions/12940626/github-error-message-permission-denied-publickey
)

[Reference 2](https://help.github.com/en/articles/error-permission-denied-publickey)



```bash
git config  --list
 git config --global user.email " "
 git config --global user.name " "
    
```

```bash
$ git init //intialize basic Git repository.
$ git add <file> Add files To index /or .
$ git status //check status of working Tree.
$ git commit -m 'Initial Commit' //commit changes.
$ git push // push to remote repository 
$ git push -u origin gcp_dev // pull the latest from Remote repository
$ git clone  //clone repository into new repository.
```
Mapping Remote repository

```bash
git init  
git remote add origin your_repo.git  
git remote -v  
git status
git remote set-url origin git@bitbucket.org:<USER>/<REPO>.git
```
To remove file

```bash
git rm --cached <filename>
```

Branch level command 
```bash
git checkout branch => for switching purpose
git branch -r  => list branch

```
