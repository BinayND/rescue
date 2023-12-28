
## Ubuntu Server Command





List of package install

```bash
apt list --installed
apt list --installed | grep screen(package name)  // for filter
sudo apt remove package_name

apt install htop  - GUI of task manager

free -h  // check the ram


```
Comman package installation and command

```bash
sudo apt-get install zip unzip
zip -r filname.zip /foldername
unzip filname.zip -d /var/www/html/foldername
cp /source path /destination path  // copy 
rm foldernamecomplete eg .zip // to delete the folder

```

Human readable for size and memory consumpation utility
```bash
du -h /var/www/html/foldername -d 1
du -h --max-depth=1 > diskusage.txt // generate the file on root

```

PHP project server level setting

```bash
path /etc/php/version/apache2/php.ini

php ini
memory_limit = 256M
max_execution_time = 300
post_max_size = 20M
upload_max_filesize = 20M
```

Security headers in .htaccess file
```cmd
<IfModule mod_headers.c>

  # Don't allow any pages to be framed - Defends against CSRF
       Header set X-Frame-Options DENY
  
  # This setting will allow a page to be displayed in frame on the same origin as the page itself
       #Header always append X-Frame-Options SAMEORIGIN
  
  # Turn on IE8-IE9 XSS prevention tools
       Header set X-XSS-Protection "1; mode=block"
  
  # Only allow JavaScript from the same domain to be run.
  
  # Don't allow inline JavaScript to run.
       Header set X-Content-Security-Policy "allow 'self';"
       #Header always set Content-Security-Policy "default-src 'self'; font-src *;img-src * data:; script-src *; style-src *;"
       Header always set Content-Security-Policy "font-src *;img-src * data:;"
  
  # prevent mime based attacks
      Header set X-Content-Type-Options "nosniff"

  # HTTP Strict Transport Security
    Header set Strict-Transport-Security "max-age=31536000" env=HTTPS

  # Referrer-Policy
    Header set Referrer-Policy "strict-origin-when-cross-origin"

  # Feature-Policy / Permissions-Policy

    #Header set Feature-Policy "geolocation 'self'; vibrate 'none'"
    #Header set Permissions-Policy "geolocation 'self'; vibrate 'none'"
    #Header always set Permissions-Policy "geolocation=();midi=();notifications=();push=();sync-xhr=();microphone=();camera=();magnetometer=();gyroscope=();speaker=(self);vibrate=();fullscreen=(self);payment=();"
    
    Header always set Permissions-Policy "fullscreen=(self);camera=();"
  
</IfModule>
```


Email enable in cpanel

```bash
1. in WHM search TweakSetting in Server Configuration
2. In Tweak Setting Page click on the Mail tab
3. Search smtp in Mail tab
4. search for Restrict outgoing SMTP to root, exim, and mailman (FKA SMTP Tweak)
5. change the default on to off
6. Save the new setting
```

Server restart
```bash
sudo systemctl restart apache2

sudo service mysqld start
sudo service mysqld stop

```

Nano Editor command

```bash
crtl + x - exit;
ALT+ a-  to select text.
alt+^ - copy text.
ctrl+u - paste copied text.
ctrl+k - cut text

alt+/ - top
alt+ \ -bottom
go to line no - alt+G 
crtl+ w - find string of data.
```

VIM Editor command

```bash
insert / i - goto editor mode 
esc-  to normal mode back .
hjkl - up/down cursor
w - start word ,b e
colon:w - to write file
press esc
:wq - exit out of file
:q! - whithout saving the file.
:w - written
ZZ -CAPS enable it save exit
s - delete single char
d- line delete
esc - u - undo changes
esc - U / R -redo changes.
0 - start line
& - end of line
gg - to go line.
p - paste the line
:set number will set numbering code line.
:10 - got to line number.
```

[Mysql Command](https://coimbatorewebhosting.com/blog/list-of-all-commands-used-in-mysql-ssh-linux-shell-in-putty/
) 

Script to take complete database backup

```bash
Export :- mysqldump -u username -p databasename > /var/www/html/filename_to_keep.sql
Import :-  mysql -u username -p databaseName < /var/www/html/filename.sql

USER=""
PASSWORD="" 
OUTPUT="/var/www/html/mysql_backup/"

databases=`mysql --user=$USER --password=$PASSWORD -e "SHOW DATABASES;" | tr -d "| " | grep -v Database`

for db in $databases; do
    if [[ "$db" != "information_schema" ]] ; then
        echo "Dumping database: $db"
        mysqldump --force --opt --user=$USER --password=$PASSWORD --databases $db > $OUTPUT/$db.sql
         $OUTPUT/$db.sql
    fi
done
```

[How To Set Up Apache Virtual Hosts on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-20-04)

How to Rewrite URLs with mod_rewrite for Apache on Ubuntu 20.04

```bash
sudo a2enmod rewrite
sudo systemctl restart apache2

sudo nano /etc/apache2/sites-available/000-default.conf

<VirtualHost *:80>
    <Directory /var/www/html>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
    
    . . .
</VirtualHost>
```