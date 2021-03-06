
# Lab Report 2

> Siddhartha Nair   A16857282   srnair@ucsd.edu

![Test 3 Fix](https://i.gyazo.com/968b35c6612e1f296fe7d90f42ea79c4.png)

[Commit Link](https://github.com/sidnair01/markdown-parse/commit/147986a3e3ee678e93a530095fed9f7140c06b4a)

[Test 3](https://sidnair01.github.io/markdown-parse/test-file3.html)

![Test 3 Error](https://i.gyazo.com/dc125cfebfee4fd08a7c38e0c47973ac.png)

The bug here is that the code ```toReturn.add(markdown.substring(openParen + 1, closeParen))``` lacks any conditional statement. As a result, if ```openParen``` and/or ```closeParen``` is negative, the program would try to find the index of markdown at -1 which would create an ```java.lang.StringIndexOutOfBoundsException```. This was fixed by adding the statement ```if(openParen!=-1 && closeParen!=-1)``` before the add method, which prevents negative values from entering and therefore keeping the list empty if no parenthesis are found.



![Test 4 Fix](https://i.gyazo.com/e7e4b34d15873eea5421cf35ca08c1f5.png)

[Commit Link](https://github.com/sidnair01/markdown-parse/commit/559ea537034629fc4f4260a6340c919cd925551b)

^Not the exact commit but right before

[Test 4](https://sidnair01.github.io/markdown-parse/test-file4.html)

![Test 4 Error](https://i.gyazo.com/43e8434c972415d8ae6712fb1302b082.png)

The bug here is the code ```currentIndex = closeParen +1;```. This is problematic because ```closeParen``` will be equal to -1 if no closed parenthesis is found in the file, which is the case in test-file4. Therefore, the adding 1 to ```closeParen``` means we are setting ```currentIndex``` equal to 0. Therefore, ```currentIndex < markdown.length()``` will always remain true and the while loop will run infinitely, preventing any output from being displayed on the terminal. This was fixed by moving the statement ```currentIndex = closeParen +1;``` underneath the conditional statement ```if(openParen!=-1 && closeParen!=-1)```, which filters out negative values. Then write the statement ```else{currentIndex+=1;}``` which runs if there are no parenthesis in the file.



![Test 6 Fix](https://i.gyazo.com/1ac365d4b6cc5baebfa4863dd3d647d0.png)

[Commit Link](https://github.com/sidnair01/markdown-parse/commit/8624b3128767922b0e65ccc5724bb4107ba01a69)


[Test 6](https://sidnair01.github.io/markdown-parse/test-file6.html)

![Test 6 Error](https://i.gyazo.com/8dfa504f45171730196e4223efaa0789.png)

The bug here is that there is no conditional statement that checks for an exclamation point before the brackets. The only difference between a link and image declaration is that exclamation point. To prevent images from being added to the list of links, we added the conditional statement ```if(nextOpenBracket!=-1 && markdown.charAt(nextOpenBracket-1)=='!'``` to check if the brackets are refering to an image. If the program has found a valid image, the code ```currentIndex = nextcloseBracket + 1``` is run to continue searching for links. Also added more requirements such as ```nextOpenBracket!=-1 && nextCloseBracket!=-1 && openParen-nextCloseBracket==1``` within the link conditional statement to make sure that both the brackets and parenthesis exist and that the parenthesis come directly after the brackets.
