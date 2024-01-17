
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

``
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
