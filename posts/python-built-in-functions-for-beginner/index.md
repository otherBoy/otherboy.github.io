# Python Build-in Functions for Beginner


Build-in Functions are functions which provided by Python interpreter, and that are always available. There are 69 build-in functions till Python 3.9.  
In this blog, we selected 59 important build-in functions for Python beginners, and classified them into 8 main categories.  

### 1. Numerical 
##### Type
**bool(x)**: Return a Boolean value, True or False  
**int(x, base=10)**: Return an integer object constructed from a number or string, or return 0 if no arguments are given. Base is optional, base 0 means to interpret exactly as a code literal, so that the actual base is 2, 8, 10, or 16  
**float(x)**: Return a floating point number constructed from a number or string  
**complex(x)**: Return a complex number with the value real + imag\*1j or convert a string or number to a complex number  

```
>>> bool(10)
True
>>> int('10')
10
>>> float(10)
10.0
>>> complex(10)
(10+0j)
```

##### Conversion
**bin(x)**: Convert an integer number to a binary string prefixed with “0b”  
**oct(x)**: Convert an integer number to an octal string prefixed with “0o”  
**hex(x)**: Convert an integer number to a lowercase hexadecimal string prefixed with “0x”  

```
>>> bin(3)
'0b11'
>>> oct(8)
'0o10'
>>> hex(255)
'0xff'
```

##### Math
**abs(x)**: Return the absolute value of a number  
**divmod(x, y)**: Take two (non complex) numbers as arguments and return a pair of numbers consisting of their quotient and remainder when using integer division  
**round(x[, ndigits])**: Return number rounded to ndigits precision after the decimal point, ndigits is optional, if ndigits is omitted or is None, it returns the nearest integer to its input  
**pow(base, exp[, mod])**: Return base to the power exp; mod is optional, if mod is present, return base to the power exp, modulo mod  
**sum(iterable[,start])**: Sums start and the items of an iterable from left to right and returns the total  
**min()**: Return the smallest item in an iterable or the smallest of two or more arguments  
**max()**: Return the largest item in an iterable or the largest of two or more arguments  

```
>>> abs(-1)
1
>>> round(2.675, 2)
2.67

>>> pow(10, 2)
100
>>> pow(10, 2, 3)
1

>>> sum([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
55

>>> min(5, 3, 9, 12, 7, 2)
2
>>> min([5, 3, 9, 12, 7, 2])
2
>>> max(7, 3, 15, 9, 4, 13)
15
```

### 2. Data Structure
#####  Sequence
**list(iterable)**: Convert an iterable object to a list  
**tuple(iterable)**: Convert an iterable object to a list  
**range([start,] stop[, step])**: Returns a sequence of numbers, starting from 0 by default, and increments by 1 by default, and stops before a specified number, start and step are optional  
**reversed(seq)**: Return a reverse iterator, seq must be an object which has a \_\_reversed\_\_() method or supports the sequence protocol  
**slice(start, stop[, step])**: Return a slice object representing the set of indices specified by range(start, stop, step), step is optional  

```
>>> list((1, 2, 3, 4, 5, 6))
[1, 2, 3, 4, 5, 6]
>>> tuple([1, 2, 3, 4, 5, 6])
(1, 2, 3, 4, 5, 6)

>>> for n in range(3, 20, 2):
...     print(n)
3
5
7
9
11
13
15
17
19

>>> list(reversed('abcdefg'))
['g', 'f', 'e', 'd', 'c', 'b', 'a']

>>> a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> a[slice(1, 3, 1)]
[2, 3]
```

##### String
**str(object)**: Return a string version of object. If object is not provided, returns the empty string  
**format(value[, format_spec])**: Convert a value to a “formatted” representation, as controlled by format_spec, [Format Spec Details](https://docs.python.org/3/library/string.html#formatspec)  
**bytes([source[, encoding[, errors]]])**: Return a new “bytes” object, which is an immutable sequence of integers in the range 0 <= x < 256  
**bytearray([source[, encoding[, errors]]])**: Return a new array of bytes. The bytearray class is a mutable sequence of integers in the range 0 <= x < 256  
**ord(c)**: Given a string representing one Unicode character, return an integer representing the Unicode code point of that character  
**chr(i)**: Return the string representing a character whose Unicode code point is the integer  
**ascii(obj)**: return a string containing a printable representation of an object, but escape the non-ASCII characters in the string returned by repr() using \x, \u or \U escapes  
**repr(obj)**: Return a string containing a printable representation of an object  

```
>>> str(1234)
'1234'
>>> format(3, 'b')
'11'
>>> format(97, 'c')
'a'
>>> format(11, 'd')
'11'
>>> format(11, 'o')
'13' 
>>> format(11, 'x')
'b'
>>> format(11, 'X')
'B'
>>> format(11, 'n')
'11'
>>> format(123456789, 'e')
'1.234568e+08'
>>> format(123456789, '0.2e')
'1.23e+08'
>>> format(123456789, '0.2E')
'1.23E+08'
>>> format(1.23456789, 'f')
'1.234568'
>>> format(1.23456789, '0.2f')
'1.23'
>>> format(1.23456789, '0.10f')
'1.2345678900'
>>> format(1.23456789e+3, 'F')
'1234.567890'

>>> bytes("哈哈哈", encoding='utf-8')
b'\xe5\x93\x88\xe5\x93\x88\xe5\x93\x88'
>>> bytearray("hello world" ,encoding ='utf-8')
bytearray(b'hello world')
>>> bytearray("hello world" ,encoding ='utf-8')[0]
104

>>> ord('a')
97
>>> chr(100)
'd'
>>> ascii("w")
"'w'"
>>> repr('hello world')
"'hello world'"
```

##### Collection
**dict()**: Create a new dictionary  
**set()**: Return a new set object, optionally with elements taken from iterable  
**frozenset([iterable])**: Return a new frozenset object, optionally with elements taken from iterable

```
>>> dict({'a': 1, 'b': 2, 'a': 3})
{'a': 3, 'b': 2}
>>> set([1, 1, 2, 2, 3])
{1, 2, 3}
>>> frozenset([1,1,2,2,3])
frozenset({1, 2, 3})
```

### 3. Operation
**len(obj)**: Return the length (the number of items) of an object  
**sorted(iterable, key=None, reverse=False)**: Return a new sorted list from the items in iterable. Key and reverse are optional. Key specifies a function of one argument that is used to extract a comparison key from each element in iterable, reverse is a boolean value  
**enumerate(iterable, start=0)**: Return an enumerate object. iterable must be a sequence, an iterator, or some other object which supports iteration  
**all(iterable)**: Return True if all elements of the iterable are true (or if the iterable is empty)  
**any(iterable)**: Return True if any element of the iterable is true. If the iterable is empty, return False  
**zip()**: Returns an iterator of tuples, where the i-th tuple contains the i-th element from each of the argument sequences or iterables  
**filter(function, iterable)**: Construct an iterator from those elements of iterable for which function returns true. iterable may be either a sequence, a container which supports iteration, or an iterator. It is equivalent to the generator expression (item for item in iterable if function(item)) if function is not None and (item for item in iterable if item) if function is None  
**map()**: Return an iterator that applies function to every item of iterable, yielding the results  

```
>>> len([1, 2, 3, 4, 5, 6])
6

>>> sorted([5, 7, 6, 12, 1, 13, 9, 18, 5])
[1, 5, 5, 6, 7, 9, 12, 13, 18]
>>> sorted([5, 7, 6, 12, 1, 13, 9, 18, 5], reverse=True)
[18, 13, 12, 9, 7, 6, 5, 5, 1]

>>> list(enumerate(['Spring', 'Summer', 'Fall', 'Winter']))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

>>> all([1, 'hello', True, 0])
False
>>> all([1, 'hello', True, 9])
True
>>> any([0, 0, 0, False, 1, 'hello'])
True

>>> list(zip([1, 2, 3], [4, 5, 6]))
[(1, 4), (2, 5), (3, 6)]

>>> def func(i):
...    return i % 2 == 1
>>> list(filter(func, [1, 2, 3, 4, 5, 6, 7, 8, 9]))
[1, 3, 5, 7, 9]

>>> def f(i):   
...   return i + 1
>>> list(map(f, [1, 2, 3, 4, 5, 6, 7]))
[2, 3, 4, 5, 6, 7, 8]
>>> 
```

### 4. Namespace
**locals()**: Update and return a dictionary representing the current local symbol table  
**globals()**: Return a dictionary representing the current global symbol table  

### 5. Iterator
**next(iterator[, default])**: Retrieve the next item from the iterator by calling its \_\_next\_\_() method. If default is given, it is returned if the iterator is exhausted, otherwise StopIteration is raised.  
**iter()**: Return an iterator object  

```
>>> a = iter([1, 2, 3, 4, 5])
>>> next(a)
1
>>> next(a)
2
>>> next(a)
3
>>> next(a)
4
>>> next(a)
5
>>> next(a)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```

### 5. Interpreter
**eval(expression[, globals[, locals]])**: The expression argument is parsed and evaluated as a Python expression (technically speaking, a condition list) using the globals and locals dictionaries as global and local namespace  
**exec(obj[, globals[, locals]])**: This function supports dynamic execution of Python code. object must be either a string or a code object. If it is a string, the string is parsed as a suite of Python statements which is then executed (unless a syntax error occurs). If it is a code object, it is simply executed  
**compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)**: Compile the source into a code or AST object. Code objects can be executed by exec() or eval(). source can either be a normal string, a byte string, or an AST object  

```
>>> x = 1
>>> eval('x + 1')
2

>>> s = "for i in range(5): print(i)"
>>> exec(s)
0
1
2
3
4

>>> com = compile("5 + 6 + 7", "", mode="eval")
>>> eval(com)
18
```

### 6. IO
**print(\*objects, sep=' ', end='\n', file=sys.stdout, flush=False)**: Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments  
**input()**: The function then reads a line from input, converts it to a string (stripping a trailing newline), and returns that. When EOF is read, EOFError is raised  
**open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)**: Open file and return a corresponding file object. If the file cannot be opened, an OSError is raised

```
>>> print("hello", "world", sep="_", end="!")
hello_world!

>>> s = input('--> ') 
--> Hello world!
>>> s
'Hello world!'

>>> f = open('file', mode='r', encoding='utf-8')
>>> f.read()
>>> f.close()
```

### 7. RAM
**hash(obj)**: Return the hash value of the object (if it has one). Hash values are integers  
**id(obj)**: Return the “identity” of an object. This is an integer which is guaranteed to be unique and constant for this object during its lifetime  
**memoryview(obj)**: Create a memoryview that references object. object must support the buffer protocol  
**object()**: Return a new featureless object. object is a base for all classes  
**isinstance(obj, classinfo)**: Return True if the object argument is an instance of the classinfo argument, or of a (direct, indirect or virtual) subclass thereof  
**issubclass(class, classinfo)**: Return True if class is a subclass (direct, indirect or virtual) of classinfo. A class is considered a subclass of itself  
**type(obj)**: Return the type of an object  

```
>>> hash("hello world")
-9210861515036063026

>>> s = "hello world"
>>> id(s)
140669275673392

>>> a = memoryview(bytes(b'hello world'))
>>> a[0]
104
>>> a[1]
101

>>> object()
<object object at 0x7ff01c5961e0>
>>> isinstance('hello world', int)
False
>>> isinstance('hello world', str)
True
>>> issubclass(str, object)
True
>>> type(100)
<class 'int'>
```

### 8. System
**\_\_ import\_\_(name, globals=None, locals=None, fromlist=(), level=0)**: The function imports the module name, potentially using the given globals and locals to determine how to interpret the name in a package context  
**help(obj)**: Invoke the built-in help system  
**callable(obj)**: Return True if the object argument appears callable, False if not. If this returns True, it is still possible that a call fails, but if it is False, calling object will never succeed  
**dir(obj)**: Without arguments, return the list of names in the current local scope. With an argument, attempt to return a list of valid attributes for that object  

```
>>> help(str)

>>> a = 100
>>> callable(a)
False
>>> def f():
...     return 100
>>> callable(f)
True

>>> dir(tuple)
```

