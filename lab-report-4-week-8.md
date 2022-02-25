Sid Nair A16857282 srnair@ucsd.edu

# Lab Report 4

[My Repository](https://github.com/sidnair01/markdown-parse.git)

[Can't find this yet]()

Although the tests for my own markdownparse and that for the group I reviewed are within separate files, the code is the exact same. The only difference is the directory I call them in.

## Tests

### Snippet 1 Test

![Snippet1Test](https://i.gyazo.com/dda181b0178bfd6080bcc963d9bc2d08.png)


### Snippet 2 Test

![Snippet2Test](https://i.gyazo.com/f846b8f462f6c5a9dbe21b120c6c9ddc.png)


### Snippet 3 Test

![Snippet3Test](https://i.gyazo.com/ca39d971c47aa168dbc9bcdef87fed34.png)



## Results

### My Implementation

![Myresults](https://i.gyazo.com/294c59c808da913544c2575a7842bfb7.png)

> All tests failed



### Other Group Implementation

![Othergroupresults](https://i.gyazo.com/a2c5d4faeba0aaa7dda10f0ee89f59b0.png)

> All tests failed


The problem is that neither my implementation nor that of the group I reviewed is able to address backticks, nested brackets/parentheses, or new lines when searching for valid links.



Q1:
To my knowledge I do not think it is possible to account for all cases of backticks within a reasonable code length (~10 lines). I was able to fix the case of ```url.com``` incorrectly showing up by adding the following argument to my conditional statement: ```markdown.charAt(nextOpenBracket-1) != '`'```, which checks if the character befroe the openbracket is a backtick and then invalidating the link. However, this is completely flawed because if a pair of backticks near the bracket was present it would throw off the link, and trying to account for all cases of backticks seems too large of a challenge to handle(for me at least).

Q2:
I think it would be possible to account for nested pairs of parentheses, brackets, and escaped brackets through the use of a stack. If an initial openbracket was found then a stack would be initialized. A for loop could start and would push any future open parentheses or brackets to the stack. If it ran into a closed parenthesis or bracket and it matched the top of the stack it would pop the stack. If the stack is empty and a closed bracket is found that signifies the end of the link name. However, I don't think this would be possible within a reasonable code length.

Q3:
I'm not exactly sure if this is possible, but once markdownparse determines that open and close brackets exist, it could set a variable equal to the substring between those two indexes of markdown and search for new lines. If it finds a new line then the link is invalidated. It would also continue this search between the open and closed parentheses. I believe this would be possible within a reasonable length assuming it's possible to search for new lines.

