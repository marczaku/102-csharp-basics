# Slides 9 - Operators

- Operators are functions represented by symbols
- They execute operations and return a result
- The result can be assigned to a variable, or used directly

```cs
int x = 5 + 5; // x = 10
int y = x + 5; // y = 15
int z = y + y; // z = 30
Console.WriteLine(z + z); // 60
```

## Binary Arithmetic Operators

- Binary Arithmetic operators are used for mathematical operations
- They take two numbers as input and return a number as output

```cs
int add = 3 + 5; // 8
int subtract = 6 - 12; // -6
int multiply = 3 * 4; // 12
int divide = 9 / 3; // 3
```

Another really cool one is the Modulo-Operator.
- It returns the Remainder after Integer Division.
- e.g. `10 % 3`
  - `10 / 3 = 3`
  - Remainder: `1`
  - Proof: `3*3+1 = 9+1 = 10`
- I will ask you to use it A LOT!

```cs
int modulo = 10 % 3; // = 1
```

They may sometimes accept non-numeric types as input, if custom operators were implemented. More on that later.
```cs
Coins twoCoins = new Coin() + new Coin();
```

## Operator Precedence

Arithmetic operators are left-associative.\
Generally speaking, this means, that operators are evaluated from left to right:
```cs
int result = 8 - 2 - 1; // 5
```

$8 - 2 - 1 = (8 - 2) - 1 = 6 - 1 = 5$

Parentheses `()` have precedence over mathematical operators. They have a higher priority and are evaluated first.
```cs
int result = 8 - (2 - 1); // 7
```

$8 - (2 - 1) = 8 - 1 = 7$

Keep in mind, that, just as in Mathematics, Division and Multiplication have higher precedence:
```cs
int result = 4 + 1 * 2; // 6
```

$4 + 1 \mul 2 = 4 + (1 \mul 2) = 4 + 2 = 6$

## Arithmetic Assignment Operators

What's wrong with the following code sample?

```cs
int gold = 50;
// collect 10 gold:
gold + 10;
```

The problem: It evaluates to this:

```cs
50 + 10;
```

Which is the same as:

```cs
60;
```

But we don't do anything with the result of that expression.\
We need to assign it:

```cs
int gold = 50;
gold = gold + 10;
```

This evaluates to:

```cs
gold = 50 + 10;
```

And then to:

```cs
gold = 60;
```

Which is, what we expected.

### Operator to the rescue

- Since we very often use an operator on a variable's value and then assign the result to the same variable
- A shorthand-writing exist for this case:

Given
```cs
int number = 5;
```

You can write

```cs
number = number + 3;
```

As:

```cs
number += 3;
```

same goes for the other operators:
```cs
number /= 2;
number *= 5;
number -= 3;
number %= 9;
```

## Increment and Decrement Operator

And in case you want to increase a number simply by 1
The increment-operator does exactly that, but even shorter:

```cs
int i = 0;
i = i + 1; // increases i by 1
i += 1; // increases i by 1
i++; // increases i by 1
```

The same goes with `-`, too, it's called decrement-operator:
```cs
i--;
```

### Post-Increment and Pre-Increment Operators

Funny enough, there is two ways of using the operator, with slightly different behavior:

Post-Increment:
- if you write `i++`, then the value is increased by 1, but the value passed on is still the old one.
  - you can remember this by reading from left to right: i is used, then it is increased (`++`)
  - this is called `post-increment`-operator
```cs
int i = 5;
Console.WriteLine(i++); // 5
Console.WriteLine(i); // 6
```

Pre-Increment:
- if you write `++i`, then the value is increased by 1 and then the already increased value is passed on.
  - you can remember this by reading from left to right: i is first increased (`++`) and then it is used.
  - this is called `pre-increment`-operator
```cs
int i = 5;
Console.WriteLine(++i); // 6
Console.WriteLine(i); // 6
```
