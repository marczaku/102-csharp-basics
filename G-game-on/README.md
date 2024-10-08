# Exercises 5 - Game On

## Goal
Recap everything that you have learned this week through an advanced exercise. Pick either the Nim-Game, the Tic-Tac-Toe-Game or the Battleship-Game depending on your confidence in your abilities.\
You are allowed to complete all three games, if you feel that you are up for the challenge.

## Game 1: Nim

### Goal
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
Output:How many matches do you want to draw?
Input: 1
Output:You drew the last match. You lose.
```

### Instructions
- Create a Console Project named `Nim` [How To?](https://gist\.github\.com/marczaku/a8b3c38c37e8876a46194a73ed24b1f2)
- Implement the game of Nim: 
- 2 players 
- 24 matches
- Players take turns to draw matches
- Each player may draw 1,2 or 3 matches (not more or less)
- The Player who has to take last match loses
- Make an ASCII-Art Display of the remaining matches `||||||||`
- Implement an AI-Player
  - Can you make it fun?
  - Can you make it unbeatable?

Need Help? [Read the Slides on Game On](slides)

## Game 2: Tic, Tac, Toe (BONUS, Difficult!)
### Instructions
- Create a Console Project named `TicTacToe`
- 2 Players
  - Player 1: `X`
  - Player 2: `O`
- 3x3 Grid (use a two-dimensional array)
- players take turns choosing an empty grid cell and putting their symbol into it
- player that has three of his symbols either
  - horizontally
  - vertically
  - diagonally
- wins and the game ends instantly.
- make an ASCII-Art Display of the grid 
```
 | |X
-----
O|X|
-----
O| |
```
- Bonus: implement AI-Player

### Sample
```
Output:Welcome to Tic-Tac-Toe!
Output: | | 
Output:-----
Output: | |
Output:-----
Output: | |
Output:In what column do you want to place your X (1-3)?
Input:2
Output:In what row do you want to place your X (1-3)?
Input:2
Output: | | 
Output:-----
Output: |X|
Output:-----
Output: | |
Output:In what column do you want to place your O (1-3)?
...
Output: |O|X
Output:-----
Output:O|X|X
Output:-----
Output:O| |X
Output:Player X wins.
```

## Game 3: Battleships (BONUS)
### Instructions
- Create a Console Project named `Battleships`
- The Rules: 
- Two players
- 10x10 grid per player
- Ships: sizes 5,4,3,2,2
- Ships may be placed vertically or horizontally
  - ships may not overlap and may not touch each other
  - there needs to be at least one empty grid cell around the ship (in every direction)
- players take alternating turns
- player 1 starts
- coordinates are given in the form: g7, a2, d2, etc…
- Feedback “Hit” or “Miss”
- Feedback “Ship sunk!”
- Feedback “Player1 Wins” / “Player2 Wins”
- Bonus: Random AI
- Bonus: Smart AI

### Sample
```
Output:  a b c d e f g h
Output:1
Output:2
Output:3
Output:4
Output:5
Output:6
Output:7
Output:8
Output:Where do you want to place your 5x ship?
Input:a1
Output:Horizontal (y/n)?
Input:y
Output:  a b c d e f g h
Output:1 X X X X X
Output:2
Output:3
Output:4
Output:5
Output:6
Output:7
Output:8
Output:Where do you want to place your 4x ship?
...
Output: Enemy field:
Output:  a b c d e f g h
Output:1 X    
Output:2 O O
Output:3
Output:4     X
Output:5 O
Output:6
Output:7       X
Output:8
Output:Where do you want to shoot?
Input:b1
Output:Hit!
Output:Ship sunk!
Output:  a b c d e f g h
Output:1 X X
Output:2 O O
Output:3
Output:4     X
Output:5 O
Output:6
Output:7       X
Output:8
...
Output: Player Wins!
```

## Done?
Do some Research of your own. This is all I can teach you in this course :)
