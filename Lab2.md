## 2. MATLAB Fundamentals

The objective of this class is to familiarize yourself with some of the fundamentals of MATLAB programming, including:
* Variables, operators, and expressions
* Arrays (including vectors and matrices)
* Basic input and output
* Repetition (`for`)
* Decision (`if`)

The contents of this class prepare you for coding projects in this course.

### Variables

A variable name must comply with the following two rules:
* It may consist only of the letters `a-z`, the digits `0-9`, and the underscore (`_`)
* It must start with a letter

A variable is created simply by assigning a value to it at the command lind or in a program -- for example, 
```
>> rain_rate = 100
>> temperature = 23
>> pressure = 1000
```

MATLAB is _case-sensitive_, which means it distinguishes between upper- and lowercase letters. Thus, `temperature`, `TEMPERATURE`, and `Temperature` are three different variables.  

### Workspace

Another fundamental concept in MATLAB is _workspace_. If you type in the three variables above and now enter the command `who`. You should see a list of variables as follows.
```
Your variables are:

pressure     rain_rate    temperature  
```

These variables remain in the workspace until you use the command `clear` to delete them. the command `whos` lists the size of each variable as well,
```
Name             Size            Bytes  Class     Attributes

pressure         1x1                 8  double              
rain_rate        1x1                 8  double              
temperature      1x1                 8  double   
```
You can see that each variable here occupies eight _bytes_ of storage. Interestingly, their sizes are `1x1`. This is because MATLAB refers to all variables as _arrays_. A single-valued variable (_scalar_) is a 1-by-1 array -- an array with a single row and a single column.

The command `clear` removes all variables from the workspace. A particular variable can be removed from the workspace (e.g. `clear rain_rate`, `clear rain_rate pressure`). The Workspace browser on the desktop provides a handy visual representation of the workspace.

### Vectors

The name MATLAB stands for _Matrix Laboratory_ because it has been designed to work with _matrices_. A matrix is a rectangular object consisting of rows and columns (e.g. a _table_). A _vector_ is a special type of matrix, having only one row or one column. MATLAB handles vectors and matrices in the same way, but because vectors are easier to think about than matrices, we start with them first. As mentioned above, MATLAB refers to scalars, vectors, and matrices generally as arrays. Vectors are one-dimensional (1D) arrays.

You can initialize vectors with _explicit lists_. Try the exercises below on the command line. 

#### Exercises

2.1 Enter a statement like
```
>> t = [15 18 20 21 17]
```
This is a list of temperature values. Can you see that you have created a vector with five elements?

2.2 Enter the command `disp(t)` to see how MATLAB display a vector.

2.3 Ener the command `whos` (or look in the Workspace brower). Under the heading `Size` you will see that `t` is 1 by 5, which means 1 row and 5 columns.

2.4 You can sue commas instead of spaces between vector elements if you like.
```
>> t = [15,18,20,21,17]
```

2.5 You can use one vector in a list for another one. Try the following:
```
>> a = [1 2 3]
>> b = [4 5]
>> c = [a b]
```
Can you work out what `c` looks like before displaying it?

2.6 What about this?
```
>> a = [2 1 0]
>> a = [a -1 -2]
```




