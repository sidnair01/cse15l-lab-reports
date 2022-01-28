

![Test 3 Fix](https://i.gyazo.com/968b35c6612e1f296fe7d90f42ea79c4.png)
[Commit Link](https://github.com/sidnair01/markdown-parse/commit/147986a3e3ee678e93a530095fed9f7140c06b4a)

[Test 3](https://sidnair01.github.io/markdown-parse/test-file3.html)

![Image](https://i.gyazo.com/dc125cfebfee4fd08a7c38e0c47973ac.png)

The bug here is that the code ```toReturn.add(markdown.substring(openParen + 1, closeParen))``` lacks any conditional statement. As a result, if openParen and/or closeParen is negative, then the program would be trying to find the index of markdown at -1 which would create an ```java.lang.StringIndexOutOfBoundsException```. This was fixed by adding the statement ```if(openParen!=-1 && closeParen!=-1)``` before the add method, which prevents negative values from entering and therefore keeps the list empty if no parenthesis are found.


The bugs in this version of markdownparse was ```currentIndex = closeParen +1;``` and ```toReturn.add(markdown.substring(openParen + 1, closeParen));```. These pieces of code are problematic because openParen and closeParen would be negative if no parenthesis were found in the test file, which was the case in test-file3.md. If closeParen was negative then ```currentIndex < markdown.length()``` would always remain true and the loop would run infinitely, preventing anything from being displayed on the terminal. This infiniteloop was fixed by changing the code to ```currentIndex +=1```. However, if openParen or closeParen was negative, it would then cause an index out of bounds exception. I solved this by adding the conditional statement ```if(openParen!=-1 && closeParen!=-1)```.





[Test 6](https://sidnair01.github.io/markdown-parse/test-file6.html)

![Imdge](https://i.gyazo.com/8dfa504f45171730196e4223efaa0789.png)
