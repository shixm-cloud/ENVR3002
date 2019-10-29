## Coding Lecture 1  Introduction

This is the first class of our coding lecture series. We will learn some basics about MATLAB today.

MATLAB is a software for scientific computing. The name stands for _matrix laboratory_. It can handle simple arithmetic calculations like those your scientific calculator can do, as well as complex machine learning algorithms that aids the design of BMW automobiles.

Next, let's take a look at the sofeware interface first (_Lecture show MATLAB on the computer ..._)

### Arithmetic

Now let's examine MATLAB by doing some simple arithmetic. This help us gain confidence and intuiation in this computing tool we are going to use. 

Type `2+6` after the `>>` prompt, followed by **Enter**
```
>> 2+6 
```
The commands are executed only after you entering them. Try a few other commands.
```
>> 3-5
>> 2*9
>> 3^2
>> 10/2
>> 2\10
>> 1/0
```
Can you figure out what the symbols `*`, `/`, `^`, `\`, mean? (They are called **operators**). For the last command, you should get `Inf` (_infinity_). You can also use `Inf` for calculation. Try `12+Inf` and `100/Inf`. Another special value you may meet is `NaN`, which stands for _Not-a-Number_.

### Variables

A variable can be created simply by assigning a value to it at the command line, for example,
```
a = 3
```
This statement _**assigns**_ the value of 3 to `a`. Then try the following two lines,
```
>> a = a + 2
>> a = a * 5
```
Do you agree with the final value of `a`? You can create new variables from old ones, like the following,
```
>> x = 5; y =7;
>> z = x + y
```
The first line above does not show any output in the command window, because the semicolon (;) suppress the output of one line being displayed. 

### Mathematical functions

All the common mathematical functions can be found in MATLAB, such as `sin`, `cos`, `log`, `sqrt`. Try the following commands,
```
>> sin(pi)
>> cos(pi/2)
>> cosd(90)
>> sqrt(pi)
>> whos
>> clear
>> whos
```
`whos` lists the current variables in your _**workspace**_. The command `clear` remove variables from memory. You should note that MATLAB knows the value of _π_, because it is one of numerous built-in functions fo MATLAB. 

### Vectors

The variables we used above (e.g. `a`, `b`, `x`) are called _**scalars**_, because they are single-valued. If a variable encompasses multiple scalars in one row or one column, it is called a _row vector_ or _column vector_, respectively.
```
>> x = [1, 2, 3, 4, 5]
>> y = [1; 2; 3; 4; 5]
```
A convenient way to create vectors with uniform interval is to use a colon (:). The following lines create row vectors ranging from 1 to 10, though they have different intervals. 
```
>> z = [1:10]
```
or
```
>> z = [1:2:10]
```
A column vector can be converted to a row vector by adding a prime symbol (') to its end. This action is called _transpose_.






