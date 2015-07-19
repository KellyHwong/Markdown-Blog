tag: Note, Python
#Noting Double Line End
In python, when there is a file handler variable, and when we use it to readlines, like this:
```python
fh = open('words.txt')
for line in fh.readlines():
    print line.upper()
```
The *readlines* method will read one line of the text file(this means from start to the first '\n' or '\r\n') when it was called at one time. **And**, this line end('\n' or '\r\n') will be convert into '\n' in python, and **will
be included in that returned string!**
As for the *print* method, I want to talk about C++ first.
As we know, if we want to print some a string **with a linefeed**, we will code like this:
```c
cout << "Some a string" << endl;
```
But, in python, actually the *print* method will not only print the string you input into it, **but also an extra linefeed**.
When you code this:
```python
print 'a'
print 'b'
print 'c'
```
The output on the screen won't be "abc"(without any linefeeds), but "a" with a linefeed and "b" with a linefeed and " c" with a linefeed.
You guys can try it yourself :-).
So come back to our problem. If we want to print the content of a text file as it is in the file. We should code like this:
```python
fh = open('words.txt')
for line in fh.readlines():
    line_strip = line.strip('\n')
    print line_strip.upper()
```
  Strip that '\n' input into the *line* variable, and the *print* method will add another '\n' for you. That's why we do this *strip* operation.
  So guys, do you catch my idea :-).
