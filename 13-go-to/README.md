# Exercises 13 - Go To

## Final Exercise

### Goal
```
Output:I have picked a number (1-100). It's your turn to guess it!
Input:32
Output:Nope! My number is Greater!
Input:60
Output: Nope! My number is Smaller!
Input:42
Output: That's the number! Well played!
```

### Instructions
- Create a Console Project named `P13GoTo` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Follow the instructions of the pseudo-code below
- Then see if you can simplify the code a bit
  - using `if`...`else if`...`else`
- Bonus: Add a Try-Counter. Tell the User, how many guesses he needed.
- Bonus: Add a Maximum Try Number. After 10 attempts, the Player loses.

```
PSEUDOCODE:
myNumber := random number between 1 and 100
explain rules to user
USER_TURN:
ask user for number
guess := user input

if myNumber is less than guess then
   tell user to guess lower
   go back to USER_TURN
end if

if myNumber is greater than guess then
   tell user to guess higher
   go back to USER_TURN
end if

if myNumber is equal to guess then
   tell user he won
end if
```

## P13_1Dollars
Write a Program that asks how many Dollars the user wants. Then, the program proceeds to printing that many Dollar Symbols.
- Input: `7`
- Output: `"Here's your Dollars: $$$$$$$"`

## P13_2Triangle
Write a program that prints an ASCII Triangle as follows. Use `goto` efficiently to write as little code as necessary.
```
#####
####
###
##
#
```

## P13_3
Write a program that prints the following pretty ASCII pattern. Use `goto` efficiently to write as little code as necessary.
```
#-#-#-#-#-
-#-#-#-#-#
#-#-#-#-#-
-#-#-#-#-#
#-#-#-#-#-
```
