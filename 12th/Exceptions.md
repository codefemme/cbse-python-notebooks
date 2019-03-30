
# Chapter-4: Exception Handling 
##  Exceptions
Even if a statement or expression is syntactically correct, it may cause an error when an attempt is made to execute it. Errors detected during execution are called ***exceptions*** and are not unconditionally fatal: you will soon learn how to handle them in Python programs. Most exceptions are not handled by programs, however, and result in error messages as shown here:


```python
print 10 * (1/0)
```


    

    ZeroDivisionErrorTraceback (most recent call last)

    <ipython-input-21-f3ff71476485> in <module>()
    ----> 1 print 10 * (1/0)
          2 print
          3 print 4 + spam*3
          4 print
          5 print '2' + 2


    ZeroDivisionError: integer division or modulo by zero



```python
print 4 + spam*3
```


    

    NameErrorTraceback (most recent call last)

    <ipython-input-22-d05dff79dda9> in <module>()
    ----> 1 print 4 + spam*3
    

    NameError: name 'spam' is not defined



```python
print '2' + 2
```


    

    TypeErrorTraceback (most recent call last)

    <ipython-input-23-e922873acc1e> in <module>()
    ----> 1 print '2' + 2
    

    TypeError: cannot concatenate 'str' and 'int' objects


*   The last line of the error message indicates what happened. Exceptions come in different types, and the type is printed as part of the message: the types in the example are ***`ZeroDivisionError`***, ***`NameError`*** and ***`TypeError`***. The string printed as the exception type is the name of the built-in exception that occurred. This is true for all built-in exceptions, but need not be true for user-defined exceptions (although it is a useful convention). Standard exception names are built-in identifiers (not reserved keywords).

*   The rest of the line provides detail based on the type of exception and what caused it.

*   The preceding part of the error message shows the context where the exception happened, in the form of a stack traceback. In general it contains a stack traceback listing source lines; however, it will not display lines read from standard input.

Before getting to know about how to handle exceptions, we must get to know about a few built-in exceptions:
> ![alt text](https://i.imgur.com/as993oO.png)

### Handling Exceptions
It is possible to write programs that handle selected exceptions. Look at the following example, which asks the user for input until a valid integer has been entered, but allows the user to interrupt the program (using *`Control-C`* or whatever the operating system supports); note that a user-generated interruption is signalled by raising the ***`KeyboardInterrupt`*** exception.


```python
while True:
     try:
         x = int(raw_input("Please enter a number: "))
         break
     except ValueError:
         print "Oops!  That was no valid number.  Try again..."
```

    Please enter a number: a
    Oops!  That was no valid number.  Try again...
    Please enter a number: abc
    Oops!  That was no valid number.  Try again...
    Please enter a number: 21


The ***`try`*** statement works as follows:

*   First, the *try clause* (the statement(s) between the ***`try`*** and ***`except`*** keywords) is executed.
*   If no exception occurs, the except clause is skipped and execution of the try statement is finished.


*   If an exception occurs during execution of the try clause, the rest of the clause is skipped. Then if its type matches the exception named after the ***`except`*** keyword, the except clause is executed, and then execution continues after the ***`try`*** statement.
*   If an exception occurs which does not match the exception named in the except clause, it is passed on to outer ***`try`*** statements; if no handler is found, it is an unhandled exception and execution stops with a message as shown above.

A ***`try`*** statement may have more than one except clause, to specify handlers for different exceptions. At most one handler will be executed. Handlers only handle exceptions that occur in the corresponding try clause, not in other handlers of the same ***`try`*** statement. An except clause may name multiple exceptions as a parenthesized tuple, for example:


```python
except (RuntimeError, TypeError, NameError):
  pass
```

The ***`try … except`*** statement has an optional *else clause*, which, when present, must follow all except clauses. It is useful for code that must be executed if the try clause does not raise an exception. For example:


```python
import sys

for arg in sys.argv[2:]:
    try:
        f = open(arg, 'r')
    except IOError:
        print 'cannot open', arg
    else:
        print arg, 'has', len(f.readlines()), 'lines'
        f.close()
```

    /root/.local/share/jupyter/runtime/kernel-8785c033-e79e-48d6-aea6-65bf50a1dcbb.json has 12 lines


### Raising Exceptions
The ***`raise`*** statement allows the programmer to force a specified exception to occur. For example:


```python
raise NameError('HiThere')
```


    

    NameErrorTraceback (most recent call last)

    <ipython-input-29-72c183edb298> in <module>()
    ----> 1 raise NameError('HiThere')
    

    NameError: HiThere


The sole argument to ***`raise`*** indicates the exception to be raised. This must be either an exception instance or an exception class (a class that derives from ***`Exception`***).

If you need to determine whether an exception was raised but don’t intend to handle it, a simpler form of the ***`raise`*** statement allows you to re-raise the exception:


```python
try:
  raise NameError('HiThere')
except NameError:
  print 'An exception flew by!'
  raise
```

    An exception flew by!



    

    NameErrorTraceback (most recent call last)

    <ipython-input-31-fc3cdc683f26> in <module>()
          1 try:
    ----> 2   raise NameError('HiThere')
          3 except NameError:
          4   print 'An exception flew by!'
          5   raise


    NameError: HiThere



```python

```
