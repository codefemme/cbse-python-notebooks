

# CodeFemme

# Python for Educators Workshop- 2018




## Chapter 1: Getting Started  


In order to tell the computer 'what you want to do', we write a program in a language
which computer can understand. Though there are many different programming
languages such as BASIC, Pascal, C, C++, Java, Haskell, Ruby, Python, etc. but we will
study Python in this course.


Before learning the technicalities of Python, some of the reasons why it is so famous are as follows:



*   It is a general purpose programming language which can be used for both
scientific and non scientific programming
*   It is a platform independent programming language.
*   It is excellent for beginners as the language is interpreted, hence gives immediate
results.
* The programs written in Python are easily readable and understandable.


## 1.1 Setting up

So for this course, to run and execute Python programs, we'll be using the default Python IDLE version 2.7. It can be downloaded from the [Python website](https://www.python.org)
There are two modes avaiable in the IDLE.


*   Interactive mode
*   Script mode



### Interactive mode
When we type Python expression / statement / command after the prompt, Python
immediately responds with the output of it


### Script mode
In script mode, we type Python program in a file and then use the interpreter to execute
the content from the file.

Working in interactive mode is convenient for beginners and
for testing small pieces of code, as we can test them immediately. But for coding more
than few lines, we should always save our code so that we may modify and reuse the
code.
Result produced by Interpreter in both the modes, viz., Interactive and script
mode is exactly same.

## 1.2  Hello World!

Python is a very simple language, and has a very straightforward syntax. It encourages programmers to program without boilerplate (prepared) code. The simplest directive in Python is the "print" directive - it simply prints out a line (and also includes a newline, unlike in C).

As we learned in the previous section, Python syntax can be executed by writing directly in the Command Line or by creating a python file on the server, using the .py file extension, and running it in the Command Line(eg. C:\Users\Your Name>python myfile.py)

For example, one difference between Python 2 and 3 is the print statement. In Python 2, the "print" statement is not a function, and therefore it is invoked without parentheses. However, in Python 3, it is a function, and must be invoked with parentheses.


```python
print('codefemme')
```

    codefemme



## 1.3 Variables and Data Types
When we create a program, we often like to store values so that it can be used later. We
use objects to capture data, which then can be manipulated by computer to provide
information. By now we know that object/ variable is a name which refers to a value.



Every object has:

A. **An Identity** - It is the object's address in memory and does not change
once it has been created.

B. **A type** – It is a set of values, and the allowable operations on those
values. 

C. **A value**



### Variables

Unlike other programming languages, Python has no command for declaring a variable.

A variable is created the moment you first assign a value to it.


```python
x = 5

print(x)
 
```

    5



```python
y= 'John'

print(y)

```

    John


**Variables do not need to be declared with any particular type and can even change type after they have been set.**


```python
x = 4  # x is of type int
x = "Sally" # x is now of type str
print(x)

```

    Sally


### Variable Names
A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume). Rules for Python variables:

* A variable name must start with a letter or the underscore character

* A variable name cannot start with a number

* A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
* Variable names are case-sensitive (age, Age and AGE are three different variables)



### Outputting Variables

We can check the output of variables using the **print()** function, as we've used before.

To combine both text and a variable, Python uses the + character:


```python
x = "CodeFemme"
print("We are " + x)

x=4
y= str(x)
print y


```

    We are CodeFemme
    4


You can also use the + character to add a variable to another variable:


```python
x = "Python is"  
y = "awesome"
z =  x + y
print(z)

```

    Python isawesome


**Note:** If you try to combine a string and a number, Python will give you an error:


```python
x = 5
y = "John"
print(x + y)

```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-4-00c66e4310ff> in <module>()
          1 x = 5
          2 y = "John"
    ----> 3 print(x + y)
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'


### Numbers 

In this section, we are going to focus on **integer,
 floating points, and Complex data types**  and associated arithmetic operations. 5 is an example of an integer data type whereas 5.0, 6.2 are examples of floating point data types. Complex as the name suggests is used to denote Complex numbers in python. All standard arithmetic operators are defined in Python.
 
 Int, or integer, is a whole number, positive or negative, without decimals, of unlimited length.


```python
x = 1
y = 35656222554887711
z = -3255522
```

Float, or "floating point number" is a number, positive or negative, containing one or more decimals.


```python
x = 1.10
y = 1.0
z = -35.59
```

Float can also be scientific numbers with an "e" to indicate the power of 10.


```python
x = 35e3
print x
```

    35000.0


### Complex
Complex number in python is made up of two floating point
values, one each for real and imaginary part. For accessing different parts of
variable (object) x;  we will use x.real and x.imag. 

Imaginary part of the
number is represented by 'j' instead of 'i', so 1+0j denotes zero imaginary
part.



```python
x = 5+ 9j

print(x.real)

print(x.imag)

```

    5.0
    9.0


### Strings
Strings are essentially how characters are represented in Python.
String literals in python are surrounded by either single quotation marks, or double quotation marks.

**'hello'** is the same as **"hello"**. 

Strings can be output to screen using the print function. For example: print("hello").

Like many other popular programming languages, strings in Python are arrays of bytes representing unicode characters.

However, **Python does not have a character data type, a single character is simply a string with a length of 1.**



```python
 a = 'Hello World'
 print(a)
```

    Hello World


String elements can be accessed using square brackets.


```python
a= "Hello World"
print(a[0])
```

    H


**There are other data types such as lists, tuples, dictionaries etc. More on that later.**



### type() function

If you're having trouble finding out what the data type of a variable is, we can use the type() function.



```python
type('CodeFemme')

```




    str




```python
type(3.2)  
```




    float




```python
type(5)
```




    int




```python
type('3.2')
```




    str



## 1.4 Operators and Operands 

### Arithmetic Operators

Arithmetic operators are used with numeric values to perform common mathematical operation

There are different types of operators 

|Symbol  | Operation | 
| ---    | --------- |
| + | addition operator | 
| - | subtraction operator|
| * | multiplication operator|
| / | division operator|
| //  | integer division operator  |
| % | remainder operator|








```python
3 + 2
```




    5




```python
3 - 2
```


```python
3 / 2
```


```python
3 * 2 
```




    6




```python
3.3 // 2 #prints the quotient of the division
```




    1.0




```python
3.3 % 2
```




    1.2999999999999998



###  Relational (or) Comparative Operators 

Python treats every line as a statement to be executed except the line beginning with a #. # indicates the line contains comments to the right of # sign which are not to be executed.

| Symbol | Operation              |
|--------|------------------------|
| ==     | equal to               |
| !=     | not equal to           |
| <      | less than              |
| >      | greater than           |
| <=     | less than/equal to     |
| >=     | greater than/ equal to |


```python
3 == 2
```




    False




```python
3 != 2
```




    True




```python
6 > 3
```




    True




```python
4 < 7
```




    True




```python
(5+3) >= 8
```




    True




```python
10-7 <= 2
```




    False



### Logical Operators

Logical operators are used to combine boolean expression or reverse the value of a boolean expression. Here are some examples in Python interactive mode:

| Keyword | Operation                                                           |
|---------|---------------------------------------------------------------------|
| not     | Reverses the state of operand/condition.                            |
| and     | If both the operands are true, then the condition becomes true.     |
| or      | If any one of the operand is true, then the condition becomes true. |




```python
not True
```




    False




```python
6 > 3 and 4 < 5
```




    True




```python
(3 > 0) or (1 > 10)
```




    True



## Assignment operators 

Assignment operators are used to assign values to variables:

| Operator 	| Example 	| Same As    	|
|----------	|---------	|------------	|
| =        	| x = 5   	| x = 5      	|
| +=       	| x += 3  	| x = x + 3  	|
| -=       	| x -= 3  	| x = x - 3  	|
| *=       	| x *= 3  	| x = x * 3  	|
| /=       	| x /= 3  	| x = x / 3  	|
| %=       	| x %= 3  	| x = x % 3  	|
| //=      	| x //= 3 	| x = x // 3 	|
| **=      	| x **= 3 	| x = x ** 3 	|
| &=       	| x &= 3  	| x = x & 3  	|
| ^=       	| x ^= 3  	| x = x ^ 3  	|
| >>=      	| x >>= 3 	| x = x >> 3 	|
| <<=      	| x <<= 3 	| x = x << 3 	|

## 1.5 Expressions and Statements 

An expression is a combination of value(s) (i.e. constant), variable and operators. It generates a single value, which by itself is an expression.
Expression values in turn can act as, Operands for Operators

An
operator may be Left-associative or Right –associative. In left associative, the operator
falling on left side will be evaluated first, while in right assosiative operator falling on
right will be evaluated first.

In python = and ** are Right Associative.





Precedence of operator - Listed from high precedence to low precedence.

| Operator                                     	| Description                                       	|
|----------------------------------------------	|---------------------------------------------------	|
| ()                                           	| Parentheses                                       	|
| **                                           	| Exponent                                          	|
| *, /, //, %                                  	| Multiplication, Division, Floor division, Modulus 	|
| +, -                                         	| Addition, Subtraction                             	|
| ==, !=, >, >=, <, <=, is, is not, in, not in 	| Comparisions, Identity, Membership operators      	|
| not                                          	| Logical NOT                                       	|
| and                                          	| Logical AND                                       	|
| or                                           	| Logical OR                                        	|


**Remember precedence of operators is applied to find out which sub expression
should be evaluated first.**

### Statements

A Python statement is a unit of code that the Python interpreter can execute



```python
area=x**2  #assigment statement
```


```python
print(x) #print statement

print(x, area) #To print multiple items in same line, separate them with comma.
```

**While writing Python statements, keep the following points in mind:**

1. Write one python statement per line (Physical Line). Although it is possible to
write two statements in a line separated by semicolon.

2. Comment starts with „#‟ outside a quoted string and ends at the end of a line.
Comments are not part of statement. They may occur on the line by themselves or
at the end of the statement. They are not executed by interpreter.

3. For a long statement, spanning multiple physical lines, we can use „/‟ at the end of
physical line to logically join it with next physical line. Use of the „/‟ for joining
lines is not required with expression consists of ( ), [ ], { }



4. When entering statement(s) in interactive mode, an extra blank line is treated as
the end of the indented block.

5. Indentation is used to represent the embedded statement(s) in a compound/
Grouped statement. All statement(s) of a compound statement must be indented
by a consistent no. of spaces (usually 4)

6. White space in the beginning of line is part of indentation, elsewhere it is not
significant.

## 1.6 Input and Output

A program needs to interact with end user to accomplish the desired task, this is done
using Input-Output facility. Input means the data entered by the user (end user) of the
program. While writing algorithm(s), getting input from user was represented by
Take/Input. In python, we have raw_input() and input ( ) function available for Input. 


```python
 x=input('Enter your name: ')
    
```

    Enter your name: tarun 



```python
n =input('Enter your name:') 

```

    Enter your name:3


x is a variable which will get the string (ABC), typed by user during the execution of
program. Typing of data for the raw_input function is terminated by 'enter' key.
We can use raw_input() to enter numeric data also. In that case we typecast, i.e., change
the datatype using function, the string data accepted from user to appropriate Numeric
type.

We can take numeric data as input by doing this:


```python
n=int(input('Enter your age: '))
 
```

    Enter your age: tarun



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-32-777d3d2d061d> in <module>()
    ----> 1 n=int(raw_input('Enter your age: '))
    

    ValueError: invalid literal for int() with base 10: 'tarun'



```python
y=int(input('Enter your roll no: '))

```

    Enter your roll no: 23


## 1.7 Comments
Python has commenting capability for the purpose of in-code documentation. Comments are not executed by the compiler.

Comments start with a #, and Python will render the rest of the line as a comment:



```python
#This is a comment.
print("Hello, World!")
```

    Hello, World!


Multi-line comments in Python are called **Docstrings** Docstrings can be one line, or multiline.

Python uses triple quotes at the beginning and end of the docstring:


```python
"""This is a 


multiline docstring."""
```

## That's it for Chapter 1. 

## In the next chapter, we'll be learning about **Functions**. Good Luck!
