# syslib
# System Librarianship

## Notes for System Librarianship

### The Beginning

1 This is rough.  
2 You've hade to delete the first trys.  
3 Cross your fingers this works better!  

### Trial and Error 

Wow! You made a whole new markdown file.
Now you need to remember the commands!
Oof! That's not easy!
Practice! Practice! Practice!

### Git and GitHub

**COMMANDS**

Since I can't seem to remember these commands
I am dropping them here to find easily!

Track changes with
>git add .

Commit changes and add message with:
>git commit -m "add message in quotes"

Push Changes to remote repo with:
>git push origin main

Pull changes to sync those made on GitHub with:
>git pull origin main


### Apache 2 

Apache 2 install worked great!
Loads of info here. Not sure how I am going to retain it all.
Maybe some sub directories are in order....

Note:
1. Use cd /var/www/html to work on on apache
2. At least I think so.

### MYSQL

Typing is extremely important. 
Like your favorite English teacher, 
MYSQL doesn't like incomplete sentences.
**Don't** forget the semicolon!

I do not recommend trying this when tired!


**COMMANDS**

**Logging In**

> mysql -u opacuser -p

-p (asks for password)
-u (indicates user name?)(check on this!)

help is "\h"
clear input is "\c"
quit is "\q"
clear screen is "ctrl l"

>use opacdb

**Table Commmands**
select title from *database name* where title not like '%e';
This selects titles that don't end in "e".

>alter table *database name*
>add publisher varchar(75) after title;

example: update books set publisher='Knopf' where id='4';

**selecting items from database to be shown**
>select * from *database name*
this selects all

>select author, publisher
    -> from *database name*
    -> where copyright < '2011-01-01';
> select author from books order by copyright;


**examples of updating**
> delete from books where author='Julia Phillips';
> insert into books
    -> (author, title, publisher, copyright) values
    -> ('Emma Donoghue', 'Room', 'Little, Brown \& Company', '2010-08-06'),

Ok, so you need to remember to select database
> use opacdb;

So, funny story, I got the search to work. It worked great!
Except... It couldn't return to the search screen.
What!!!!
Look, look some more, look a lot!
Seriously what is **WRONG**?
Paste the link... works just peachy.
*SIGH*
I feel like Dory...
*"Just keep looking, looking, looking"*
*"Just keep looking, looking, looking"*
Wait a minute.
Compare copied link to link on search page.
**OMG** I typed the web address wrong in the *.html* file!
Yes, brilliant that I am... I kept typing a *5* instead of a *4*!
But instead of dwelling on it...
I'm going to **pat myself on the back** for finding it and
not having to ask for help!
You go girl! :)

### Cataloging Page with our Bare Bones OPAC

Not bad at all.
Seemed to go pretty smoothly.
**Except**, weirdly, the URL to return to the entry page
is not shown correctly.  WHAT!!!!

**BUT IT WORKS!**

Yes, I went back to the insert.php file,
and yep, that's my URL.
IDK why, but it works! **WEIRD!!**

I even tried a different browser. Yep, Still works!

My other question I will ask Dr. Burns,
*"Why doesn't it ask you for your password
every time you open it."*
No, I did not save the password.

Got it. Thanks Dr. Burns

### OMEKA ###

1)sudo apt install imagemagick
2) sudo a2enmod rewrite
3) sudo systemctl restart apache2
4) sudo systemctl restart mysql
5) I **KNOW**  I'm missing stuff!
6) cd /var/www/html
7) sudo wget https://github.com/omeka/Omeka/releases/download/v3.1/omeka-3.1.zip
8) ls

9) sudo unzip omeka-3.1.zip
wait, no, I've got to download that...   
10) sudo apt install unzip

ok now unzip. GREAT!

11) cp omeka-3.1 omeka
No? hmm... wait, it's a direcctory?!?!?!
try mv omeka-3.1 omeka
gotta add sudo!!!!

12) cd omeka
13) sudo nano -l db.ini
ok go refresh your memory as to what goes here....

Add  
define('FS_METHOD','direct');
to bootstrap.php?

14) sudo chown -R www-data;www-data *

15) restart apache2 and mysql

Not working... will dig deeper, in a bit.

OK I'm back.
need to reboot and install some updates

So, after searching my files and going back and forth in the previous chapters directions
I think I've got it figured out.

16)cd omeka
17)sudo nano -l db.ini 
(localhost, omekauser, pswd - super secret, omekadb)

18 & 19) restart apache 2 and mysql

I'm gonna try it.  I think I forgot to document something, but IDK.

**SUCCESS!**
*I really, really, thought it would take longer to figure out what I left out. 
Especially since I apparently didn't document the last couple sections. 
May need to do an after the fact edit.*

Set up admin page and ready to populate!
Wish me luck!
















