#HSLIDE
<img src="http://www.cakex.org/sites/default/files/National_Conservation_Training_Center.gif" width="200">
<img src="https://www.python.org/static/img/python-logo.png" width="400">
#### Python for Advanced GIS
#### NCTC CSP7300
<br>
<span style="color:gray">NCTC Advanced GIS</span>
<br>
<span style="color:gray">Daryl Van Dyke</span>

#HSLIDE
#### Python for Advanced GIS
#### NCTC CSP7300
<br>
<span style="color:gray">https://github.com/GeospatialDaryl/AdvGIS_Python_Part1</span>
<br>
<span style="color:gray">https://gitpitch.com/GeospatialDaryl/AdvGIS_Python_Part1</span>

#HSLIDE
## Major Language Elements
* Hello, World!
* Variables and Types
* Lists
* Basic Operators
* String Formatting
* Basic String Operations

#HSLIDE
## Statements
### Assignment `=`
We recall:

1.  All python things are objects.

2.  All objects have classes - that is, **they are an instance of a class.**

  + Python has two fundamental flavors of objects.  Mutable and immutable.

#HSLIDE
## List Indexing
Call it by it's position, 0-index.
```python
>>> listE = ["abba", 3, False]
>>> listE[0]
'abba'
>>> listE[-1]
False
>>> listE[0:1]
['abba']
>>> listE[0:2]
['abba', 3]
>>>
```
#HSLIDE
## More common ```list``` methods and functions
```python
>>> #Nested list
>>> listF = ["Oh NO!", "This is too much!", True]
>>> listE.append(listF)
>>> listE
['Iron Maiden', 3, False, 'this String', ['Oh NO!', 'This is too much!', True]]
>>> #Appended list
>>> listF = ["Oh NO!", "This is too much!", True]
>>> listEF = listE + ListF
>>> listEF
['Iron Maiden', 3, False, 'this String', 'Oh NO!', 'This is too much!', True]
>>>
```
#HSLIDE
## Statements
### Assignment *=* ... in Python
- ```x = 2``` - *in Python* - means:
"(generic) name x receives a reference to a separate, dynamically allocated object of numeric (int) type of value 2."
<img src="http://archive.oreilly.com/oreillyschool/courses/Python1/images/lessons/ModuleVsObjectSpace.jpg">
***This is termed binding the name to the object.***
