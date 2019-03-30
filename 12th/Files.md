
# Chapter-3: Data File Handling
## What is a file?
*   File is a named location on disk to store related information. It is used to permanently store data in a non-volatile memory (e.g. hard disk).

*    Since, random access memory (RAM) is volatile which loses its data when computer is turned off, we use files for future use of the data.

*    When we want to read from or write to a file we need to open it first. When we are done, it needs to be closed, so that resources that are tied with the file are freed.


*   Hence, in Python, a file operation takes place in the following order.

> 1.   Open a file
2.   Read or write (perform operation)
3.   Close the file

## How to open a file?
Python has a built-in function ***`open()`*** to open a file. This function returns a file object, also called a handle, as it is used to read or modify the file accordingly.


```python
# Syntax
f = open(file[, mode])

# Example
f = open("test.txt")    # open file in current directory
f = open("C:\\Python33\\README.txt")  # specifying full path
```

*   We can specify the mode while opening a file. In mode, we specify whether we want to read ***` 'r'`*** , write***` 'w' `*** or append ***` 'a'`*** to the file. We also specify if we want to open the file in text mode or binary mode.

*   The default is reading in text mode. In this mode, we get strings when reading from the file.

*   On the other hand, binary mode returns bytes and this is the mode to be used when dealing with non-text files like image or exe files.

> ![alt text](https://i.imgur.com/jxnIkEn.png)


```python
f = open("test.txt")      # equivalent to 'r' or 'rt'
f = open("test.txt",'w')  # write in text mode
f = open("img.bmp",'r+b') # read and write in binary mode
```

## How to close a file Using Python?
*  When we are done with operations to the file, we need to properly close the file.

*  Closing a file will free up the resources that were tied with the file and is done using Python ***`close()`*** method.

*  Python has a garbage collector to clean up unreferenced objects but, we must not rely on it to close the file.


```python
f = open("test.txt")
# perform file operations
f.close()
```

*  Another way is to use the  ***`with`***  statement
*  We don't need to explicitly call the close() method. It is done internally.


```python
with open("test.txt") as f:
   # perform file operations
```

## How to read files in Python?
To read a file in Python, we must open the file in reading mode.

There are various methods available for this purpose. We can use the ***`read(size)`*** method to read in ***`size`*** number of data. If ***`size`*** parameter is not specified, it reads and returns up to the end of the file.


```python
# This is the test file
!cat /content/gdrive/My\ Drive/file_handling/test.txt
```

    This is my first file
    This file
    contains three lines



```python
from google.colab import drive
drive.mount('/content/gdrive')

f = open("/content/gdrive/My Drive/file_handling/test.txt",'r')
print f.read(4)    # read the first 4 data
print f.read(4)    # read the next 4 data
print f.read()     # read in the rest till end of file
print f.read()  # further reading returns empty sting
```

    This
     is 
    my first file
    This file
    contains three lines
    
    


We can see that, the ***`read()`*** method returns newline as '\n'. Once the end of file is reached, we get empty string on further reading.

We can change our current file cursor (position) using the ***`seek()`*** method. Similarly, the ***`tell()`*** method returns our current position (in number of bytes).


```python
print f.tell()
f.seek(0)
print f.read()
```

    0
    None
    This is my first file
    This file
    contains three lines
    


Alternately, we can use ***`readline()`*** method to read individual lines of a file. This method reads a file till the newline, including the newline character.


```python
print f.readline()

print f.readline()

print f.readline()

print f.readline()
```

    This is my first file
    
    This file
    
    contains three lines
    
    


Lastly, the ***`readlines()`*** method returns a list of remaining lines of the entire file. All these reading method return empty values when end of file (EOF) is reached.


```python
print f.readlines()
```

    ['This is my first file\n', 'This file\n', 'contains three lines\n']


## How to write to File Using Python?
*  In order to write into a file in Python, we need to open it in write 'w', append 'a' or exclusive creation 'x' mode.

*  We need to be careful with the 'w' mode as it will overwrite into the file if it already exists. All previous data are erased.

*  Writing a string or sequence of bytes (for binary files) is done using write() method. This method returns the number of characters written to the file.


```python
with open("test.txt",'w') as f:
   f.write("my first file\n")
   f.write("This file\n\n")
   f.write("contains three lines\n")
```


```python

```
