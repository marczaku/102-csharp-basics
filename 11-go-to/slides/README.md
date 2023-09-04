# Slides 4 - Go To

## Goal
Learn about how we can go back in time (well at least lines of code) by using `goto`. This will allow us to run the same line(s) of code a second time. Or a hundredth. Or forever.

## 11. Go To

### Label

We can use Labels in our Code by using `LabelName:`-Syntax.\
Here, you can see a few labels defined: 

```cs
GameStart:
Console.WriteLine("Game Starting now.");
```

```cs
GameOver:
Console.Writing("GAME OVER");
```

What's their use? They can be used in Combination with...

### goto

The `goto`-Statement allows us to jump to a label that we have defined before. Check out this example:

```cs
AskToBuy:
Console.WriteLine("Please buy my game? Answer Yes or No.");
string answer = Console.ReadLine();
if (answer != "Yes")
{
    goto AskToBuy;
}
Console.WriteLine("Thanks for buying my game!");
```

Output:
```
Please buy my game? Answer Yes or No.
No
Please buy my game? Answer Yes or No.
No
Please buy my game? Answer Yes or No.
Yes
Thanks for buying my game!

```

This is one way of increasing our Game Sales! :D

### Bad Code?

Note: The `goto`-Statement is often considered a very bad code-style. This is mostly due to programmers having discovered many reusable patterns where you'd usually use `goto` and having introduced more specialized Statements for each of these use cases (`for`, `while`, `do`, `break`, `continue`, ...) More on these keywords later :)

### Not always!

There is a few use cases, where the `goto`-Statement might perfectly or at least more cleanly solve your problem. It is definitely worth knowing and understanding in order to also understand, why other loop keywords have been introduced at a later point.
