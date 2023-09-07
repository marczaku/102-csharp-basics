# Slides 6 - Types

- C# is a **type-safe** language.
- You use different types to represent different data.
- Most basic types should be clear in their usage.

## Whole Numbers
Used whenever you want to count something
  - number of items in your inventory `12`
  - level of the player `97`
```cs
int age = 5;
int motivation = -1;
```

<details>
Other Types include: sbyte, short, long, byte, ushort, uint, ulong
</details>

## Fractional numbers
Used a lot in programming for all numbers which are not whole numbers
- a player's coordinate in the game world `12.53f`
- player's progress `0.99f` (99%)
```cs
float interestRate = 0.025f;
float interestRate2 = .025f;
float multiplier = 3f;
```

These numbers are inaccurate approximations
- for memory reasons
- therefore, you need to avoid comparing for equality
- and avoid very large numbers (positive and negative)
<details>
   <summary>Code Example</summary>

```cs
float add = 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f + 0.1f;
float multiply = 0.1f * 11;
Console.WriteLine($"is {add} the same as {multiply}?");
```

</details>

<details>
  <summary>More Precision</summary>

### More precise Fractional numbers
- Used whenever `float` is too inaccurate for you
  - the player's gps coordinates in the world `56.461234424`
  - a stock's market cap at 4 trillion `4000000000000.0`
```cs
double bacteriaSize = 24e-10;
double atomSize = 0.00000000000001;
```
</details>


## True or false flag
- Used whenever you have something in your game that can have two states
  - door: open `true` and closed `false`
  - gameOver: `true` or `false`
```cs
bool isWinning = false;
bool lovesProgramming = true;
```

## Single Letters
Not used very often
- contains the numeric value of a character

```cs
char euroSign = '€';
```

You can actually do math with `chars`:

```cs
char c = 'C';
char a = 'A';
int result = c-a; // 2
```

## Text
Used to store text
- the player's name `"Marc"`
- an items' description `"The long-sword has been a danger..."`
```cs
string name = "Marc";
```

There is a few special characters:
```cs
Console.WriteLine("Hello, World.\nThis is a new line.");
Console.WriteLine("If you want to print \"Quotes\", escape them.");
Console.WriteLine("Better put some\t\tDistance.");
```

You can define multiline strings more comfortably using `@`:
```cs
string starWarsIntro = @"Star Wars
Episode IV:
A New Hope";
```

And interpolated strings, where you use variables within a string using `$`:
```cs
string name = "Marc";
string response = $"Welcome, {name}!";
```