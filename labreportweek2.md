The objective of our first lab was to remote access and modify files on UCSD campus-machines remotely.

*Installing VSCode*

Download the correct VSCode installer for your operating system. This should open an empty page where new files can be created and written in any language.

![Image](https://i.gyazo.com/1b658b1e105963ab1d3ca846d61353df.png)

*Remotely Connecting*

The first step to remotely connecting is instaling an SSH program, for example, OpenSSH for Windows.
Then create a new terminal in VSCode and type ```ssh cs15lwi22zz@ieng6.ucsd.edu```, replacing ```zz``` with the phrase associated with your student ETS account, and entering the password associated with such ETS account. If you don't know your ETS account, visit this [Link](https://sdacs.ucsd.edu/~icc/index.php) and enter your username and student ID number, and change your password if necessary. 

![Image](https://i.gyazo.com/253bfd51dbbf43fc1238576e6df76d6f.png)

*Trying some Commands*

After connecting to the machine, try these commands and make sure they work as they should

1. ```ls``` lists all public files
2. ```ls -a``` lists all files in a directory
3. ```pwd``` lists the current directory
4. ```cd <directory>``` changes path to the speciifed directory

![Image](https://i.gyazo.com/635f21d971149ccfd4a9bfde88217047.png)

*Moving Files with* ```scp```

To move a file from a certain path on client computer to the server, the ```scp``` command is used.
Make sure to move into the directory containing the file you want to transfer. Then type:

```scp <filename> cs15lwi22zz@ieng6.csd.edu:~/``` into the terminal, once again replacing ```zz``` with your personal phrase. Certain statistics should be displayed such as the file name, copy percetange complete, filesize, download speed, and time.

![Image](https://i.gyazo.com/2e7a8b278f7fee8890c01cd8eb285589.png)

*Setting an SSH Key*



*Optimizing Remote Running*
