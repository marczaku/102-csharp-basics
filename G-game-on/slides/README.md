# Slides 5 - Game On

## Goal
Here's some tips on how to overcome the seemingly impossible task of implementing Nim.

## 1. Step By Step

Some projects might seem overwhelming, but can get a lost easier, if attacked step by step. Let's look at our desired Output:

```
Output:Welcome to Nim!
Output:|||||||||||||||||||||||| (24)
Output:How many matches do you want to draw?
Input:3
Output:||||||||||||||||||||| (21)
Output:The AI draws 3 matches.
Output:|||||||||||||||||| (18)
...
Output:|||
Output:The AI draws 2 matches.
Output:|
Output: You lose.
```

Oof! But can we start slowly somehow? As easy as possible?

Let's start just printing the welcome message:
```cs
Console.WriteLine("Welcome to Nim!");
```

Okay, easy enough. But what about the next line? We need to print different number of matches depending on how many there is? Let's keep that one for later and hack in a first solution:

```cs
// TODO: This is hard-coded for now. How to do better?
Console.WriteLine("|||||||||||||||||||||||| (24)");
```

The next one is very easy again. Just some text.

```cs
Console.WriteLine("How many matches do you want to draw?");
```

Now, we need to read the user's input...

```cs
string userInput = Console.ReadLine();
```

```
Input:3
```

And then tell, how many matches are left? How to do that?

```
Output:||||||||||||||||||||| (21)
```

Well, we had `24` before and now have `21`. The `string` `"3"` was the user's input, but we cannot do Maths from a string. Also, we need to store the result somewhere...

Maybe, it's about time that we introduce a Variable in which we can store the number of matches. What could be the right type? The right name?

When we have done that:
- introduced a variable to store the number of matches
- reduced the number by the amount the user wanted us to remove

We're back to the problem of printing it properly:

```
Output:||||||||||||||||||||| (21)
```

Printing 21 `|`-Symbols looks a bit difficult to me. But maybe, we can start with the easy way for now?

```cs
Console.Writeline("Draw matches here later: "+placeYourVariableNameHere);
```

```
Output:Draw matches here later: 21
```

Well, close enough for now :D

Next?

```
Output:The AI draws 3 matches.
```

Oof, AI. I'm no AI programmer, I'm not Google or Meta... We're not that smart, yet. But we're quite smart now, even though we started as Babies. Similarly, our Code can start with a baby version and then grow into something smarter in the future. For now, we'll code the world's most simple AI:

```cs
// TODO: Add smarter AI here
int aiChoice = 1;
```

Next steps:
- Reduce your variable that counts the matches by `aiChoice`
- Evaluate the Game:
  - Is there still matches left? Use `goto` to let the player choose, how many matches to draw again.
  - Are all gone? Who drew the last one? Print, who lost.