## 2. MATLAB Fundamentals

The objective of this class is to familiarize yourself with some of the fundamentals of MATLAB programming, including:
* Variables, operators, and expressions
* Arrays (including vectors and matrices)
* Operators
* Repetition (`for`)

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
>> b .^ a
```
MATLAB has some additional arithmetic operators, as shown in Table 2.3 that work on corresponding elements of arrays with equal dimensions. They are called _array_ or _element-by-element_ operations because they are performed element by element. For example, `a .* b` results in the following vector,
```
[a(1)*b(1) a(2)*b(2) a(3)*b(3)]
```
which is, `[2 4 12]`.

**Table 2.3** Arithmetic operators that operate element-by-element on arrays.

| Operator | Description |
|:-------- |:----------- |
| `.*` | Multiplication |
| `./` | Division |
| `.^` | Power |

The period (dot) is necessary for the array operations of multiplication, division, and exponentiation because these operations defined differently for matrieces (so-called _matrix operations_). For addition and subtraction, array operations and matrix operations are the same, so we do not need the period to distinguish them.

Array operations also apply between a scalar and a nonscalar. Try `2 .* a` and `a .^ 2` at the command line. This property is called _scalar expansion_. Multiplication and division operations between scalars and nonscalars can be written with or without the period. 

With arry operations, you can easily evaluate a formula repeatedly for a large set of data. This is one of MATLAB's useful features, and you should always look for ways to exploit it. Let's consider, as an example, the calculation of compound interest. An amount of money _A_ invested over a period of years _n_ with an annual interest rate _r_ grows to an amount _A_(1+_r_)<sup><i>n</i></sup>. Suppose we want to calculate final balances for investments of $750, $1000, $3000, $5000, and $11,999 over 10 years with an interest rate of 9%. The following program uses array operations on a vector of initial investments to do this:
```
format bank
A = [750 1000 3000 5000 11999];
r = 0.09;
n = 10;
B = A * (1+r) ^ n;
disp( [A' B'])
```
Here `format bank` set the output to use currency format with 2 digits after the decimal point. `disp` shows the content of the array in its brackets.

The output is 
```
  750.00       1775.52
 1000.00       2367.36
 3000.00       7102.09
 5000.00      11836.82
11999.00      28406.00
```

### _Exercises_

2.12 If _C_ and _F_ are Celsius and Fahrenheit temperatures, respectively, the formula for conversion from Celsius to Fahrenheit is _F_ = 9 _C_ / 5 + 32.

(a) Write a script that will take the Celsius temperature and display the Fahrenheit equivalent with some sort of comment, such as

`The Fahrenheit temperature is: ...`

Try it out on the following Celsius temperatures (answers in parentheses): 0 (32), 100 (212), -40 (-40), 37 (98.6).

(b) Change the script to use vectors and array operations to compute the Fahrenheit equivalents of Celsius temperatures ranging from 20<sup>o</sup>C to 30<sup>o</sup>C in steps of 1<sup>o</sup>C, and display them in two columns with a heading, like this:
```
Celsius   Fahrenheit
20.00     68.00
21.00     69.80
...
30.00     86.00
```

### Repeating with `for`

_Repetition_ is implemented by the `for` construct. Let's look at a couple of examples of its use, followed by explanations.

#### Example 1

For starters, enter the following group of statements on the command line. Enter the command `format compact` first to make the output neeter:
```
for i = 1:5
     disp(i)
end
```
Then change it slightly to
```
for i = 1:3
     disp(i)
end
```
So the `disp` statement is repeated five times and three times.

#### Example 2

{% include mathjax.html %}

Run the following program to generate a list of _n_ and _n!_ ("_n_ factorial"). where
\\[
n! = 1 \times 2 \times 3 \times ... \times (n-1) \times (n)
\\]

```
n = 10;
fact = 1;
for k = 1:n
    fact = k * fact;
    disp( [k fact] )
end
```


In general the most common form of the `for` loop is
```
for index = j:k
    statements;
end
```
or
```
for index = j:m:k
    statements;
end
```
The `for` construct above executes a group of statements in a loop for a specified number of times. 
 
* `j:k` -- this form increments the index variable from `j` to `k` by 1, repeating the execution of statements until index is greater than `k`.

* `j:m:k` -- this form increments index by the value `m` on each iteration, or decrements index when `m` is negative.

