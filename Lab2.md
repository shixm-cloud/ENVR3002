## 2. MATLAB Fundamentals

The objective of this class is to familiarize yourself with some of the fundamentals of MATLAB programming, including:
* Variables, operators, and expressions
* Arrays (including vectors and matrices)
* Operators
* Basic input and output

The contents of this class prepare you for a large portion of the coding projects in this course.

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

pressure  rain_rate  temperature  
```

These variables remain in the workspace until you use the command `clear` to delete them. the command `whos` lists the size of each variable as well,
```
Name        Size  Bytes  Class  Attributes
pressure    1x1   8      double
rain_rate   1x1   8      double
temperature 1x1   8      double
```
You can see that each variable here occupies eight _bytes_ of storage. Interestingly, their sizes are `1x1`. This is because MATLAB refers to all variables as _arrays_. A single-valued variable (_scalar_) is a 1-by-1 array -- an array with a single row and a single column. 

The command `clear` removes all variables from the workspace. A particular variable can be removed from the workspace (e.g. `clear rain_rate`, `clear rain_rate pressure`). The Workspace browser on the desktop provides a handy visual representation of the workspace.

### Vectors

The name MATLAB stands for _Matrix Laboratory_ because it has been designed to work with _matrices_. A matrix is a rectangular object consisting of rows and columns (e.g. a _table_). A _vector_ is a special type of matrix, having only one row or one column. MATLAB handles vectors and matrices in the same way, but because vectors are easier to think about than matrices, we start with them first. As mentioned above, MATLAB refers to scalars, vectors, and matrices generally as arrays. Vectors are one-dimensional (1D) arrays.

You can initialize vectors with _explicit lists_. Try the exercises below on the command line. 

### _Exercises_

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

A vector can also be generated with the _colon operator_. `x = j:k` creates a unit-spaced vector `x` with elements `[j,j+1,j+2,...,k]`. `x = j:i:k` creates a regularly-spaced vector `x` using `i` as the increment between elements. The vector elements are roughly equal to `[j,j+i,j+2*i,...,k]`. Try the following statements.
```
>> x = 1:10
>> x = 1:0.5:5
>> x = 1:2:8
>> x = 5:-1:-5
```
Another convenient tool to create 1D array is `linspace`. You can type `help linspace` in MATLAB to see how to use it.

All of the vectors we examined so far are _row vectors_. Each has one row and several columns. To generate _column vectors_ you need to _transpose_ row vectors. This is done with the single quote, or _apostrophe_ (`'`). 

Enter `x = 1:5` and then enter `x'` to display the transpose of `x`. Note that `x` itself remains a row vector. If you want to store the transposed vector, you need to create a new one, e.g., `y = x'`. You can also create a column vector directly:
```
>> y = [1 2 3 4 5]'
```

### Subscripts

We can refer to particular elements of a vector by means of _subscripts_. Complete the following exercise to see how subscripts work.

### _Exercises_

2.7 Enter `time = [0:23]`. This gives you a row vector of the 24 hours.

2.8 Enter `time(3)`. Here `3` is is the _subscript_. Which element of `time` do you get, the second or the third?

2.9 Try `time(1:5)` and `time(6:9)`. Which elements do you get? Can you see why? _(hint: we used the colon operator here)_

2.10 What about `time(1:6:end)` and `time([1 7 2 5])`? _(Yes, you can use `end` to replace 23, the subscript of the last element here. Isn't that cool?)_

To summarize:
* A subscript is indicated by parenthese.
* A subscript may be a scalar or a vector.
* In MATLAB subscripts always start at 1.
* Subscripts are always integers, i.e., fractional subscripts are not allowed.

### Matrices

A _matrix_ may be thought of as a table consisting of rows and columns. You can create a matrix using _explicit lists_, just like the way you create vectors, except that a semicolon is used to indicate the end of a row. For example,
```
>> a = [1 2 3; 4 5 6]
```
results in 
```
a =

     1     2     3
     4     5     6
```

A matrix may be transposed, for example, the statement `a' ` results in
```
ans =

     1     4
     2     5
     3     6
```

The elements of a matrix can be accessed with _subscripts_. Try the following statements to see which elements of `a` you are accessing.
```
>> a(2,3)
>> a(:,2)
>> a(1,:)
```
You will find that the colon operator here basically represents `1:end`, all subscripts available in that dimension.

### Numbers

As we have learned, numbers can be represented in MATLAB in the usual decimal form (_fixed point_) with an optional decimal point, such as `1.234`, `-123`, `.001`.

They may also be represented in _scientific notation_. For example, 1.234 <span>&#215;</span> 10<sup>5</sup> may be represented as `1.234e5`. This is also called _floating-point_ notation. The number has two parts: _mantissa_, which may have an optional decimal point (`1.234` in this example) and the _exponent_ (`5`), which must be an integer (signed or unsigned). mantissa and exponent must be separated by the letter `e` (or `E`). The mantissa is multiplied by the power of 10 indicated by the exponent.

### Arithmetic operators

The arithmetic operations on two _scalar_ constants or variables are shown in Table 2.1. Operators operate on _operands_ (`a` and `b` in the table).

**Table 2.1** Arithmetic operations between two scalars

| Operation      | Algebraic form | MATLAB  |
|:-------------- |:--------------:|:-------:|
| Addition       |  a + b         | `a + b` |
| Subtraction    |  a - b         | `a - b` |
| Multiplication |  a <span>&#215;</span> b | `a * b` |
| Division       |  a <span>&#247;</span> b | `a / b` |
| Power          |  a<sup>b</sup> | `a ^ b` |

Several operations may be combined in one expression -- for example, `a * b ^ c`. MATLAB has strict precedence rules for which operations are performed first in such cases. The rules for the operators in Table 2.1  are shown in Table 2.2. Note that parentheses have the hightest precedence.

**Table 2.2** Precedence of arithmetic operations

| Precedence | Operator |
|:---------- |:-------- |
| 1 | Parentheses (round brackets) |
| 2 | Power, left to right |
| 3 | Multiplication and division, left to right |
| 4 | Addition and subtraction, left to right |

### _Exercises_

2.11 Evaluate the following MATLAB expressions yourself before checking the answers in MATLAB
```
>> 1 + 2 * 3
>> 4 / 2 * 2
>> 1 + 2 / 4
>> 2 * 2 ^ 3
>> 2 ^ (1 + 2)/3
```

### Arithmetic operations on arrays

Enter the following statements at the command line:
```
>> a = [1 2 3];
>> b = [2 2 4];
>> a .* b
>> a ./ b
```
MATLAB has four additional arithmetic operators, as shown in Table 2.3 that work on corresponding elements of arrays with equal dimensions. They are called  




