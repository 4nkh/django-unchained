Session 1: Intro to Python
==============================================
Description:
------------
This session will discuss pythonic syntax, structure, and principles. Useful built-in functions, and data structures critical for use with django will be covered. We will be using the python interactive interpreter for a portion of this lesson.

Outline:
--------
* Intro to Python: Why Python?
* Data Structures: Strings, Integers, Floats, Dictionaries, Lists, Tuples, Sets. Talk about differences and use cases.
* Statements and Functions: if, while, for, lambda, filter, sorted, map, dir, help, pdb
* something to code in class
* something to take home.

Setup:
------
1. Clone the git repo
2. Make sure python is installed (type python in the command line, it should open up an interpreter)
3. Navigate to the 1-Intro directory
4. Run ```python -m unittest test_intro``` in your powershell(windows) or terminal(mac) to ensure everything is configured correctly
5. open up test_intro.py and intro.py in your favourite editor, and begin the workshop



Python's built-in types:
------------------------
http://en.wikipedia.org/wiki/Python_(programming_language)#Typing

Statements and Functions:
----------------

### Dissection of a python function

```python

def spam(name, firstword='hello', secondword='world', *args, **kwargs):
	'''Prints a string with two words and a name

    Args:
        name: The name of the user
        firstword: The first word in the sequence, defaulting to 'hello'
        secondword: The second word in the sequence, defaulting to 'world'

    Returns:
        A tuple containing all three strings

    Raises:
        NameError: Only occurs when user named Vimal attempts to use this function
    '''

    if name=='Vimol':
    	raise NameError('VI')

    spam_tuple = (firstword, secondword, name)
	print "%s %s, %s" % spam_tuple

	return spam_tuple

```

### Function Arguments

The first thing you will notice about the arguments is that python is **dynamically typed**. Type checking is performed at run-time as opposed to compile time.

Now lets look at each argument, and the special properties and syntax of each one:

* *name* is a mandatory argument
* *firstword* and *secondword* are both **default argument values**, this means that the argument is optional, and a default value is assumed when no value is specified
* *args* is an **arbitrary argument list**, this means that our function can be called with an arbitrary number of arguments
* *kwargs* is a dictionary containing all keyword arguments except our formal parameters specified.

Try the following calls to spam:

```python
spam('Alex')
spam(name='Alex')
spam('Alex', 'Hey', 'Globe')
spam(firstword='Hey', name='Alex', secondword='Globe')
spam('Alex', 'Hey', 'Globe', 'WTF?')
spam(firstword='Hey', name='Alex', secondword='Globe', crazyvar='WTF?')
```

####The Magic of Lambda Functions

```python
magic = lambda x: x*2

print magic(2)
```

Try it out, see what happens.

Here's how we could accomplish the same thing without a lambda function

```python
def magic(x):
    return x*2

print magic(2)
```

Lambda Functions (or Anonymous Functions) are functions that are not bound to a name--- and are frequently used with other built in functions such as map() and filter()

####Built-in python functions - Map, Filter

For the full list, check out: 
http://docs.python.org/library/functions.html