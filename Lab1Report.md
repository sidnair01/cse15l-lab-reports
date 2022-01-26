The objective of our first lab was to remotely access and modify files on UCSD campus-machines from one personal computer.

#Installing VSCode

If not done already, install the correct version of VSCode for your operating system through this [Link]( https://code.visualstudio.com/). Follow the instructions and once finished, start the program, which should open an empty page.

![Image](https://i.gyazo.com/d0a170818e2ec5385168fb1b63872fc9.png)

New files and terminals can be created from the toolbar above.

#Remotely Connecting

The first step to remotely connecting is installing an SSH program, for example, OpenSSH for Windows.
Then create a new terminal in VSCode and type ```ssh cs15lwi22zz@ieng6.ucsd.edu```, replacing ```zz``` with the phrase associated with your student ETS account, and entering the password associated with such ETS account. If you don't know your ETS account, visit this [Link](https://sdacs.ucsd.edu/~icc/index.php) and enter your username and student ID number, and change your password if necessary. 

![Image](https://i.gyazo.com/6ebe06beeb7c622d365c6cb6c4b9cd99.png)

When you first connect to the server, type 'yes' to the initial question.

#Trying some Commands

After connecting to the machine, try these commands and ensure they work as they should.

1. ```ls``` lists all public files
2. ```ls -a``` lists all files in a directory
3. ```pwd``` lists the current directory
4. ```cd <directory>``` changes path to the speciifed directory

![Image](https://i.gyazo.com/635f21d971149ccfd4a9bfde88217047.png)

#Moving Files with ```scp```

Move into the directory on the client computer containing the file. Then type:
```scp <filename> cs15lwi22zz@ieng6.csd.edu:~/<directory>``` 
(remembering to replace ```zz``` with your personal phrase).
Specify the filename before the server, and specify the server directory at the end.
If it works, certain statistics should be displayed such as the file name, copy percetange complete, filesize, download speed, and time.

![Image](https://i.gyazo.com/2e7a8b278f7fee8890c01cd8eb285589.png)

![Image](https://i.gyazo.com/80e538d3c85971f26a5979158aa6f6b4.png)
The file should appear in the server directory as so.

#Setting an SSH Key

Type ```ssh-keygen``` onto the client computer. This will create a private and public key pair within the directory ```Users/<your user>/.ssh/id_rsa``` by default, and ask you to set an optional passphrase.
![Image](https://i.gyazo.com/aba796d7b1be73dea8fcfb736c84bf87.png)

Extra steps for Windows users can be found through this [Link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

![Image](https://i.gyazo.com/bf1828a95de3812762ccafb16884cc0d.png)

Within an administrator prompt, use the commands ```ssh-add <path of key>``` to add the key files into the ssh-agent, and ```mkdir C:\Users\username\.ssh\``` to create a folder to hold the public key.

Use the ```scp``` command described before to copy the public key file to this directory on the server.
```scp /Users/<your user>/.ssh/id_rsa.pub cs15lwi22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys```

Once saved, the server containing the public key will automatically recognize the client containing the private key. Therefore, the server will allow connection from the client without a password.
![Image](https://i.gyazo.com/a60598dadd98218b4d982e11f17ce019.png)

#Optimizing Remote Running

To run certain commands while connecting to the server, include them on the same line in quotes.
![Image](https://i.gyazo.com/ea9fd31542ee332dda199e35a18bd718.png)

To allow multiple commands to be run on a single line, separate them with a semicolon.
![Image](https://i.gyazo.com/aa02decb75b8a06c1cd78a564c49cdf9.png)
In this example the ```WhereAmI.java``` file is being called on both the client and server simultaneously.

Running commands from client to server can be sped up if the amount of terminal requests is reduced.
Using methods like these to fit our commands onto fewer lines both simplifies and speeds up the process.
