# Exercises 4 - Go To

## Goal
Learn about how we can go back in time (well at least lines of code) by using `goto`. This will allow us to run the same line(s) of code a second time. Or a hundredth. Or forever.

## 11 - Go-To: 

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
- Use `Random` to create a random number between 1 and 100 and assign it to a variable named `myNumber`.
- Explain the game to the user and ask for his number.
- Read the user's input and assign it to a variable named `guess`.
- Compare the `guess` to `myNumber`.
  - if `myNumber` is smaller than `guess`, tell the user it's smaller.
    - And then `goto` the line of code where you wait for the user's input.
  - if `myNumber` is greater than `guess`, tell the user it's greater.
    - And then `goto` the line of code where you wait for the user's input.
  - if `myNumber` is equal to `guess`, tell the user that he guessed correctly!
    - And then end the application. (No more `goto`)
- Bonus: Add a Try-Counter. Tell the User, how many guesses he needed.
- Bonus: Add a Maximum Try Number. After 10 attempts, the Player loses.

Need Help? [Read the Slides on Go-To](slides#11-go-to)

---

## Done?
Return to the [Overview](../../..#4-go-to)
