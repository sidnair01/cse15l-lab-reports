Sid Nair A16857282 srnair@ucsd.edu

Lab Report 5


To find differences between tests I first ran the script file to write into a results file in different directories using the ```>``` operator:

```[cs15lwi22akp@ieng6-201]:markdown-parse_old:476$ bash script.sh > results.txt```(My group directory)
```[cs15lwi22akp@ieng6-201]:lab-9:475$ bash script.sh > results.txt ```(class directory)


Then I used the diff command to compare the files with and without vim.

```diff lab-9/results.txt markdown-parse_old/results.txt```
```vimdiff lab-9/results.txt markdown-parse_old/results.txt```

Finally, to double check, I did a quick scan of the files manually.

Test 194.md

Our Group: [] Cloned : [url]


Test

Our Group: [] Cloned: [baz]

