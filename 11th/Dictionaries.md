
# Dictionaries
*   Dictionaries are sometimes found in other languages as “associative memories” or “associative arrays”. Unlike sequences, which are indexed by a range of numbers, dictionaries are indexed by keys, which can be any immutable type; strings and numbers can always be keys

*   It is best to think of a dictionary as an unordered set of *key: value* pairs, with the requirement that the keys are unique (within one dictionary).

## Creating a dictionary
Creating a dictionary is as simple as placing items inside curly braces `{}` separated by comma.


```python
# empty dictionary
myDict = {}
print (myDict)

# dictionary with integer keys
myDict = {1: 'apple', 2: 'ball'}
print( myDict)

# dictionary with mixed keys
myDict = {'name': 'John', 1: [2, 4, 3]}
print (myDict)

# using dict()
myDict = dict({1:'apple', 2:'ball'})
print (myDict)

# from sequence having each item as a pair
myDict = dict([(1,'apple'), (2,'ball')])
print (myDict)
```

    {}
    {1: 'apple', 2: 'ball'}
    {1: [2, 4, 3], 'name': 'John'}
    {1: 'apple', 2: 'ball'}
    {1: 'apple', 2: 'ball'}


## Accessing Elements
*   While indexing is used with other container types to access values, dictionary uses keys. Key can be used either inside square brackets or with the **`get()`** method.
*   The difference while using `get()` is that it returns `None` instead of `KeyError`, if the key is not found.


```python
myDict = {'name':'Jack', 'age': 26}

# Output: Jack
print (myDict['name'])

# Output: 26
print (myDict.get('age'))

# Trying to access keys which doesn't exist returns None
print (myDict.get('address'))

# Trying to access keys which doesn't exist throws KeyError
# print myDict['address']
```

    Jack
    26
    None


## Change or Add Elements

*   Dictionaries are mutable. We can add new items or change the value of existing items using assignment operator.

*   If the key is already present, value gets updated, else a new key: value pair is added to the dictionary.



```python
myDict = {'name':'Jack', 'age': 26}
print (myDict)

# update value
myDict['age'] = 27
print (myDict)

# add item
myDict['address'] = 'Downtown'  
print (myDict)
```

    {'age': 26, 'name': 'Jack'}
    {'age': 27, 'name': 'Jack'}
    {'age': 27, 'name': 'Jack', 'address': 'Downtown'}


## Delete Elements
*   We can remove a particular item in a dictionary by using the method pop(). This method removes as item with the provided key and returns the value.
*   The method, popitem() can be used to remove and return an arbitrary item (key, value) form the dictionary. All the items can be removed at once using the clear() method.
*   We can also use the del keyword to remove individual items or the entire dictionary itself.


```python
# create a dictionary
squares = {1:1, 2:4, 3:9, 4:16, 5:25}  

# remove a particular item
print (squares.pop(4)) 
print (squares)

# remove an arbitrary item
print (squares.popitem())
print (squares)

# delete a particular item
del squares[5]  
print (squares)

# remove all items
squares.clear()
print (squares)

# delete the dictionary itself
del squares

# Throws Error
# print squares
```

    16
    {1: 1, 2: 4, 3: 9, 5: 25}
    (1, 1)
    {2: 4, 3: 9, 5: 25}
    {2: 4, 3: 9}
    {}


## Traversing a Dictionary
Let us visit each element of the dictionary to display its values on screen. This can be done by using a `for` loop. 


```python
ageDict = {'Tim': 18,'Charlie':12,'Tiffany':22,'Robert':25}

for i in ageDict:
  print i, ':', ageDict[i]
```

    Tim : 18
    Tiffany : 22
    Robert : 25
    Charlie : 12


## Merging Dictionaries
Two dictionaries can be merged in to one by using **`update()`** method.  It merges the keys and values of one dictionary into another and overwrites values of the same key.


```python
dict = {'Name': 'Zara', 'Age': 7}
dict2 = {'Sex': 'female' }

dict.update(dict2)
print( dict)
```

    {'Name': 'Zara', 'Age': 7, 'Sex': 'female'}


## Other Dictionary Methods
### len(s)
 This method returns number of key-value pairs in the given dictionary.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}

print (len(myDict))
```

    7


### dict.clear()
It removes all items from the particular dictionary.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}
print (myDict)

myDict.clear()
print (myDict)

```

    {'wed': 'Wednesday', 'sun': 'Sunday', 'thu': 'Thursday', 'tue': 'Tuesday', 'mon': 'Monday', 'fri': 'Friday', 'sat': 'Saturday'}
    {}


### dict.get(key[, value])
Return the value for `key` if `key` is in the dictionary, else default. If default is not given, it defaults to `None`, so that this method never raises a `KeyError`.


```python
person = {'name': 'Phill', 'age': 22}

print ('Name:', person.get('name'))
print ('Age:', person.get('age'))

# value is not provided
print ('Salary:', person.get('salary'))

# value is provided
print ('Salary:', person.get('salary', 0.0))
```

    Name: Phill
    Age: 22
    Salary: None
    Salary: 0.0


### dict.has_key(key)
This function returns ‘True’, if dictionary has a key, otherwise it returns ‘False’.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}

print (myDict.has_key('fri'))
print (myDict.has_key('aaa'))
```

    True
    False


### dict.items()
Return a copy of the dictionary’s list of **`(key, value)`** pairs.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}

print (myDict.items())
```

    [('wed', 'Wednesday'), ('sun', 'Sunday'), ('thu', 'Thursday'), ('tue', 'Tuesday'), ('mon', 'Monday'), ('fri', 'Friday'), ('sat', 'Saturday')]


### dict.keys()
Return a copy of the dictionary’s list of keys.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}

print (myDict.keys())
```

    ['wed', 'sun', 'thu', 'tue', 'mon', 'fri', 'sat']


### dict.values()
Return a copy of the dictionary’s list of values.


```python
myDict = {'sun': 'Sunday', 'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday',
          'sat': 'Saturday'}

print (myDict.values())
```

    ['Wednesday', 'Sunday', 'Thursday', 'Tuesday', 'Monday', 'Friday', 'Saturday']



```python

```
