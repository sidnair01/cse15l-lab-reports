Sid Nair A16857282 srnair@ucsd.edu

Lab Report 5


To find differences between tests I first ran the script file to write into a results file in different directories using the ```>``` operator:

```[cs15lwi22akp@ieng6-201]:markdown-parse_old:476$ bash script.sh > results.txt```(My group directory)
```[cs15lwi22akp@ieng6-201]:lab-9:475$ bash script.sh > results.txt ```(class directory)


Then I used the ```diff``` command to compare the two results file:


```diff lab-9/results.txt markdown-parse_old/results.txt```(without vim)


```vimdiff lab-9/results.txt markdown-parse_old/results.txt```(with vim)

Finally, to double check, I did a quick scan of the files manually.



Test 194.md

![194.md image](https://i.gyazo.com/17d0d72d5a0ab86999f01be591d5c2cb.png)

Our Group: [] Cloned : [url]



Test 201.md

![201.md image](https://i.gyazo.com/da36179b5956cf7e3c12bdf63f4a1596.png)

Our Group: [] Cloned: [baz]



