
# Strings

*   Strings can be defined as a contiguous sequence of symbols or characters.
*   In Python Strings are denoted by single, double quotes.




```python
print ('spam eggs')  # single quotes
print ('doesn\'t')  # use \' to escape the single quote...
print ("doesn't")  # ...or use double quotes instead
print ('"Yes," they said.')
print ("\"Yes,\" they said.")
print ('"Isn\'t," they said.')

```

    spam eggs
    doesn't
    doesn't
    "Yes," they said.
    "Yes," they said.
    "Isn't," they said.


In the above example, backslash (\\) is used as an **escape sequence**. An escape sequence is nothing but a **special character that has a specific function**. As shown above, backslash (\\) is used to escape the quote. 

## Creating and Initialising Strings

We can inialise a string in the following ways:


*   Literal/Constant
*   Using input() method to take input from user




```python
strLiteral = 'spam eggs'
print(strLiteral)

strInput = input()
print (strInput) #hi gets printed only once below, the first hi is the input statement.
```

    spam eggs
    hi
    hi


## Indexing

Strings can be indexed (subscripted), with the first character having index 0. There is no separate character type; a character is simply a string of size one:


```python
word = 'Python'
print (word[0])  # character in position 0
print (word[5])  # character in position 5
```

    P
    n


Indices may also be negative numbers, to start counting from the right:


```python
word = 'Python'
print (word[-1])  # last character
print (word[-2])  # second-last character
print (word[-6])
```

    n
    o
    P


## Python Strings are Immutable
Python strings cannot be changed — they are immutable. Therefore, assigning to an indexed position in the string results in an error:


```python
word = 'Python'
word[0] = 'J'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-26-ad89e228b316> in <module>
          1 word = 'Python'
    ----> 2 word[0] = 'J'
    

    TypeError: 'str' object does not support item assignment


## Traversing a string
Traversing a string means accessing all the elements of the string one after the other by
using the subscript. A string can be traversed using a 'for' loop or a 'while' loop. 


```python
word = 'Python'

# Traversal using for loop
for i in word:
  print(i)

print ('')

# Traversal using while loop
i = 0
while i < len(word):
  print( word[i])
  i = i + 1
```

    P
    y
    t
    h
    o
    n
    
    P
    y
    t
    h
    o
    n


## Operations on String

### Concatenation (+)
Strings can be concatenated (glued together) with the + operator. Both the operands should be of string datatype else it results in an error


```python
# 'un', followed by 'ium'
word = 'un' + 'ium'
print( word)

# Concatenating an integer and a string leads to an error
word = 'un' + 3
print( word)
```

    unium



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-28-242014416292> in <module>
          4 
          5 # Concatenating an integer and a string leads to an error
    ----> 6 word = 'un' + 3
          7 print( word)


    TypeError: can only concatenate str (not "int") to str


### Repetition (*)

Strings can be repeated with the * operator where one operand is the string and the other operand is an integer:


```python
# 3 times 'Python'
word = 3 * 'Python'
print( word)
```

    PythonPythonPython


### Membership ([not] in)
The *in* operator returns the boolean value *True* if the string contains the given character or the sequence of characters and vice-versa for the case of *not in* operator.


```python
word = 'crossing farewell'

# Usage of in
evalIn = 'fare' in word
print( evalIn)

# Usage of not in
evalNotIn = 'fare' not in word
print(evalNotIn)
```

    True
    False


### Slicing (str[m:n])


*   Slicing allows you to obtain a substring
*   Slice indices have useful defaults; an omitted first index defaults to zero, an omitted second index defaults to the size of the string being sliced.




```python
word = 'Python'
print (word[0:2])  # characters from position 0 (included) to 2 (excluded)
print (word[2:5])  # characters from position 2 (included) to 5 (excluded)

print (word[:2])   # character from the beginning to position 2 (excluded)
print (word[4:])   # characters from position 4 (included) to the end
print (word[-2:])  # characters from the second-last (included) to the end
```

    Py
    tho
    Py
    on
    on


## String methods & built in functions

### len()
Returns the length of the string:


```python
word = 'Python'
print (len(word))
```

    6


### string.capitalize(word)
Return a copy of word with only its first character capitalized.


```python
word = 'liGHT battlefield'
print (word.capitalize())
```

    Light battlefield


### string.find(s, sub[, start[, end]])
Return the lowest index in s where the substring sub is found such that sub is wholly contained in s[start:end]. Return -1 on failure. Defaults for start and end and interpretation of negative values is the same as for slices.


```python
word = 'mammals'

# On omitting the start parameters, the function starts the search from the 
# beginning
print (word.find('ma'))
print (word.find('ma',2))

# Displays -1 because the substring could not be found between the index 2 
# and 4-1
print (word.find('ma',2,4))

print (word.find('ma',2,5))
```

    0
    3
    -1
    3


### str.isalnum()
Return true if all characters in the string are alphanumeric and there is at least one character, false otherwise.


```python
word = 'institution kitchen'
print (word.isalnum()) # Returns False as space is not an alphanumeric character

word = 'institution4kitchen'
print (word.isalnum()) # Returns True
```

    False
    True


### str.isalpha()
Return true if all characters in the string are alphabetic and there is at least one character, false otherwise.


```python
word = 'apparatus123'
print (word.isalpha()) # Returns False as it contains numeric values

word = 'apparatus'
print (word.isalpha()) # Returns True
```

    False
    True


### str.isdigit()
Return true if all characters in the string are digits and there is at least one character, false otherwise.


```python
word = 'displace123'
print (word.isdigit())

word = '123'
print (word.isdigit())
```

    False
    True


### str.lower()
Returns the exact copy of the string with all the letters in lowercase. 


```python
word = 'fUnCtIonAl jUnGlE'
print (word.lower())
```

    functional jungle


### str.islower()
Returns True if the string is in lowercase else returns False.


```python
word = 'Python'
print (word.islower())

word = 'python'
print (word.islower())
```

    False
    True


### str.isupper()
Returns True if the string is in uppercase.


```python
word = 'PYTHON'
print (word.isupper())

word = 'python'
print (word.isupper())
```

    True
    False


### str.upper()
Returns the exact copy of the string with all letters in uppercase.


```python
word = 'fUnCtIonAl jUnGlE'
print (word.upper())
```

    FUNCTIONAL JUNGLE


### str.lstrip([chars])
Return a copy of the string with leading characters removed. The *chars* argument is a string specifying the set of characters to be removed. If omitted or `None`, the *chars* argument defaults to removing whitespace. The chars argument is not a prefix; rather, all combinations of its values are stripped


```python
word = '   spacious   '
print (word.lstrip()) # repr() is a method which adds apostrophes

word = 'www.example.com'
print (word.lstrip('www.'))# repr() is a method which adds apostrophes
```

    spacious   
    example.com


### str.rstrip([chars])
Return a copy of the string with trailing characters removed. The *chars* argument is a string specifying the set of characters to be removed. If omitted or `None`, the *chars* argument defaults to removing whitespace. The *chars* argument is not a suffix; rather, all combinations of its values are stripped:


```python
word = '   spacious   '
print (repr(word.rstrip()))

word = 'mississippi'
print (repr(word.rstrip('ippi')))
```

    '   spacious'
    'mississ'


### str.isspace()
Return true if there are only whitespace characters in the string and there is at least one character, false otherwise.


```python
word = '  '
print (word.isspace())

word = 'Python'
print (word.isspace())
```

    True
    False


### str.istitle()
Return true if the string is a titlecased string and there is at least one character, for example uppercase characters may only follow uncased characters and lowercase characters only cased ones. Return false otherwise.


```python
word = 'marsh exact'
print (word.istitle())

word = 'Marsh Exact'
print (word.istitle())
```

    False
    True


### str.replace(old, new[, count])
Return a copy of the string with all occurrences of substring old replaced by new. If the optional argument count is given, only the first count occurrences are replaced.


```python
word = 'mourning silver mourning silver silver mourning silver'

print (word.replace('mourning', 'happy')) # Replaces all occurrences of mourning
print (word.replace('mourning', 'happy', 2)) # Replaces only 2 occurence of mourning
```

    happy silver happy silver silver happy silver
    happy silver happy silver silver mourning silver


### str.join(iterable)
Returns a string in which the string elements have been joined by  a separator. 


```python
words = ['Jan', 'Feb', 'Mar'] # List containing three strings
op = '&'

print(op.join(words))
```

    Jan&Feb&Mar


### str.swapcase()
Return a copy of the string with uppercase characters converted to lowercase and vice versa.


```python
word = 'fUnCtIonAl jUnGlE'
print (word.swapcase())
```

    FuNcTiONaL JuNgLe


### str.partition(sep)
The function partitions the strings at the first occurrence of separator, and returns the strings partition in three parts i.e. before the separator, the separator itself, and the part after the separator. If the separator is not found, returns the string itself, followed by two empty strings.


```python
word = 'The Green Revolution'

print (word.partition('Rev'))
print (word.partition('pe'))
print (word.partition('e'))
```

    ('The Green ', 'Rev', 'olution')
    ('The Green Revolution', '', '')
    ('Th', 'e', ' Green Revolution')


### str.split([sep[, maxsplit]])
The function splits the string into substrings using the separator. The second argument is optional and its default value is zero. If an integer value N is given for the second argument, the string is split in N+1 strings.


```python
word = 'linear$pit$syndrome$cottage$fitness'

print (word.split('$', 3))
print (word.split('e'))
```

    ['linear', 'pit', 'syndrome', 'cottage$fitness']
    ['lin', 'ar$pit$syndrom', '$cottag', '$fitn', 'ss']

