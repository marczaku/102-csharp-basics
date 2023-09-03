# Slides 5 - Variables

Variables are used to store information in C#. We need variables to keep track of all kinds of information that our applications need. Imagine a game of chess, for example. We would need variables to store 
- all the pieces that are part of the Game
- as well as their positions
- whose turn it is.

We can then read the information, so we can display the Chess Board to the player, and we can also change the information stored in those variables when the players make moves on the board.

## Variable Definition
- Variables are used to store data
- Variables consist of a Type and a Name. (More on Types in the next Chapter)
- This is, how you declare a variable:
```cs
int money;
```

## Variable Assignment
- You can access variables for reading and writing using their name
- You can assign a value to a variable using the assignment operator `=`
```cs
money = 5;
```

## Variable Access
- You can access a variable through it's variable name, too.
- When you access a variable, you access its value.
- In the following code, when accessing the `money` variable, we access its value, which is `5`:
```cs
Console.WriteLine(money); // This prints 5
```

Hint: This is different from when you'd pass the variable name in quotation marks:
```cs
Console.WriteLine("money"); // This prints money
```

## Variable Initialization
- Whenever a variable is assigned (`=`) a value for the first time
- We call it Initialization
- Before a variable has been initialized, we cannot access it:

```cs
// You can not use an uninitialized variable
int y;
Console.WriteLine(y); // ERROR: Cannot access uninitialized variable.
```

- You can initialize a variable directly when defining it:
```cs
int score = 99;
Console.WriteLine(score); // This prints 99
```

- You can assign a new value to a variable anytime:
```cs
score = 30;
Console.WriteLine(z); // This prints 30
score = 10;
Console.WriteLine(z); // This prints 10
```

## Variable Validity
- A variable is only accessible below the line where it is defined
```cs
Console.WriteLine(a); // ERROR, you can only use `a` AFTER it has been defined.
int a = 5; // This is, where a is defined.
```

## Multiple Definition
You can define multiple variables of the same type by separating the variable names by a comma `,`:
```cs
int a, b, c;
```

But careful, if you assign a value right away, it only gets assigned to the right-most variable.
- `a`: uninitialized
- `b`: uninitialized
- `c`: 2
```c
int a, b, c = 2;
```

## Multiple Assignments
You can do multiple assignments.\
Assignments are right-associative, which means, that they are evaluated from right to left:
- First: `c = 5`
- Second: `b = c` (which is `5`)
- Third: `a = b` (which is `5`)
```cs
int a = 1;
int b = 2;
int c = 3;
a = b = c = 5;
```