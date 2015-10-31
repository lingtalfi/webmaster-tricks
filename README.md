Webmaster tricks
=======================
2015-10-14





Hello.
In this document, you'll find some general webmaster tricks that I use.
The general theme is always to be as most efficient as possible at a given task.



Audience
---------------

I've just noticed that when someone tries to explain something, the audience has to be someone like him.
By that I mean that you cannot discuss something you know nothing about, and therefore if I explain my tricks here,
the audience has to be like me, more or less.
(so who ami I?)


The perfect audience here is a webmaster with a few clients (client=website), and a dedicated server.
The websites are not big (it's not ebay.com or big sites like those),
but some of them are dynamic and have their small communities (people can post things, you should know what 
I am talking about).

Because traffic is not so high, I won't talk about clustered machines, which by the way I know nothing about.

So what's left to discuss?

Small and convenient tools that ease the transferring of data from the localhost to a remote server for instance,
or other stuff that a webmaster will need at some point of this webmaster life.

So now you should know whether or not this document might be worth reading.




Tricks
================


Productivity Tricks
-------------------------

This section contains tricks about being more efficient in typing commands, and about you being generally
faster, or better organized.


### ssh config trick 

2015-10-14

Not really a trick, just a native feature of ssh, but the net effect is that it reduces a ssh command like this:
    
```bash
ssh 12.34.56.78 -p 2424 -i ~/.ssh/id_dsa_keyone -l lingtalfi 'mysqldump -usketch -pZERj07Fe1 sketch'
```
    
    
to this:


```bash
ssh conn1 'mysqldump -usketch -pZERj07Fe1 sketch'
```

and is more convenient than aliases in my opinion.
I found it recently and thought it might be worth sharing.
Read the [full trick](https://github.com/lingtalfi/webmaster-tricks/blob/master/tricks/ssh-config.md)
here.
    
    
### Navigate the command line like an editor
    
2015-10-14
    
This is also a huge time saver if you spend a lot of time typing commands in a shell.<br>
Unfortunately, this tip is only for mac users.<br>

Basically it allows you to navigate the command line intuitively, like you do editing in an IDE for instance, 
rather than using weird shortcuts. For instance, to move to the previous word, simply type alt+left (so much time
saved in the long run).


Read the [full trick here](https://github.com/lingtalfi/mac-terminal-shortcuts)

    
Statistics Tricks
----------------------
    
This section contains tricks related to statistics.    
    
    
### Pick'n'treat

2015-10-15
    
This trick is about quickly grabbing information from the user, and treat them in a second phase.
Therefore, the user feels (almost) no performance penalty, and you have the data that you want for your later analysis.
 

Read the [full trick here](https://github.com/lingtalfi/webmaster-tricks/blob/master/tricks/pick-n-treat.md)

    
    
    
Front End Application Tricks
----------------------------
    
This section contains tricks related to one's application or/and website.
    
    
### Handle Sitemaps

2015-10-18
    
Handling sitemap in a php application is a common task.
There are plenty of scripts on the web.
Here are the two that I use:
     
- [Sitemap Builder](https://github.com/lingtalfi/SitemapBuilderBox): create simple sitemaps with php oop (handles google video extension and more)
- [Sitemap Slicer](https://github.com/lingtalfi/SitemapSlicer): synchronize your sitemaps from your database (handles sitemap index)

    
        
    
### Php Error Log

2015-10-19
    
    
In php, you can use the ini_set('error_log', '/path/to/myapp/logs/applog.txt') directive to control where
your php errors are going. But now you have two problems:

- how do you rotate the applog.txt file?
- how do you send yourself an email whenever the applog.txt file is updated?
 
There are two lightweight bash scripts which are perfect for this situation.

- [log rotator](https://github.com/lingtalfi/logrotator): rotates any file
- [log change notify](https://github.com/lingtalfi/log-change-notify): a script that allows us to execute hooks
    whenever the log file is updated. Hooks can be written in php.

Both scripts are based on cron.
My cron setup is so that it launches the log rotator script every day, and the log change notify script every minute.



#### Writing to log file 

2015-10-25

Now if you are more concerned with how to write to a log file, there are two classes that might help you:

- [ApplicationLog](https://github.com/lingtalfi/ApplicationLog): a simple class that logs all your application log messages to one file
- [QuickLog](https://github.com/lingtalfi/QuickLog): a simple class like ApplicationLog, but you can write different messages on different files

Actually, I've been using both of them together, and they play nice together.
I use ApplicationLog to collect every log message from my application, plus php's error_log.
Therefore, all my application logs go to ONE and one only location, which is very appreciable.

On the other hand, sometimes I need to collect data from the users, for instance what expressions they typed in 
a search engine on the website. In this case, I find that the QuickLog is more appropriated, because I can create a search.txt
log file on the fly and put all the users searches in it, without messing with my application log.





### Resizing images, Renaming files

2015-10-22

From time to time, webmasters need to resize an image.
Maybe the fastest way to do so is to use the image magick commands directly.
However, one may not always remember the syntax.
An alternative to this is to use the webWizard's [batchFileTreatment tasks](https://github.com/lingtalfi/webmaster-wizard/blob/master/doc/tasks-description.md#batch-file-tasks-12).
Once setup, this tool works fine not only for resizing a directory of images, but also for renaming files.

The kool thing about the [webwizard](https://github.com/lingtalfi/webmaster-wizard) tool is that it's extensible, and if you start to use it, 
it boosts your productivity in different areas of your work.



Local Remote Transfer Tricks
--------------------------------
    
### Quickly transfer local database to remote server and vice versa

2015-10-22

If you own a remote webserver with some web applications on it, and if at least one of your application
uses a database, then at some point you need to think how you will sync your local app with your remote app.

If you don't have a workflow for that, or if you're just curious, you might be interested by the 
web wizard's [database save apply tasks](https://github.com/lingtalfi/webmaster-wizard/blob/master/doc/tasks-description.md#database-tasks-save-apply-11).

They basically allow you to execute any basic backup operation in a matter of seconds (as it is always the case with command line tools).
So, you can backup your local database, mirror it into your remote server, and vice versa, and more.

The [webwizard](https://github.com/lingtalfi/webmaster-wizard) tool has even more power to offer, but the database tasks are one of the main reason
it was created in the first place.
    
   
   
   
Bash tricks
---------------
   
### How to make any command system wide available

2015-10-31   

Rather than typing the full path to a command, you can simply type its name, which is much easier to remember.

Everybody should know that.
But anyway, you can find the explanation on how to do that [here](https://github.com/lingtalfi/webmaster-tricks/blob/master/tricks/bash.make-command-system-wide-available.md).






