### Sid Nair A16857282 srnair@ucsd.edu

# Lab Report 5


I first ran the script bash file with the ```>``` command to write the results of each test into a file called ```results.txt```:

```[cs15lwi22akp@ieng6-201]:markdown-parse_old:476$ bash script.sh > results.txt```(My group directory)
```[cs15lwi22akp@ieng6-201]:lab-9:475$ bash script.sh > results.txt ```(class directory)


Then I used the ```diff``` command to compare the two results file:


```diff lab-9/results.txt markdown-parse_old/results.txt```(without vim)


```vimdiff lab-9/results.txt markdown-parse_old/results.txt```(with vim)

Finally, to double check, I did a quick scan of the files manually.



### Test 194.md

![194.md image](https://i.gyazo.com/17d0d72d5a0ab86999f01be591d5c2cb.png)

> Results

Expected: []

My Group Directory: []

Cloned Directory: [url]


The implementation my group has is corrected in this situation because 194.md does not contain any parsable links. The cloned directory seems to have issues dealing with spaces and/or characters between the parsable brackets and parentheses.

> Bug

![194 bug](https://i.gyazo.com/ab115344ba97b90a7c8cdbbaff1045a6.png)

The cloned MarkdownParse lacks code to check for text in between the closed bracket and open parenthesis. Therefore, it adds invalid links to the list.

Adding a simple conditional statement such as ```if (openParen == nextCloseBracket +1)```to check if the open parentheses comes directly after the closed bracket would help.






### Test 201.md

![201.md image](https://i.gyazo.com/da36179b5956cf7e3c12bdf63f4a1596.png)

> Results

Expected: []

My Group Directory: []

Cloned Directory: [baz]


The implementation my group has is corrected in this situation because 201.md does not contain any parsable links. The cloned directory seems to have issues dealing with spaces and/or characters between the parsable brackets and parentheses.

>Bug 

![201 bug](https://i.gyazo.com/ab115344ba97b90a7c8cdbbaff1045a6.png)

The cloned MarkdownParse lacks code to check for text in between the closed bracket and open parenthesis. Therefore, it adds invalid links to the list.

Adding a simple conditional statement such as ```if (openParen == nextCloseBracket +1)```to check if the open parentheses comes directly after the closed bracket would help.

