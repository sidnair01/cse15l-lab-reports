Sid Nair A16857282 srnair@ucsd.edu

Although the tests for my own markdownparse and that for the group I reviewed are within separate files, the code is the exact same. The only difference is the directory I call them in.

Snippet 1 Test:

![Snippet1Test](https://i.gyazo.com/dda181b0178bfd6080bcc963d9bc2d08.png)

Snippet 2 Test:

![Snippet2Test](https://i.gyazo.com/f846b8f462f6c5a9dbe21b120c6c9ddc.png)

Snippet 3 Test:

![Snippet3Test](https://i.gyazo.com/ca39d971c47aa168dbc9bcdef87fed34.png)

Results:

My implementation:

All tests failed

![Myresults](https://i.gyazo.com/294c59c808da913544c2575a7842bfb7.png)


Group I reviewed:

All tests failed

![Othergroupresults](https://i.gyazo.com/a2c5d4faeba0aaa7dda10f0ee89f59b0.png)


The problem is that neither my implementation nor that of the group I reviewed is able to address backticks when searching for valid links.

