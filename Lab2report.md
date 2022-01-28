

![Test 3 Fix](https://i.gyazo.com/507c5b6cf6e0c6851f520f20a45cf407.png)
[Commit Link](https://github.com/sidnair01/markdown-parse/commit/a9fe78a5801e5c5fcc7492e8caee876a54a5983e)

[Test 3](https://sidnair01.github.io/markdown-parse/test-file3.html)

![Image](https://i.gyazo.com/ae4b1881d5a4e6a09cbbfeae3dabdf9d.png)

The bugs in this version of markdownparse was ```currentIndex = closeParen +1;``` and ```toReturn.add(markdown.substring(openParen + 1, closeParen));```. These pieces of code are problematic because openParen and closeParen would be negative if no parenthesis were found in the test file, which was the case in test-file3.md. If closeParen was negative then ```currentIndex < markdown.length()``` would always remain true and the loop would run infinitely, preventing anything from being displayed on the terminal. This infiniteloop was fixed by changing the code to ```currentIndex +=1```. However, if openParen or closeParen was negative, it would then cause an index out of bounds exception. I solved this by adding the conditional statement ```if(openParen!=-1 && closeParen!=-1)```.





[Test 6](https://sidnair01.github.io/markdown-parse/test-file6.html)

![Imdge](https://i.gyazo.com/8dfa504f45171730196e4223efaa0789.png)
