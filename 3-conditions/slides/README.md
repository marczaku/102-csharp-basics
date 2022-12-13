# Slides 3 - Conditions

## 8. Boolean

## bool Type

- **Booleans** (`bool`) are used to display values, that can be:
  - `YES` or `NO`
  - `ON` or `OFF`
  - `TRUE` or `FALSE`
```cs
bool isWaterBlue = true;
bool isWaterRed = false;
```

## Logical Operators

- You can inverse them by using an exclamation mark `!` (read it as `NOT`
  - `!true` -> `false`
  - `!false` -> `true`
```cs
bool isWaterNotRed = !isWaterRed; // true
```
- You can combine two `bool` values with `&&` (Read: AND) or `||` (Read: OR)
- `&&` only returns `true`, if both incoming values are `true`:
```cs
bool isOfFullAge = true;
bool hasEnoughMoney = true;
// You are only allowed, if you are of full age AND you have enough money:
bool mayBuyBeer = isOfFullAge && hasEnoughMoney; // true
```

```cs
bool isOfFullAge = false;
bool hasEnoughMoney = true;
bool mayBuyBeer = isOfFullAge && hasEnoughMoney; // false, because you are not of Full Age.
```

<img width="663" alt="image" src="https://user-images.githubusercontent.com/7360266/135261149-d4c2a4d5-7528-48cd-a834-0beb68c3e78c.png">

- `||` returns `true`, if either incoming value is `true`:
```cs
bool hasEnoughMoney = true;
bool canGetALoan = true;
// You are allowed to buy the product, if you either have enough money, or you can get a loan:
bool mayBuyBeer = hasEnoughMoney || canGetALoan; // true
```

```cs
bool hasEnoughMoney = false;
bool canGetALoan = true;
bool mayBuyBeer = hasEnoughMoney || canGetALoan; // true
```

```cs
bool hasEnoughMoney = false;
bool canGetALoan = false;
bool mayBuyBeer = hasEnoughMoney || canGetALoan; // false
```

<img width="663" alt="image" src="https://user-images.githubusercontent.com/7360266/135261875-3d194376-9e52-459a-9991-664225e8e8d0.png">

## Toggling Bool

You can use `!` to Toggle a `bool` value between two states:

```cs
bool playerTurn = true;
// ...
playerTurn = !playerTurn;
// ...
playerTurn = !playerTurn;
```

## Comparison Operators

- Comparision operators can compare two values and return a `bool` (`true` or `false`)
```cs
bool isGreater = 10 > 9; // True
bool isEqual = 10 == 9; // False
bool isNotEqual = 10 != 9; // True
bool isLess = 10 < 9; // False
bool isGreaterOrEqual = 10>= 9; // True
bool isLessOrEqual = 10<= 9; // False
```

---

## 9. If .. Else

- Using `if`-`else` Blocks with Conditions allows you to write conditional code
- Code, that is only executed, if a condition is met

```cs
if(bool-condition) { // if-scope-start
   // then execute this code
} // if-scope-end
else 
{ // else-scope-start
   // else execute this code
} // else-scope-end
```

- Here is an example of using `if`-`else if`-`else` to print an appropriate Greeting depending on the time:
```cs
int hour = GetHour();
if (hour <12) {
  // If the hour is 0-11
  Console.WriteLine("Good morning!");
}
else if (hour <18) {
  // Else, if the hour is 12-17
  Console.WriteLine("Good Day!");
}
else {
  // If the hour is more than 18
  Console.WriteLine("Good Evening!");
}
```

- If-Statements are also called flow control statements, because you can control the flow of the code.
- Take this code sample, for example:
```cs
int age = Convert.ToInt32(Console.ReadLine());
if(age >= 18)
{
  Console.WriteLine("You are grown up!");
} 
else 
{
  Console.WriteLine("Not old enough!");
}
Console.WriteLine("Thanks for visiting!");
```
- The Code Flow can be seen here:

<img width="510" alt="image" src="https://user-images.githubusercontent.com/7360266/135164846-9f41ef18-9263-49ab-87fb-3273ef9d1c6e.png">

As you can see, the Code Flow (Arrows) changes depending on the condition.\
Without flow control statements, code simply runs from top to bottom.\
But thanks to `if`..`else` and other flow control statements, we can write dynamic and interactive code!


- The ternary if-operator can be used as a short-cut for `if`-`else`-blocks, when assigning a value:
```cs
string greeting = condition ? then-value : else-value;
string greeting = condition ? true-value : false-value;
```

```cs
string greeting = hour < 12 ? "Good Morning!" : "Good Day!";
```
- Above code sample is the same as:
```cs
string greeting;
if (hour < 12) {
  greeting = "Good Morning!";
}
else {
  greeting = "Good Day!";
}
```

## 9.5 Switch

Whenever you have a lot of `if..else..` blocks checking for the same value:

```cs
if(input == 2){
  // ...
} else if(input == 12){
  // ...
} else if(input == 16){
  // ...
} else if(input == 13){
  // ...
} else {
  // ELSE
}
```

You can replace it with a `switch` statement:

```cs
int input = 12;
switch(input) {
  case 2:
    // ...
    break;
  case 12:
    // ...
    break;
  case 16:
    // ...
    break;
  case 13:
    // ...
    break;
  default:
    // ELSE
    break;
}
```

It also works for `string`:

```cs
string input = Console.ReadLine();
switch(input){
  case "Start Game":
    // ...
    break;
  case "Load Game":
    // ...
    break;
  case "Quit Game":
    // ...
    break;
  default:
    Console.WriteLine($"Invalid Input: {input}");
    break;
}
```
            
---

## 10. Random

- Using `.NET`s `Random`-Class allows you to generate random numbers
- The numbers are pseudo-random: 
  - they are using complex mathematical operations to make them appear random*
  - They are guaranteed to be evenly ditributed across all numbers
- You use a seed to determine, which sequence of numbers you want to have
- **That‘s a feature:** we can reproduce the same random numbers if we know the seed. 
  - e.g. for Replays or Multiplayer-Simulations
  - where it's important for the replays to have the same "random" events as the original match

### Without Seed

If the seed doesn't matter, you can, since .NET 6, simply use:

```cs
Random.Shared.Next();
random.Shared.NextDouble();
// ... etc. Details will follow later
```

### More Control: With or Without Seed:

`new Random()` initializes a new `Random` Instance with a Random Seed. You can assign the result to a variable of Type `Random`:
- We will learn more about this later in `104 CSharp OOP - Classes & Objects`

```cs
Random random = new Random();
```

`Random(int seed)` initializes a new `Random` Instance with a Custom Seed
```cs
Random random = new Random(23746);
```

### Getting Random Whole Numbers (Integers)

- `int Next(int max)` receives a new random integer between `0` (inclusive) and `max` (exclusive), so for the following code either `0`, `1`, `2`, `3` or `4`
```cs
int number = random.Next(0, 5); // [0..5[
```

- `int Next(int min, int max)` receives a new random integer between `min` (inclusive) and `max` (exclusive), so for the following code either `2`, `3` or `4`
```cs
int number = random.Next(2, 5); // [2..5[
```

- `int Next()` gets a random integer between `0` and `int.MaxValue` (2.1 bln)
```cs
int number = random.Next(); // [0..2147483647[
```

### Getting Random Rational Numbers

`double NextDouble()` Receive a new randomNumber between 0 (inclusive) and 1 (exclusive), so anything between 0.000000 and 0.9999999
```cs
double number = random.NextDouble(); // [0.0..1.0[
```

To receive a number between 0 (inclusive) and 2.3 (exclusive), you can apply this simple mathematical trick:
- You just multiply the result with 2.3, which will scale all the numbers between 0 and 1 to be evenly distributed between 0 and 2.3
```cs
double number = random.NextDouble()*2.3; // [0.0..2.3[
```

- To receive a number between 1.2 (inclusive) and 2.3 (exclusive), it is a bit more complicated:
- You need to multiply the number with 1.1 (2.3-1.2), because that's the range of different numbers you need.
  - This will give you numbers between 0 and 1.1
- Now, you just add 1.2 to that number, which will move all numbers 1.2 higher
  - This will give you numbers between 1.2 and 2.3
```cs
double number = random.NextDouble()*(2.3-1.2)+1.2; // [1.2..2.3[
```

### Using Random Numbers for Random Chances

If you have random chances in your game, e.g.
- a `20%` chance of landing a critical hit
- a `5%` chance for some epic loot
- a `50%` chance of starting as White in Chess
- a `0%` chance to land a hit on an enemy 20 levels above you
- a `100%` chance to land a hit on an enemy 20 levels below you

Then you can do the following:\
First: Translate your chance to a decimal number:
- `20%` = `20/100` = `0.2`
- `5%` = `5/100` = `0.05`
- `50%` = `50/100` = `0.5`
- `0%` = `0/100` = `0`
- `100%` = `100/100` = `1`

```cs
double chance = 0.2;
```

Now, roll a random number between 0 and 1 (exclusive):

```cs
double roll = Random.Shared.NextDouble(); // e.g. 0.45
```

If the roll is smaller than your chance, then your roll has been successful:

- `0.45 < 0.2` = `false` = not successful
- `0.45 < 0.05` = `false` = not successful
- `0.45 < 0.5` = `true` = successful
- `0.45 < 0` = `false` = not successful
- `0.45 < 1` = `true` = successful

```cs
bool successful = roll < chance;
```

#### Why does it work?

Why do we need to use the `<` operator?
- `NextDouble()` gives us a number from 0.0000000 to 0.9999999
- For `100%`, all random numbers should return `true`
  - `0.0000000` is smaller than `1`
  - `0.9999999` is also smaller than `1`
  - Which means, that it works for 100% chance!
- For `0%`, all numbers should return `false`
  - `0.0000000` is not smaller than `0`
  - `0.9999999` is not smaller than `0`
  - Which means, that it works for 0% chance!
- For `50%`, half of the numbers should return true
  - `0.000000` up to `0.4999999` are smaller than `0.5`
  - `0.500000` up to `0.9999999` are not smaller than `0.5`
  - Both ranges are the same in size, so it works also for 50%!

#### Complete Code Sample:

```cs
if(Random.Shared.NextDouble() < `0.2`){
  Console.WriteLine("You only had a 20% chance, but you were successful!");
} else {
  Console.WriteLine("Unfortunately, 20% chance was not enough this time :(");
}
```