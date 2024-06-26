
# List of Command for ubuntu server used during website deployment

Major Command inclue git process, server level command


## Github setup

Config fot token creation and ssh machine

[Reference 1](https://stackoverflow.com/questions/12940626/github-error-message-permission-denied-publickey
)

[Reference 2](https://help.github.com/en/articles/error-permission-denied-publickey)

[inital Project Setup With new account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)


[Add A GitHub Repository To Your Local Machine](https://gist.github.com/ericconrad/ccc1af3cd12a69ef2e6e)


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
Mapping Remote repository For new project on machine

```bash
git init  
git remote add origin your_repo.git - ssh path  
git remote -v  
git status
git remote set-url origin git@bitbucket.org:<USER>/<REPO>.git

If there pathsec error or branch not exist , follow below command
git branch
git fetch origin // first pull on local
git fetch origin branch
git checkout branch 



```
To remove file

```bash
git rm --cached <filename>
```

- While fetching repo new member changes first remove you code or don't start it - solve error Your local changes to the following files would be overwritten by merge: Please commit your changes or stash them before you merge pull request on local machine

  ```
git checkout -- . to discard all changes.
Stash your changes: If you want to temporarily save your changes and apply them later, you can use git stash to stash them. After resolving the merge, you can apply your changes with git stash apply.

  ```

Branch level command 
```bash
git checkout branch => for switching purpose
git branch -r  => list branch

```

## Solving the git pull conflict error steps

```
https://www.simplilearn.com/tutorials/git-tutorial/merge-conflicts-in-git

git stash  --  command is used to save changes that are not ready to be committed yet but need to be temporarily set aside
git stash apply or  git stash pop -- To retrieve your changes that are lost while conflict solving.

```

Always daily do git pull working on any project.

Once you have done the code save on local than push on dir.

```
git stash  -  store on local machine for rollback purpose.
git stash apply - store the previous all working code which was lost during conflict solved.

```

## How to resolve conflict and merge issue 

```
1) Abort the Merge (if necessary): If you've started the merge process but haven't resolved any conflicts yet, you can abort the merge and start over.
git merge --abort

2)git mergetool ->Once you select one, it will launch the tool and guide you through resolving conflicts.
3)git status
4)git diff <conflicted-file>
5) git add <conflicted-file>
6)git merge --continue

```


## Mysql Query Related

Create dummy records in mysql using procedures for faster execution
```bash
DELIMITER //

CREATE PROCEDURE InsertRecords()
BEGIN
  DECLARE counter INT DEFAULT 0;

  -- Loop to insert records
  WHILE counter < 100 DO
    
   INSERT INTO `tb_members` (`member_id`, `unique_code`, `first_name`, `email`, `phone_number`, `profile_img`, `dob`, `address`, `join_date`, `is_delete`, `is_active`, `createdAt`, `updatedAt`, `agent`, `ip`) VALUES (NULL, '0103-19', 'casd', 'test@gmail.com', '23546789', '300x3001.png', '2024-01-04', 'xsacds', '2024-01-11', '0', '1', '2024-01-03 21:04:28', '2024-01-03 21:04:28', 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36', '::1');
    
    SET counter = counter + 1;
  END WHILE;
END //

DELIMITER ;

-- Call the stored procedure to insert records
CALL InsertRecords();

```

## Year /month type

```
SELECT id,event_date,title FROM `tbl_event_details` where (YEAR(event_date)= '2022' ) and (MONTH(event_date) = "12");

```
