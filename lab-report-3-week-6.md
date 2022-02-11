Sid Nair A16857282 srnair@ucsd.edu

#Streamlining ssh Configuration

I'm going to explain the process of how I streamlined my ssh Configuration using the directions from 
Week 5 [Streamlining ssh Configuration](https://ucsd-cse15l-w22.github.io/week/week5/#group-choice-1-streamline-ssh-configuration).

Originally, I would remote ssh into ieng6 using key-based authentication. I followed the template ```ssh username@server```, typing out my specific 
cse15l account username.



![previous ssh image]()

Before predefining my configuration settings, typing ```ssh ieng6``` was unrecognized and prompted me for a password.

![requires password]()

The first step to making this work was moving into my ```.ssh``` folder under the path ```C:\Users\sidna\.ssh```.
After checking and making sure there wasn't a previous config file within the directory, I opened a new Notepad file form the start menu.

![opening new notepad]()

I typed this command into the file and saved it as ```config.txt```, since notepad wanted to store it as a text file.

```Host ieng6
	   HostName ieng6.ucsd.edu
	  User cs15lwi22akp
	  IdentityFile ~/.ssh/id_ed25519_cs15l```
    

This first two lines of code in the block defines the variable ```ieng6```, which represents the server ieng6.ucsd.edu. The third line specifies my username, and 
the fourth specifies the path of the ssh key.

![config.txt]()
  
  
  After saving the file into my directory, I renamed the file to just ```config``` which changed the type of the file from a textfile to a file.
  
 ![config]()
 
 I now tried running ```ssh ieng6``` and was able to successfully connect to the server using the shortcut.
 
 I then typed ```scp hello.java ieng6``` which successfully transfered the file onto the server.
  
