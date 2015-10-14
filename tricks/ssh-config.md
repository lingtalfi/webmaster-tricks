Ssh config trick
===================
2015-10-14




Problem
-------------

So instead of typing this:

```bash
ssh 12.34.56.78 -p 2424 -i ~/.ssh/id_dsa_keyone -l lingtalfi 'mysqldump -usketch -pZERj07Fe1 sketch'
```

You want to type this:

```bash
ssh conn1 'mysqldump -usketch -pZERj07Fe1 sketch'
```


Solution
--------------

Create the ~/.ssh/config file if it doesn't exist, and put the following content in it:


    Host conn1
        HostName 12.34.56.78
        User lingtalfi
        IdentityFile ~/.ssh/id_dsa_keyone
        IdentitiesOnly yes
        Port 2424
        
	
	
You can create as many "Host" sections as you want.	


More info: [http://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/](http://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/) 





