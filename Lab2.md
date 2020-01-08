## 2. MATLAB Fundamentals

The objective of this class is to familiarize yourself with some of the fundamentals of MATLAB programming, including:
* Variables, operators, and expressions
* Arrays (including vectors and matrices)
* Basic input and output
* Repetition (`for`)
* Decision (`if`)

The contents of this class prepare you for coding projects in this course, as well as some scientific and engineering problems you may encounter in the future.

### Variables

A variable name must comply with the following two rules:
* It may consist only of the letters `a-z`, the digits `0-9`, and the underscore (`_`)
* It must start with a letter

A variable is created simply by assigning a value to it at the command lind or in a program -- for example, 
```
rain_rate = 100
temperature = 23
pressure = 1000
```

MATLAB is _case-sensitive_, which means it distinguishes between upper- and lowercase letters. Thus, `temperature`, `TEMPERATURE`, and `Temperature` are three different variables.  

### Workspace

Another fundamental concept in MATLAB is _workspace_. If you type in the three variables above and now enter the command `who`. You should see a list of variables as follows.



