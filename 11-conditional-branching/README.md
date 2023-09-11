# Exercises 11 - Conditional Branching

## Goal
```
Output:What's your age?
Input:31
Output:You are an adult.
Output:Give me another integer.
Input:20
Output:The maximum is: 31
Output:That number is an odd number.
```

## Instructions
- Create a Console Project named `P11IfElse` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Ask the user for his age
- Print one of these statements (the correct one): 
  - You are an adult
  - You are a child 
  - You are a teenager

- Ask the user for another integer
- Tell him, which is the greater number, the number just given, or his age
- Tell him, whether the greater number is 
  - an even (like 2 4 6) number
  - an odd (like 1 3 5) number
- Hint: How you can find out, whether a number is even or odd?
- Hint: There is an arithmetic operator on the operators-slide that helps you here :)
- Hint: Don't feel ashamed asking another student or googling `How to find out if a number is even c#`
- BONUS: Do the age-task using the ternary operator

## P11_1Grades

Create a program that takes a numerical grade as input from the user and then displays a letter grade (A, B, C, D, or F) based on the following scale:

- A: 90-100
- B: 80-89
- C: 70-79
- D: 60-69
- F: <60

- Input: `90`
- Output: `A`

## P11_2MinMax

Create a program that asks the user to input three numbers and then displays the minimum and maximum of those numbers.
\Do not use `Math.Min` or `Math.Max` (also not `MathF.Min` or `MathF.Max`). You can solve this problem using if...else expressions.

- Input: `12`, `-7`, `100`
- Output: `-7`, `100`

## P11_3Characters

Develop a program that asks the user to enter a single character and then determines whether it's a digit, a vowel or a consonant. Display an appropriate message.

- Input: `'a'`
- Output: `"That's a vowel."`

## P11_4Calculator

Develop a simple calculator program that allows operations such as addition, subtraction, multiplication, and division. Allow the user to choose which operation to perform.

- Input: `3`, `+`, `7`
- Output: `10`

## P11_5EvenOrOdd

Write a program that checks if a given integer is even or odd and displays an appropriate message.

- Input: `12`
- Output: `"That's even."`
