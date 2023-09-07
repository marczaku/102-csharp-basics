# Slides 13 - Go To

## Label

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

Sometimes, you want to put a label where there's no more lines of code. In that case, just an empty statement:

```cs
GameOver:;
```

What's their use? They can be used in Combination with...

## goto

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

## Bad Code?

Note: The `goto`-Statement is often considered a very bad code-style.
- It's because there's different reasons for using `goto`
- And to make them more clear, other keywords were introduced (`for`, `while`, `do`, `break`, `continue`, ...) More on these keywords later :)

## Not always!

- sometimes, `goto` works just as well
- sometimes even better
- useful to know, anyways
