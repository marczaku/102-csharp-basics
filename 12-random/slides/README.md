# Slides 12 - Random

- Using `.NET`s `Random`-Class allows you to generate random numbers
- The numbers are pseudo-random:
    - they are using complex mathematical operations to make them appear random*
    - They are guaranteed to be evenly distributed across all numbers
- You use a seed to determine, which sequence of numbers you want to have
- **That‘s a feature:** we can reproduce the same random numbers if we know the seed.
    - e.g. for Replays or Multiplayer-Simulations
    - where it's important for the replays to have the same "random" events as the original match

## Without Seed

If the seed doesn't matter, you can, since .NET 6, simply use:

```cs
Random.Shared.Next();
random.Shared.NextDouble();
// ... etc. Details will follow later
```

## More Control: With or Without Seed:

`new Random()` initializes a new `Random` Instance with a Random Seed. You can assign the result to a variable of Type `Random`:

- We will learn more about this later in `104 CSharp OOP - Classes & Objects`

```cs
Random random = new Random();
```

`Random(int seed)` initializes a new `Random` Instance with a Custom Seed

```cs
Random random = new Random(23746);
```

## Getting Random Whole Numbers (Integers)

- `int Next(int max)` receives a new random integer between `0` (inclusive) and `max` (exclusive), so for the following code either `0`, `1`, `2`, `3` or `4`

```cs
int number = random.Next(0, 5); // [0..5)
```

- `int Next(int min, int max)` receives a new random integer between `min` (inclusive) and `max` (exclusive), so for the following code either `2`, `3` or `4`

```cs
int number = random.Next(2, 5); // [2..5)
```

- `int Next()` gets a random integer between `0` and `int.MaxValue` (2.1 bln)

```cs
int number = random.Next(); // [0..2147483647)
```

## Getting Random Rational Numbers

`double NextDouble()` Receive a new random number between `0` (inclusive) and `1` (exclusive), so anything from `0.000000` to `0.9999999`

```cs
double number = random.NextDouble(); // [0.0..1.0)
```

## Max Value

To receive a number between `0` (inclusive) and `2.3` (exclusive), you can apply this simple mathematical trick:

- You just multiply the result with `2.3`, which will scale all the numbers between `0` and `1` to be evenly distributed between `0` and `2.3`

```cs
double number = random.NextDouble()*2.3; // [0.0..2.3)
```

## Min Value

To receive a number between `1` (inclusive) and `2` (exclusive), you can apply this simple mathematical trick:

- You just add `1` to the result, which will offset all numbers between `0` and `1` to be evenly distributed between `1` and `2`

```cs
double number = random.NextDouble()+1; // [1.0..2.0)
```

## Min Value and Max Value

- To receive a number between `1.2` (inclusive) and `2.3` (exclusive), it is a bit more complicated:
- You need to multiply the number with `1.1` (`2.3-1.2`), because that's the range of different numbers you need.
    - This will give you numbers between `0` and `1.1`
- Now, you just add `1.2` to that number, which will move all numbers `1.2` higher
    - This will give you numbers between 1.2 and 2.3

```cs
double number = random.NextDouble()*(2.3-1.2)+1.2; // [1.2..2.3)
```

## Using Random Numbers for Random Effects

If you have random chances in your game, e.g.

- a `20%` chance of landing a critical hit
- a `5%` chance for some epic loot
- a `50%` chance of starting as White in Chess
- a `0%` chance to land a hit on an enemy 20 levels above you
- a `100%` chance to land a hit on an enemy 20 levels below you

Then you can do the following:\
First: Convert your chance to a decimal number:

- `20%` = `20/100` = `0.2`
- `5%` = `5/100` = `0.05`
- `50%` = `50/100` = `0.5`
- `0%` = `0/100` = `0.0`
- `100%` = `100/100` = `1.0`

```cs
double chance = 0.2;
```

Now, roll a random number between 0 and 1 (exclusive):

```cs
double roll = Random.Shared.NextDouble(); // e.g. 0.45
```

If the roll is smaller than your chance, then your roll has been successful:

| Roll | 10% Chance | 30% Chance | 50% Chance | 80% Chance | 100% Chance |
|------|------------|------------|------------|------------|-------------|
| 0.0  | ✅          | ✅          | ✅          | ✅          | ✅           |
| 0.1  | ❌          | ✅          | ✅          | ✅          | ✅           |
| 0.2  | ❌          | ✅          | ✅          | ✅          | ✅           |
| 0.3  | ❌          | ❌          | ✅          | ✅          | ✅           |
| 0.4  | ❌          | ❌          | ✅          | ✅          | ✅           |
| 0.5  | ❌          | ❌          | ❌          | ✅          | ✅           |
| 0.6  | ❌          | ❌          | ❌          | ✅          | ✅           |
| 0.7  | ❌          | ❌          | ❌          | ✅          | ✅           |
| 0.8  | ❌          | ❌          | ❌          | ❌          | ✅           |
| 0.9  | ❌          | ❌          | ❌          | ❌          | ✅           |

If you have a 50% Crit Chance, then a Roll of `0.45` would be successful! :)

```cs
bool successful = roll < chance;
```

### How does it work?

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

### Complete Code Sample:

```cs
if(Random.Shared.NextDouble() < `0.2`){
  Console.WriteLine("You only had a 20% chance, but you were successful!");
} else {
  Console.WriteLine("Unfortunately, 20% chance was not enough this time :(");
}
```