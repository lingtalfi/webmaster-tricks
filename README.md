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
-----------

### ssh config trick 

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
    
This is also a huge time saver if you spend a lot of time typing commands in a shell.<br>
Unfortunately, this tip is only for mac users.<br>

Basically it allows you to navigate the command line intuitively, like you do editing in an IDE for instance, 
rather than using weird shortcuts. For instance, to move to the previous word, simply type alt+left (so much time
saved in the long run).


Read the [full trick here](https://github.com/lingtalfi/mac-terminal-shortcuts)

    
