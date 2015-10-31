Make command system wide available
======================================
2015-10-31



On Unix.

To execute a program via a terminal, suffices to type its full path.
However, the full path to a program can be hard to remember and to type it on the terminal takes some time,
depending on the length of your path.

It would be much easier to simply type the name of the program you want to use.

Fortunately, this is not hard to do.
You basically just need to put your program where it can be found by the shell, in other words you need to put
it in your PATH.




1. First, check out what your path is using the following command.

```bash
echo $PATH | tr ':' '\n'
```


2. Now, you can move/copy your program in any of the location defined in your PATH.
You can also add your own locations to the PATH, for instance if you want to create a ~/bin directory 
and put your programs there, you can.

There are different ways to customize the PATH.
On Mac, there is the /etc/paths file.
On Unixes, you can add the following line:

```bash
export PATH="/path/to/my/directory:$PATH"
```

in your ~/.bashrc


Once the program is in your PATH, you can just type its name.
Therefore, it might be a good idea to get rid of the file extension of your program.
For instance, if your program is named myprogram.sh, you should rename it myprogram.
  
