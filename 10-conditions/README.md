# Exercises 3 - Conditions

## Goal
Learn about more complex data manipulation through Maths, Strings, Random Numbers and comparison, as well as code flow control through conditional code.

## 8 - Boolean: 

### Goal
```
Output:What's your age?
Input:31
Output:You are a child:False
Output:You are a teenager:False
Output:You are a grown-up:True
```

### Instructions
- Create a Console Project named `P10Boolean` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Ask the user for his age. Save it to a variable named `age`
- First, do a few age-checks:
  - Save to a `bool`-variable named `isChild`, whether the age is between 0 and 12
  - Save to a `bool`-variable named `isTeenager`, whether the age is between 13 and 19
  - Save to a `bool`-variable named `isGrownup`, whether the age is greater 19
- Then, print them all to the console like this:
  - `You are a child: True` etc. (see sample below)

Need Help? [Here's The Slides!](slides/README.md#8-boolean)

## 9 - If..Else:

### Goal
```
Output:What's your age?
Input:31
Output:You are a grown-up.
Output:Give me another integer.
Input:20
Output:The maximum is: 31
Output:Your number is an odd number.
```

### Instructions
- Create a Console Project named `P11IfElse` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Ask the user for his age
- Print one of these statements (the correct one): 
  - You are a grown-up 
  - You are a child 
  - You are a teenager

- Ask the user for another integer
- Tell him, which is the larger number, the number just given, or his age
- Tell him, whether the larger number is 
  - an even (like 2 4 6) number
  - an odd (like 1 3 5) number
- Hint: How you can find out, whether a number is even or odd?
- Hint: There is an arithmetic operator on the operators-slide that helps you here :)
- Hint: Don't feel ashamed asking another student or googling `How to find out if a number is even c#`
- BONUS: Do the age-task using the ternary operator

Need Help? [Read the Slides on If..Else](slides#9-if--else)

## 10 - Random:

### Goal
```
Output:Please pass me a seed (integer).
Input:1234
Output:Three integers between 0 and 5:
Output:1
Output:4
Output:1
Output:Three numbers between 0.0 and 0.5:
Output:0.47336876693804225
Output:0.16971801229273809
Output:0.47438912045880643
Output:Three numbers between 0.2 and 0.7:
Output:0.6039959450736623
Output:0.46036547346057627
Output:0.5219790320480144
Output:Give me a crit chance between 0.0 (0%) and 1.0 (100%)
Input:0.7
Output:Crit
Output:Crit
Output:No Crit
Output:No Crit
Output:Crit
```

### Instructions
- Create a Console Project named `P12Random` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Ask the User for a Seed and store it in a variable.
- Initialize Random with the given Seed.
- Get three Random Numbers between 0 and 5 (including 0, excluding 5) and print them to the Console.
- Get three Random Numbers between 0 and 0.5 (including 0, excluding 0.5) and print them to the Console.
- Get three Random Numbers between 0.2 and 0.7 (including 0.2, excluding 0.7) and print them to the Console.
- Ask the user for a Crit Chance between 0.0 (0%) and 1.0 (100%). 
- Then simulate 5 Attacks and write, whether it’s a Crit. Or No Crit. 
- Hint: Thanks to using the Seed, you should actually receive the same results as me below, if using the same Seed. Test it! :)
Need Help? [Here's The Slides!](slides/README.md#10-random)

## Done?
Return to the [Overview](../../..#3-conditions)
