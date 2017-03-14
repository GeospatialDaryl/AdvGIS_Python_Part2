# Exercise 1:

## Purpose
The purpose of this exercise is to enable you to identify a component of your project analysis, and translate that into a scripting element.
We will do this by setting up a common function using an ArcPy call (or any geoprocessor you want) and then iterating over a list with it.

We will want to define a function:
- which has purpose (a job),
- with defined inputs and outputs,
- and a clearly defined scope (what info does it need to 'see'/access).

## Step 1:  Function Design
1. Create a script file, version it, and define your function in comments.
2. Place the function in the proper 'place' on your script.  This determines the scope it sees.
3. Add the def statement, docstrings, and the return statement.
4. Now, populate the function.
5. Use a single call to test it, and run it from the command-line with a single input (a FC).
6. Debug, and get the function working correctly.
##  Step 2: Implement in ArcPy in ArcMap
1. Open the Python window, and paste in the whole function declaration.
2. Test the function by processing a single input.
3. Then, select a number of feature classes of the same geometry from you table of contents, and drag-n-drop them into the python window.
4. The names of the feature classes will be automatically packed in to a list.
5. Use the `for` construct to iterate through the list.
```python
  for items in listFC:
    ...do something...
```

## Hints:
Arcpy calls a bit wierd, but here's an example:
From ArcPy Help:  
`Buffer_analysis (in_features, out_feature_class, buffer_distance_or_field, {line_side}, {line_end_type}, {dissolve_option}, {dissolve_field}, {method})`.

This becomes:   
`arcpy.Buffer_analysis(inFC, outFC, 10)`

Remember:  Use the run in ArcMap, R-Click-Copy Python snippet from Results.
Paste in text editor.

Profit.
