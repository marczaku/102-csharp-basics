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
string user;
```

## Variable Assignment
- You can access variables for reading and writing using their name
- You can assign a value to a variable using the assignment operator `=`
```cs
user = "Marc;
```

## Variable Access
- You can access a variable through it's variable name, too.
- When you access a variable, you access its value.
- In the following code, when accessing the `user` variable, we access its value, which is `"Marc"`:
```cs
Console.WriteLine(user); // This prints Marc
```

Hint: This is different from when you'd pass the variable name in quotation marks:
```cs
Console.WriteLine("user"); // This prints user
```

## Variable Initialization
- Whenever a variable is assigned (`=`) a value for the first time
- We call it Initialization
- Before a variable has been initialized, we cannot access it:

```cs
// You can not use an uninitialized variable
string pet;
Console.WriteLine(pet); // ERROR: Cannot access uninitialized variable.
```

- You can initialize a variable directly when defining it:
```cs
string trinket = "The One Ring";
Console.WriteLine(score); // This prints 99
```

- You can assign a new value to a variable anytime:
```cs
string book = "Harry Potter";
Console.WriteLine(z); // This prints Harry Potter
book = "Kungsgatan"
Console.WriteLine(z); // This prints Kungsgatan
```

## Variable Validity
- A variable is only accessible below the line where it is defined
```cs
Console.WriteLine(movie); // ERROR, you can only use `a` AFTER it has been defined.
string movie = "Inception"; // This is, where a is defined.
```

## Multiple Definition
You can define multiple variables of the same type by separating the variable names by a comma `,`:
```cs
int book, movie, tvShow;
```

But careful, if you assign a value right away, it only gets assigned to the right-most variable.
- `book`: uninitialized
- `movie`: uninitialized
- `tvShow`: `"Harry Potter"`
```c
int book, movie, tvShow = 2;
```

## Multiple Assignments
You can do multiple assignments.\
Assignments are right-associative, which means, that they are evaluated from right to left:
- First: `first = "Marc"`
- Second: `second = first` (which is `"Marc"`)
- Third: `third = second` (which is `"Marc"`)
```cs
string first;
string second;
string third;
third = second = first = "Marc";
```