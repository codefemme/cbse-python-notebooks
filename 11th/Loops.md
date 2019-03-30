
# Chapter 3: Conditional and Looping Constructs

## Conditional Statements

* Equals: a == b
* Not Equals: a != b
* Less than: a < b
* Less than or equal to: a <= b
* Greater than: a > b
* Greater than or equal to: a >= b

We almost always need the ability to check the condition and then change the course of program of what needs to be done, and the simplest way to do so is using conditional statements.

## 3.1 If Statement

Conditional operations can be performed in Python using **if** statements.

An "if statement" is written by using the if keyword.


```python
a = 33
b = 200
if b > a:
  print("b is greater than a")
```


```python
if a > b and c > a:
  print("Both conditions are True")

```


```python
if a > b or a > c:
  print("At least one of the conditions are True")

```

**INDENTATION IS MANDATORY.**

**Unlike C++, Python relies on indentation, using whitespace, to define scope in the code whereas most other programming languages often use curly-brackets for this purpose. Not indenting your code properly will lead to syntactical errors.** 


```python
a = 33
b = 200
if b > a:
print("b is greater than a") 
# you will get an error frankly because the compiler doesn't know where your if statement starts and ends.
 
```

### elif statement

The **elif** keyword is pythons way of saying "if the previous conditions were not true, then try this condition".


```python
a = 33
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")

```

###  else statement

The else keyword catches anything which isn't caught by the preceding conditions. No parameter can be given along with the else keyword.


```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```


```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```

## Looping Constructs 

We know that computers are often used to automate the repetitive tasks. One of the
advantages of using computer to repeatedly perform an identical task is that it is done
without making any mistake. Loops are used to repeatedly execute the same code in a
program. Python provides two types of looping constructs:

* while loop
* for loop

## 3.2 While loop

With the while loop we can execute a set of statements as long as a condition is true.

Syntax: 
while expression:
       statement(s)


```python
i = 1
while i < 6:
  print(i)
  i += 1
```

Note: remember to increment i, or else the loop will continue forever. 

The while loop requires relevant variables to be ready, in this example we need to define an indexing variable, i, which we set to 1.

### break statement

With the break statement we can stop the loop even if the while condition is true: 

![Flowchart](https://www.tutorialspoint.com/python/images/cpp_break_statement.jpg)


```python
chocolates =10
while chocolates<=10:
  chocolates-=1
  print("We have", chocolates ,"chocolates")
  if chocolates==5:
    break
print("call the parents, we have a thief")
```

    ('We have', 9, 'chocolates')
    ('We have', 8, 'chocolates')
    ('We have', 7, 'chocolates')
    ('We have', 6, 'chocolates')
    ('We have', 5, 'chocolates')
    we have a thief


### continue statement

With the continue statement we can stop the current iteration, and continue with the next:

![alt text](https://www.tutorialspoint.com/python/images/cpp_continue_statement.jpg)




```python
oranges = 0
apples = 0 

while oranges!= -1:
  oranges= int(input("Enter the number of oranges"))
  apples = int(input("Enter the number of apples"))
  
  if oranges==0:
    continue
  print(apples+ oranges)
  
  
```

### pass statement

The pass statement is a null operation; nothing happens when it executes. The pass is also useful in places where your code will eventually go, but has not been written yet


```python
while True:
  pass
  #This is a pass block
```

## 3.3 for loops

A for loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).

This is less like the for keyword in other regular programming language, and works more like an iterator method as found in other object-orientated programming languages.


```python
# Syntax

for iterating_variable in sequence:
   statements
```

![alt text](https://www.tutorialspoint.com/python/images/python_for_loop.jpg)

Even strings are iterable objects, they contain a sequence of characters:


```python
for letter in 'Python':    
   print ('Current Letter :', letter)


```


```python
for x in "CodeFemme":
  print x
```

for loops are the most efficient looping constructs available in Python. They can iterate through almost anything.

They can iterate through lists as well.


```python
fruits = ['banana', 'apple',  'mango', 'watermelon', 'pineapple']
for fruit in fruits:       
   print 'Current fruit :', fruit
    
    
    

```

An alternative way of iterating through each item is by index offset into the sequence itself.


```python
fruits = ['banana', 'apple',  'mango', 'watermelon', 'pineapple']
for i in range(len(fruits)):
   print 'Current fruit :', fruits[i]

```

With the break statement we can stop the loop before it has looped through all the items:

Exit the loop when x is "banana":


```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x) 
  if x == "banana":
    break

```

With the continue statement we can stop the current iteration of the loop, and continue with the next:

Do not print banana:


```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    continue
  print(x)
```

### The range() Function

We saw the range() function in Chapter 2 when we studied about Built-in functions.
It is basically used to specify an arithmetic progression during iteration. 
To loop through a set of code a specified number of times, we can use the range() function.
 
The range() function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.


```python
for x in range(10):
  print(x)
```

The value for x starts as 0,  as indexing starts at 0 in Python, and ends at the stop value minus 1. Like in the above example it stops at 9 since its the 10 iteration.


```python
for x in range(2, 6):
  print(x)
```


```python
for x in range(3, 30, 3):
  print(x)
```

    3
    6
    9
    12
    15
    18
    21
    24
    27


### Using else in a for loop?

The else keyword in a for loop specifies a block of code to be executed when the loop is finished:


```python
for x in range(6):
  print(x)
else:
  print("Finally finished!")
```


```python
for x in "Codefemme":
  if x=="a":
    print("A")
else:
  print("no A found") #Why no indent?
```

    no A found


## 3.4 Nested Loops

A nested loop is a loop inside a loop.

The "inner loop" will be executed one time for each iteration of the "outer loop":

Syntax: 


```python
for iterating_var in sequence:
   for iterating_var in sequence:
                  statements(s)
   statements(s)
```

You can put any type of loop inside of any other type of loop. For example a for loop can be inside a while loop or vice versa.


```python

# Python program to display all the prime numbers within an interval


lower = 1
upper = 100

print("Prime numbers between",lower,"and",upper,"are:")

for num in range(lower,upper + 1):
   # prime numbers are greater than 1
   if num > 1:
       for i in range(2,num):
           if (num % i) == 0:
               break
       else:
           print(num)
```


```python
# Python program to see loop pointer

for b in range(0,11):
    print 'here is the outer loop',b
    for x in range(0, 16):
        #k=p[x]
        print 'here is the inner loop',x
```

## 3.5 Recursion

Recursion is a common mathematical and programming concept. It means that a function calls itself. This has the benefit of meaning that you can loop through data to reach a result.

The developer should be very careful with recursion as it can be quite easy to slip into writing a function which never terminates, or one that uses excess amounts of memory or processor power. However, when written correctly recursion can be a very efficient and mathematically-elegant approach to programming.


```python
# Python program to print fibonacci numbers:
def recur_fibo(n):
   """Recursive function to
   print Fibonacci sequence"""
   if n <= 1:
       return n
   else:
       return(recur_fibo(n-1) + recur_fibo(n-2))
nterms = 8
if nterms <= 0:
   print("Plese enter a positive integer!")
else:
   print("Fibonacci sequence:")
   for i in range(nterms):
       print(recur_fibo(i))
```

    Fibonacci sequence:
    0
    1
    1
    2
    3
    5
    8
    13



```python
# Python program for the factorial of a number using recursion


def fact(n):
    if n == 0:
        return 1
    else:
        return n * fact(n-1)
 
 
print(fact(20))

```

    2432902008176640000



```python

```
