#HSLIDE
<img src="http://www.cakex.org/sites/default/files/National_Conservation_Training_Center.gif" width="200">
<img src="https://www.python.org/static/img/python-logo.png" width="400">
#### Python for Advanced GIS
<br>
<span style="color:gray">NCTC Advanced GIS</span>
<br>
<span style="color:gray">Daryl Van Dyke</span>

#HSLIDE
## Major Language Elements
- Package Management with `pip`
- Assignment and Reassignment
- Flow Control
- Dictionaries, Sets, and Iterables
- Modules and Reusable code

#HSLIDE
## `pip` Package manager
Package management is awesomesauce!
0. https://pypi.python.org/pypi
1.  Open a CMD with WinFlag + "cmd"
2. Type `pip install pymodis`
3. Type `pip --trusted-host pypi.python.org install pymodis`
4. Profit

#HSLIDE
## Type conversion
```python
>>> a = 1
>>> thisFileName = "Sweet_NetCDF_num"+a

Traceback (most recent call last):
  File "<pyshell#3>", line 1, in <module>
    thisFileName = "Sweet_NetCDF_num"+a
TypeError: cannot concatenate 'str' and 'int' objects
>>> thisFileName = "Sweet_NetCDF_num"+str(a)
>>> thisFileName
'Sweet_NetCDF_num1'
>>>
```
#HSLIDE
### Typing
- Duck Typing
- Dynamic Typing
- Strongly typed

Python is "strongly typed" = it does not do implicit type conversion.
Type error = Crash (an Exception)

#HSLIDE
### Typing
This is not "static typing" - we can change the type of a variable by re-referencing it, and the compiler doesn not check ahead of time.

The term 'duck typing' is now used to describe the dynamic typing paradigm used by the languages in this group.


#HSLIDE
##  Assignment
3. Assignment (token `=`, the equals sign).
  + Different than other C-style languages (C, Java, C++, etc).
  + Assignment in C, e.g., `x = 2`, translates to "typed variable name x receives a copy of numeric value 2".  

#HSLIDE
## Assignment
<img src="https://i.stack.imgur.com/M3iZD.png" width=500>

#HSLIDE
## Assignemnt: A Subtlety - C/Java vs. Python
1. The memory for this element (determined by data type and width) is allocated,
2. the data are copied over,
3. and the *variable name* is an alias or symbolic address for that memory location.  
4. Therefore, pointers, addresses, referencing, de-referencing, and pointer arithmetic.

#HSLIDE
## Statements
### Assignment *=* ... in Python
- ```x = 2``` - *in Python* - means:
"(generic) name x receives a reference to a separate, dynamically allocated object of numeric (int) type of value 2."
<img src="http://archive.oreilly.com/oreillyschool/courses/Python1/images/lessons/ModuleVsObjectSpace.jpg">
***This is termed binding the name to the object.***

#HSLIDE
### Assignment
 To be technical - they aren't variables.  They are names bound to objects.

 Names may be subsequently rebound at any time to objects of greatly varying types...
 * strings,
 * procedures,
 * complex objects with data and methods, etc.

#HSLIDE
### Assignment
OK - what happens?
```python
x = 2
y = 2
z = 2
```

#HSLIDE
### Assignment
`x = 2; y = 2; z = 2`
three names and one numeric object,
to which all three names are bound.

#HSLIDE


#HSLIDE
### Assignement
Since a name is a generic reference holder it is unreasonable to associate a fixed data type with it.

However at a given time a name will be bound to some object, which will have a type;
***thus there is dynamic typing.***


#HSLIDE
## Python Type Conversions
Function|Description|
--------|-----------|
int(x [,base])|Converts x to an integer. base specifies the base if x is a string.|
long(x [,base] )|Converts x to a long integer. base specifies the base if x is a string.|
float(x)|Converts x to a floating-point number.|
complex(real [,imag])|Creates a complex number.|
str(x)|Converts object x to a string representation.|

#HSLIDE
##  Naming some files example
Imagine we already have a great function `writeMyData(inputFile)`
```python
# in python, we can use `r"..."` to force raw strings
# *Always* do this for paths - works for Windows and Nixes
indxPolarBear = [1,2,3]
pathToOutputs = r"D:/AwesomesaucePolarBearHatchery/"
for bears in indxPolarBear:
	# do a bunch of stuff with your bear data
	thisFile = pathToOutputs+"PolarBear"+str(bears)
	# writeMyData(thisFile)
  print "Bear model "+thisFile+" finished processing."
```

#HSLIDE
### Assignment
Since it is just a name, pick a good one.  While you can do all of the above, why not?
Well, there are very good (and very advanced) reasons to do this... object polymorphism, for one.

Class inheritance and class hierarchies, another.

#HSLIDE
## A Simple Program - Shell mode
```python
>>> # Fibonacci series:
... # the sum of two elements defines the next
... a, b = 0, 1
>>> while b < 10:
...     print b
...     a, b = b, a+b
...
1
1
2
3
5
8
```
`print`, `while`, multiple assignement

#HSLIDE
## Flow Control 1: `if`
```python
>>> x = int(raw_input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print 'Negative changed to zero'
... elif x == 0:
...     print 'Zero'
... elif x == 1:
...     print 'Single'
... else:
...     print 'More'
...
More
```
#HSLIDE
## `if` Bonus Round
`elif` - chains of if
`else` - optional end to if-then chain

Other languages have a `switch` or `case` logical block.
Python uses `if ... elif ... elif ... (else)` structure.

#HSLIDE
## `for`
`for` in Python iterates over iterable objects (containers).
Not based on arithemic or logical conditions.
```python
>>> # Measure some strings:
... words = ['cat', 'window', 'defenestrate']
>>> for w in words:
...     print w, len(w)
...
cat 3
window 6
defenestrate 12
```
#HSLIDE
## `range()` function
`range()` generates arithmetic progressions.
Can have 1, 2, or 3 arguments.
1.  implicit start 0, argument is # of entries generated.
This will **not** include the #.
```python
>>> range(10)
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

#HSLIDE
## `range()` function
2.  1st argument start, 2nd argument "stop" position.
Python "stops" before it gets to the value.
```python
>>> range(5, 10)
[5, 6, 7, 8, 9]
```

#HSLIDE
## `range()` function
3.  Start, Stop, and Step
Like 2, but it specifies a step-size
```python
>>> range(0, 10, 3)
[0, 3, 6, 9]
>>> range(-10, -100, -30)
[-10, -40, -70]
```

#HSLIDE
## Putting them together...
remember `len()`?
```python
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print i, a[i]
...
0 Mary
1 had
2 a
3 little
4 lamb
```

#HSLIDE
## `break` and `continue`
`break` steps out 1 logical block from the enclosing `for` or `while` loop.
```python
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:  # % is modulus.  It is the whole number from division
...             print n, 'equals', x, '*', n/x
...             break
...     else:
...         # loop fell through without finding a factor
...         print n, 'is a prime number'
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
```

#HSLIDE
# #

#HSLIDE
##Great Job, Folks
That was a lot, but it is the core of learning the Python language.
We have:
* Basic types
* Assignment
* Flow control
* Some standard library functions and statements
  + `def`
  + `print` vs. `print()`
  + `len()`
  + ``
