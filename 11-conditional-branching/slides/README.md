# Slides 11 - Conditional Branching

## If
- Using `if`, you can write code that is skipped if the condition is NOT `true`:
- `if` the `bool`-condition is `true`, it will execute the code between `{` and `}`
- `if` the `bool`-condition is `false`, it will skip to the code after `}`

```cs
bool playerTouchGround = true;
if(playerTouchGround) { // if-scope-start
   Console.WriteLine("Player is on the ground.");
   Console.WriteLine("Player can jump.");
} // if-scope-end

// code after if
```

## If..Else

Let's say, you wanted to print a message in case the player is currently not touching the ground:

```cs
bool playerTouchGround = true;
if(playerTouchGround) { // if-scope-start
   Console.WriteLine("Player is on the ground.");
   Console.WriteLine("Player can jump.");
   playerTouchGround = false;
} // if-scope-end

if(!playerTouchGround) {
   Console.WriteLine("Player is not touching the ground.");
   Console.WriteLine("You can not jump right now.");
}
```

What is the problem with above code?

The problem:
- it will always check for both conditions.

The Solution:

Using `if`-`else`:
- It will check the condition of `playerTouchGround` once
- and then either
  - if `true`: jump to `if-scope-start` `{`
  - if `false`: jump to `else-scope-start` `{`

```cs
if(playerTouchGround) { // if-scope-start
   // then execute this code
} // if-scope-end
else 
{ // else-scope-start
   // else execute this code
} // else-scope-end
```

## If..ElseIf..Else

This code here can be simplified:

```cs
int hour = GetHour();
if (hour < 12) {
  // If the hour is 0-11
  Console.WriteLine("Good morning!");
}
if (hour >= 12 && hour < 18) {
  // Else, if the hour is 12-17
  Console.WriteLine("Good Day!");
}
if (hour >= 18) {
  // If the hour is more than 18
  Console.WriteLine("Good Evening!");
}
```

Using `if`..`else if`..`else`:

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
int age = int.Parse(Console.ReadLine());
if(age >= 18)
{
  Console.WriteLine("You are an adult!");
} 
else 
{
  Console.WriteLine("Not old enough!");
}
Console.WriteLine("Thanks for visiting!");
```

The Code Flow can be seen here:

<img width="510" alt="image" src="https://user-images.githubusercontent.com/7360266/135164846-9f41ef18-9263-49ab-87fb-3273ef9d1c6e.png">

As you can see, the Code Flow (Arrows) changes depending on the condition.\
Without flow control statements, code simply runs from top to bottom.\
But thanks to `if`..`else` and other flow control statements, we can write dynamic and interactive code!

## Ternary If

Quite often, you will end up with code like this:

```cs
string buttonText;
if(isSubscribed) {
   buttonText = "Unsubscribe";
} else {
   buttonText = "Subscribe"
}
Console.WriteLine(buttonText);
```

The problem is, that's a lot of lines of code!\
You also can't write this: (why?)

```cs
if(isSubscribed) {
   string buttonText = "Unsubscribe";
} else {
   string buttonText = "Subscribe"
}
Console.WriteLine(buttonText);
```

- The ternary if-operator can be used as a short-cut for `if`-`else`-blocks, when assigning a value:

```cs
string buttonText = isSubscribed ? "Unsubscribe" : "Subscribe";
```

### Syntax

```cs
type result = condition ? then-value : else-value;
```

### Another Example

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

## Switch
(Intentionally left out.)

The `switch` statement can improve readability under certain circumstances and even improve performance, but it won't enable you to solve any new problems:

```cs
if (time < 12)
{
    Console.WriteLine("Good Morning!");
}
else if (time < 18)
{
    Console.WriteLine("Good Day!");
}
else
{
    Console.WriteLine("Good evening!");
}
```

Can also be written as:
```cs
switch (time)
{
    case < 12:
        Console.WriteLine("Good Morning!");
        break;
    case < 18:
        Console.WriteLine("Good Day!");
        break;
    default:
        Console.WriteLine("Good evening!");
        break;
}
```

Yes, it does look more clean, but I recommend paying intention to this at a later time.