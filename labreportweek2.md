The objective of our first lab was to remotely access and modify files on UCSD campus-machines from one personal computer.

*Installing VSCode*

Download the correct VSCode installer for your operating system. This should open an empty page where new files can be created and written in any language.

![Image](https://i.gyazo.com/1b658b1e105963ab1d3ca846d61353df.png)

*Remotely Connecting*

The first step to remotely connecting is instaling an SSH program, for example, OpenSSH for Windows.
Then create a new terminal in VSCode and type ```ssh cs15lwi22zz@ieng6.ucsd.edu```, replacing ```zz``` with the phrase associated with your student ETS account, and entering the password associated with such ETS account. If you don't know your ETS account, visit this [Link](https://sdacs.ucsd.edu/~icc/index.php) and enter your username and student ID number, and change your password if necessary. 

![Image](https://i.gyazo.com/6ebe06beeb7c622d365c6cb6c4b9cd99.png)

*Trying some Commands*

After connecting to the machine, try these commands and ensure they work as they should.

1. ```ls``` lists all public files
2. ```ls -a``` lists all files in a directory
3. ```pwd``` lists the current directory
4. ```cd <directory>``` changes path to the speciifed directory

![Image](https://i.gyazo.com/635f21d971149ccfd4a9bfde88217047.png)

*Moving Files with* ```scp```

Move into the directory on the client computer containing the file. Then type:
```scp <filename> cs15lwi22zz@ieng6.csd.edu:~/``` 
(remembering to replace ```zz``` with your personal phrase).
Certain statistics should be displayed such as the file name, copy percetange complete, filesize, download speed, and time.

![Image](https://i.gyazo.com/2e7a8b278f7fee8890c01cd8eb285589.png)

*Setting an SSH Key*

Type ```ssh-keygen``` onto the client computer. This will create a private and public key pair within the directory ```Users/<your user>/.ssh/id_rsa``` by default, and ask you to set an optional passphrase.
Change to this directory on your client computer and use the ```scp``` command described before to copy the public key file to the specified directory on the server.
```scp id_rsa.pub cs15lwi22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys```
Once this is saved the server containing the public key will automatically recognize the client containing the private key and will allow connection without a password requirement.
![Image](https://i.gyazo.com/a60598dadd98218b4d982e11f17ce019.png)

*Optimizing Remote Running*

To run commands while connecting to the server, including further commands on the same line in quotes.
![Image](https://i.gyazo.com/ea9fd31542ee332dda199e35a18bd718.png)

To allow multiple commands to be run on a single line, separate them with a semicolon.
![Image](https://i.gyazo.com/aa02decb75b8a06c1cd78a564c49cdf9.png)
In this example the ```WhereAmI.java``` file is being called on both the client and server simultaneously.

Running commands from client to server can be sped up if the amount of terminal requests is reduced.
Shortening our commands to fit onto fewer lines both simplifies and speeds up the process.
