
# Linear List Manipulation
## Data Structures
A data structure is a specialized format for organizing and storing data. General data structure types include the array, the file, the record, the table, the tree, and so on. Any data structure is designed to organize data to suit a specific purpose so that it can be accessed and worked with in appropriate ways. In computer programming, a data structure may be selected or designed to store data for the purpose of working on it with various algorithms.

## List Internal Implementation
*   CPython’s lists are really variable-length arrays, not Lisp-style linked lists. The implementation uses a contiguous array of references to other objects, and keeps a pointer to this array and the array’s length in a list head structure.

*   This makes indexing a list a[i] an operation whose cost is independent of the size of the list or the value of the index.

*    When items are appended or inserted, the array of references is resized. Some cleverness is applied to improve the performance of appending items repeatedly; when the array must be grown, some extra space is allocated so the next few times don’t require an actual resize.

## Basic Operations on a List
### Traversal
Traversal means to move in a list in sequential manner starting from first element to the last element. The code for traversal in the list is as follows:


```python
def traverseList(lst):
  for i in range(len(lst)):
    print lst[i]

lst = [2, 5, 1, 9, 4, 6]
traverseList(lst)
```

    2
    5
    1
    9
    4
    6


### Insertion
Insertion of an element in a sorted list is implemented using bisect module in python as it is more optimized compared to inserting and shifting each and every element.


```python
import bisect

def insertEle(lst, ele):
  loc = bisect.bisect(lst, ele)
  bisect.insort(lst, ele)
  return lst

lst = [14, 26, 45, 50, 77, 85]
ele = 66
print insertEle(lst, ele)
```

    [14, 26, 45, 50, 66, 77, 85]


### Deletion
Implementation to delete and element at a position from a sorted list


```python
def deleteEle(lst, pos):
  for i in range(pos, len(lst)-1):
    lst[i] = lst[i+1]

  # Now we need to delete the last element
  del lst[-1]
  return lst

lst = [14, 26, 45, 50, 77, 85]
pos = 4
print lst
print deleteEle(lst, pos)

```

    [14, 26, 45, 50, 77, 85]
    [14, 26, 45, 50, 85]


# Searching Techniques
There are many searching algorithms. We shall be discussing two of them - Linear Search and Binary
Search.


### Linear search
Implementation to search an element from a list:


```python
def linearSearch(lst, ele):
  flag = 0

  for i in range(len(lst)):
    if lst[i] == ele:
      flag = 1
      break

  if flag > 0:
    print 'Element found at index %d' % i
  else:
    print 'Element not found'

lst = [6, 3, 5, 9, 0, 2, 3]
ele = 2
linearSearch(lst, ele)
```

    Element found at index 5


### Binary Search
This searching technique reduces the number of comparisons and hence saves on processing time. For
binary search, the condition that has to be fulfilled is that the array should be sorted in either ascending or
descending order.


```python
def binarySearch(lst, ele):
  low = 0
  high = len(lst) - 1

  while low < high:
    mid = int((low + high) / 2)

    if lst[mid] == ele:
      print 'Element found at index %d' % mid
      break
    elif lst[mid] < ele:
      low = mid + 1
    else:
      high = mid - 1
  else:
      print 'Element not found' 
  

lst = [1, 3, 6, 8, 10, 13, 15, 17, 20, 23]
ele = 17
binarySearch(lst, ele)
```

    Element found at index 7


## Sorting Techniques
### Selection Sort
The basic logic of selection sort is to repeatedly select the smallest element in the unsorted part of the array
and then swap it with the first element of the unsorted part of the list.


```python
def selectionSort(lst):
  for i in range(len(lst)):
    min = i
    for j in range(i + 1, len(lst)):
      if lst[j] < lst[min]:
        min = j
    lst[min], lst[i] = lst[i], lst[min]
  
  return lst

lst = [6, 2, 5, 8, 4, 9]
print lst
print selectionSort(lst)
```

    [6, 2, 5, 8, 4, 9]
    [2, 4, 5, 6, 8, 9]


### Bubble Sort
In case of bubble sort algorithm, comparison starts from the beginning of the list. Every adjacent pair is
compared and swapped if they are not in the right order (the next one is smaller than the former one).


```python
def bubbleSort(lst):
  for i in range(len(lst)):
    for j in range(len(lst) - 1 - i):
      if lst[j] > lst[j+1]: 
        lst[j], lst[j+1] = lst[j+1], lst[j]
   
  return lst

lst = [6, 2, 5, 8, 4, 9]
print lst
print bubbleSort(lst)
```

    [6, 2, 5, 8, 4, 9]
    [2, 4, 5, 6, 8, 9]


### Insertion Sort
As far as the functioning of the outer loop is considered, insertion sort is similar to selection sort. 
The difference is that the insertion sort does not select the smallest element and put it into place; rather it selects the next element to the right of what was already sorted. Then it slides up each larger element until it gets to the correct location to insert into the sorted part of the array.


```python
def insertionSort(lst):  
    for i in range(1, len(lst)): 
        key = lst[i] 
        j = i - 1
        while j >= 0 and key < lst[j] : 
                lst[j+1] = lst[j] 
                j -= 1
        lst[j+1] = key
    return lst

lst = [6, 2, 5, 8, 4, 9]
print lst
print insertionSort(lst)
```

    [6, 2, 5, 8, 4, 9]
    [2, 4, 5, 6, 8, 9]


# Stacks and Queues in List
## Stack
A stack is a data structure whose elements are accessed according to the Last-In First-Out (LIFO) principle.
This is because in a stack, insertion and deletion of elements can only take place at one end, called top of the
stack.Let's look at the implementation of stack in python:


```python
class Stack(object):
  def __init__(self, limit):
    self.lst = []
    self.limit = limit
  
  def isEmpty(self):
    return bool(len(lst) == 0)
  
  def myPush(self, data):
    if len(lst) < self.limit:
      lst.append(data)
    else:
      print ('Overflow')
  
  def myPop(self):
    if self.isEmpty():
      print ('Underflow')
    else:
      print (lst.pop())
  
  def display(self):
    print ('Base -> ', lst, '<- Top')

s = Stack(10)
op = 'y'

while op == 'y':
  choice = int(input('1.Push\n2.Pop\n3.Display\nEnter Choice: '))
  if choice == 1:
    data = int(input('Enter a number to push into stack: '))
    s.myPush(data)
  elif choice == 2:
    s.myPop()
  elif choice == 3:
    s.display()
  else:
    print ('Invalid Choice')

  op =input('Do you want to continue? (y/n)')

```

    1.Push
    2.Pop
    3.Display
    Enter Choice: 1
    Enter a number to push into stack: 23
    Do you want to continue? (y/n)y
    1.Push
    2.Pop
    3.Display
    Enter Choice: 1
    Enter a number to push into stack: 65
    Do you want to continue? (y/n)y
    1.Push
    2.Pop
    3.Display
    Enter Choice: 3
    Base ->  [23, 65] <- Top
    Do you want to continue? (y/n)y
    1.Push
    2.Pop
    3.Display
    Enter Choice: 2
    65
    Do you want to continue? (y/n)y
    1.Push
    2.Pop
    3.Display
    Enter Choice: 3
    Base ->  [23] <- Top
    Do you want to continue? (y/n)n


## Queue
A Queue is a linear structure which follows a particular order in which the operations are performed. The order is First In First Out (FIFO). A good example of a queue is any queue of consumers for a resource where the consumer that came first is served first. The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added. Let's look at the implementation of queue in python:


```python
class Queue(object):
  def __init__(self, limit):
    self.lst = []
    self.limit = limit
  
  def isEmpty(self):
    return bool(len(lst) == 0)
  
  def enqueue(self, data):
    if len(lst) < self.limit:
      lst.append(data)
    else:
      print ('Overflow')
  
  def dequeue(self):
    if self.isEmpty():
      print ('Underflow')
    else:
      print( lst.pop(0))
  
  def display(self):
    print ('Front -> ', lst, '<- Rear')

s = Queue(10)
op = 'y'

while op == 'y':
  choice = int(raw_input('1.Enqueue\n2.Dequeue\n3.Display\nEnter Choice: '))
  if choice == 1:
    data = int(raw_input('Enter a number to enqueue into queue: '))
    s.enqueue(data)
  elif choice == 2:
    s.dequeue()
  elif choice == 3:
    s.display()
  else:
    print ('Invalid Choice')

  op = input('Do you want to continue? (y/n)')
```

    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 1
    Enter a number to enqueue into queue: 43
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 1
    Enter a number to enqueue into queue: 56
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 1
    Enter a number to enqueue into queue: 78
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 3
    Front ->  [43, 56, 78] <- Rear
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 2
    43
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 4
    Invalid Choice
    Do you want to continue? (y/n)y
    1.Enqueue
    2.Dequeue
    3.Display
    Enter Choice: 3
    Front ->  [56, 78] <- Rear
    Do you want to continue? (y/n)n



```python

```
