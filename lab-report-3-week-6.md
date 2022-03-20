Sid Nair 	A16857282 	srnair@ucsd.edu

# Streamlining ssh Configuration

### Before Streamlining :(

I'm going to explain the process of how I streamlined my ssh Configuration using the directions from 
Week 5 [Streamline ssh Configuration](https://ucsd-cse15l-w22.github.io/week/week5/#group-choice-1-streamline-ssh-configuration).

Originally, I would remote ssh into ieng6 using key-based authentication. I followed the template ```ssh username@server```, typing out my specific 
cse15l account username.

![previous ssh image](https://i.gyazo.com/9e25c68719484d6dbc2d37dedbd05b3f.png)

To transfer files I used the template ```scp filename username@server```.

![previous scp image](https://i.gyazo.com/e9aea6624d76a6b4975499a8fbd82320.png)

### Streamlined SSH

Before predefining my configuration settings, typing ```ssh ieng6``` was unrecognized and prompted me for a password.

![requires password](https://i.gyazo.com/076ac507636bb3ff3b765da49d8c1586.png)

First I moved into the ```.ssh``` folder, which for me was under the path ```C:\Users\sidna\.ssh```.
After checking and making sure there wasn't a previous config file within the directory, I opened a new Notepad file (most editors will be fine) and typed the following command.

![config file](https://i.gyazo.com/b03726eed617444ab6bad756a5ad44bc.png)

This first two lines of code in the block define the variable ```ieng6```, which represents the server ```ieng6.ucsd.edu```. The third line specifies my username, and 
the fourth specifies the path of the ssh key.

I saved the file as ```config.txt```, since notepad wanted to store it as a text file.

![config.txt](https://i.gyazo.com/46852ff03280968b0372eaa4db4e95e8.png)
  
  
After saving the file into my directory, I renamed the file to just ```config``` which changed the type of the file from a textfile to a file.
  
![config](https://i.gyazo.com/0e75d48f0a2ff6ba63a673813ac6b24f.png)
 
I now tried running ```ssh ieng6``` and was able to successfully connect to the server using the shortcut.

![ssh ieng6](https://i.gyazo.com/1a5f05489f6ad49f032a812809016b0b.png)

### Streamlined SCP

I then created a basic program named ```MyJavaFile.java``` with the code below:

```
class MyJavaFile{
    public static void main(String[] args){
        System.out.println("Congrats, you did it!");
    }
}
```
 
I changed directories to ```\CSE15L\GitHub\cse15l-lab-reports``` which contained the file. Using the shortcut enabled through the config file, I typed ```scp MyJavaFile.java ieng6:~/``` to transfer the program onto the server.

![scp ieng6](https://i.gyazo.com/917897bd0fe5b0098adc696d1d56c43d.png)

I connected to the server and ran ```ls```, ```javac MyJavaFile.java```, and ```java MyJavafile``` to ensure the program is present and working on the server.

![testing scp](https://i.gyazo.com/319bde8dde27b136b881e7acb5af8990.png)

  
