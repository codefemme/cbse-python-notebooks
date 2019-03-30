
# Lists
Python knows a number of compound data types, used to group together other values. The most versatile is the list, which can be written as a list of comma-separated values (items) between square brackets. Lists might contain items of different types, but usually the items all have the same type.


```python
squares = [1, 4, 9, 16, 25]
print(squares)
```

    [1, 4, 9, 16, 25]


## Creating and Initialising Lists


We can inialise a list in the following ways:


*   By enclosing elements in [ ].
*   Using other Lists
*   List  comprehension
*   Using built-in object




```python
# Using []
list1 = [1, 2, 3]
print (list1)

# Using other list
list2 = list1[:]
print( list2)

# List Comprehension
n = 5
list3 = range(5)
print (list3)

# Using built-in object
list4 = list() # This method creates an empty list
print( list4)
```

    [1, 2, 3]
    [1, 2, 3]
    [0, 1, 2, 3, 4]
    []


## Indexing

Lists can be indexed (subscripted), with the first element having index 0:


```python
squares = [1, 4, 9, 16, 25]
print( squares[0])  # element in position 0
print( squares[4])  # element in position 5
```

    1
    25


Indices may also be negative numbers, to start counting from the right:


```python
squares = [1, 4, 9, 16, 25]
print(squares[-1])  # last element
print(squares[-2])  # second-last element
```

    25
    16


## Slicing


*   Syntax of list slicing is `lst[start : stop : steps]`.
*   which means that slicing will start from index **start** will go up to **stop** in **step** of steps.
*   Default value of start is 0, stop is last index of list and for step it is 1.




```python
# Let us first create a list to demonstrate slicing 
# lst contains all number from 1 to 10 
lst = range(1, 11) 
print( lst) 
#  below list has numbers from 2 to 5 
lst1_5 = lst[1 : 5] 
print( lst1_5) 
#  below list has numbers from 6 to 8 
lst5_8 = lst[5 : 8] 
print( lst5_8) 
#  below list has numbers from 2 to 10 
lst1_ = lst[1 : ] 
print( lst1_) #notice the underscore
#  below list has numbers from 1 to 5 
lst_5 = lst[: 5] 
print( lst_5) 
#  below list has numbers from 2 to 8 in step 2 
lst1_8_2 = lst[1 : 8 : 2] 
print (lst1_8_2) 
#  below list has numbers from 10 to 1 
lst_rev = lst[ : : -1] 
print (lst_rev) 
#  below list has numbers from 10 to 6 in step 2 
lst_rev_9_5_2 = lst[9 : 4 : -2] 
print (lst_rev_9_5_2)
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    [2, 3, 4, 5]
    [6, 7, 8]
    [2, 3, 4, 5, 6, 7, 8, 9, 10]
    [1, 2, 3, 4, 5]
    [2, 4, 6, 8]
    [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
    [10, 8, 6]


## Traversing a List
Traversing a list means accessing all the elements of the list one after the other by
using the subscript. A list can be traversed using a 'for' loop or a 'while' loop.


```python
squares = [1, 4, 9, 16, 25]

# Traversal using for loop
for i in range(len(squares)):
  print( squares[i])

print('')

# Traversal using while loop
i = 0
while i < len(squares):
  print( squares[i])
  i = i + 1
```

    1
    4
    9
    16
    25
    
    1
    4
    9
    16
    25


## Appending elements to a list
Appending a list is adding more element(s) at the end of the list. To add new elements at the end of the list, Python provides a method `append()`.




```python
squares = [1, 4, 9, 16, 25]
squares.append(36)

print( squares)
```

    [1, 4, 9, 16, 25, 36]


## Updating list elements
Unlike strings, which are immutable, lists are a mutable type, i.e. it is possible to change their content:


```python
cubes = [1, 8, 27, 65, 125]  # something's wrong here
# the cube of 4 is 64, not 65!
cubes[3] = 64  # replace the wrong value
print( cubes)
```

    [1, 8, 27, 64, 125]


## Concatenation(+) And Repetitions(*)
As lists are sequences, they support many operations of strings. For example, operator + & * results in concatenation & repetition of lists. Use of these operators generate a new list.


```python
squares1 = [1, 4, 9, 16, 25]
squares2 = [36, 49, 64, 81]

# Concatenation
print( squares1 + squares2)

# Repetition
print (squares1 * 3)
```

    [1, 4, 9, 16, 25, 36, 49, 64, 81]
    [1, 4, 9, 16, 25, 1, 4, 9, 16, 25, 1, 4, 9, 16, 25]


## Deleting Elements
It is possible to delete/remove element(s) from the list. There are many ways of doing so:

*   If index is known, we can use pop ( ) or del.
*   If the element is known, not the index, remove ( ) can be used.
*   To remove more than one element, del ( ) with list slice can be used.
*   Using assignment operator.



### list.pop([i])
Remove the item at the given position in the list, and return it. If no index is specified, ` a.pop()` removes and returns the last item in the list.


```python
lst = [-1, 1, 66.25, 333, 333, 1234.5]

print (lst.pop(2)) # Removes element in the second position and returns it
print (lst)

print (lst.pop()) # By default it removes and returns the last element
print (lst)
```

    66.25
    [-1, 1, 333, 333, 1234.5]
    1234.5
    [-1, 1, 333, 333]


### list.remove(x)
Remove the first item from the list whose value is x. It is an error if there is no such item.


```python
lst = [-1, 1, 66.25, 333, 333, 1234.5]

lst.remove(333) # Removes the first occurrence of 333
print( lst)
```

    [-1, 1, 66.25, 333, 1234.5]


### The del statement
There is a way to remove an item from a list given its index instead of its value: the `del` statement. This differs from the `pop()` method which returns a value. The `del` statement can also be used to remove slices from a list or clear the entire list (which we did earlier by assignment of an empty list to the slice). For example:


```python
a = [-1, 1, 66.25, 333, 333, 1234.5]

del a[0]
print( a)

del a[2:4]
print( a)

del a[:]
print( a)
```

    [1, 66.25, 333, 333, 1234.5]
    [1, 66.25, 1234.5]
    []


### Using Assignment operator
A slice can be equated to an empty list which implicitly deletes the slice:


```python
a = [-1, 1, 66.25, 333, 333, 1234.5]

a[2:4] = [] # deletes elements of the slice
print( a)
```

    [-1, 1, 333, 1234.5]


## Other list methods
### list.insert(i, x)
Insert an item at a given position. The first argument is the index of the element before which to insert, so a.insert(0, x) inserts at the front of the list, and a.insert(len(a), x) is equivalent to a.append(x).


```python
squares = [1, 4, 16, 25]
squares.insert(2,9) # inserts 9 in the index 2

print( squares)
```

    [1, 4, 9, 16, 25]


### list.reverse()
Reverse the elements of the list, in place.


```python
a = [66.25, -1, 333, 1, 1234.5, 333]

a.reverse()
print( a)
```

    [333, 1234.5, 1, 333, -1, 66.25]


### list.sort(key=None, reverse=False)
Sort the items of the list in place (the arguments can be used for sort customization).



```python
# A function that returns the length of the value:
def myFunc(e):
  return len(e)

cars = ['Ford', 'BMWX', 'Volvo']

#cars.sort() # sorts alphabetically
#print cars

#cars.sort(reverse=True) # sorts in the reverse order of alphabets
#print cars

cars.sort(key=myFunc) # sort the list by the length of the values
print( cars)

cars.sort(key=myFunc, reverse=True) # sort the list by the length of the values and reversed
print( cars)

cars.sort(reverse = True, key = myFunc) # sort the list by the length of the values and reversed
print( cars)
```

    ['Ford', 'BMWX', 'Volvo']
    ['Volvo', 'Ford', 'BMWX']
    ['Volvo', 'Ford', 'BMWX']


### sorted(iterable[, cmp[, key[, reverse]]])
`sorted()` function also behaves in similar manner except for it produce a new sorted list, so original is not changed.


```python
# A function that returns the length of the value:
def myFunc(e):
  return len(e)

cars = ['Ford', 'BMW', 'Volvo']

print (sorted(cars)) # sorts alphabetically
print (sorted(cars, reverse=True)) # sorts in the reverse order of alphabets
print (cars)
print (sorted(cars, key=myFunc)) # sort the list by the length of the values
print (sorted(cars, key=myFunc, reverse=True)) # sort the list by the length of the values and reversed
```

    ['BMW', 'Ford', 'Volvo']
    ['Volvo', 'Ford', 'BMW']
    ['Ford', 'BMW', 'Volvo']
    ['BMW', 'Ford', 'Volvo']
    ['Volvo', 'Ford', 'BMW']



```python

```
