

![Test 3 Fix](https://i.gyazo.com/968b35c6612e1f296fe7d90f42ea79c4.png)
[Commit Link](https://github.com/sidnair01/markdown-parse/commit/147986a3e3ee678e93a530095fed9f7140c06b4a)

[Test 3](https://sidnair01.github.io/markdown-parse/test-file3.html)

![Test 3 Error](https://i.gyazo.com/dc125cfebfee4fd08a7c38e0c47973ac.png)

The bug here is that the code ```toReturn.add(markdown.substring(openParen + 1, closeParen))``` lacks any conditional statement. As a result, if openParen and/or closeParen is negative, then the program would be trying to find the index of markdown at -1 which would create an ```java.lang.StringIndexOutOfBoundsException```. This was fixed by adding the statement ```if(openParen!=-1 && closeParen!=-1)``` before the add method, which prevents negative values from entering and therefore keeps the list empty if no parenthesis are found.



![Test 4 Fix](https://i.gyazo.com/e7e4b34d15873eea5421cf35ca08c1f5.png)
[Commit Link](https://github.com/sidnair01/markdown-parse/commit/559ea537034629fc4f4260a6340c919cd925551b)

[Test 4](https://sidnair01.github.io/markdown-parse/test-file4.html)

![Test 4 Error](https://i.gyazo.com/43e8434c972415d8ae6712fb1302b082.png)

The bug here is the code ```currentIndex = closeParen +1;```. This is problematic because ```closeParen``` will be equal to -1 if no closed parenthesis is found in the file, which is the case in test-file4. Therefore, the adding 1 to ```closeParen``` means we are setting ```currentIndex``` equal to 0. Therefore, ```currentIndex < markdown.length()``` will always remain true and the while loop will run infinitely, preventing any output from being displayd on the terminal. This was fixed by moving the statement ```currentIndex = closeParen +1;``` underneath the conditional statement ```if(openParen!=-1 && closeParen!=-1)```, which filters out negative values. Then write the statement ```else{currentIndex+=1;}``` which runs if there are no parenthesis in the file.



![Test 6 Fix]()
[Commit Link]()


[Test 6](https://sidnair01.github.io/markdown-parse/test-file6.html)

![Test 6 Error](https://i.gyazo.com/8dfa504f45171730196e4223efaa0789.png)
