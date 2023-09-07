# Slides 10 - Boolean

- **Booleans** (`bool`) are used to display values, that can be:
  - `YES` or `NO`
  - `ON` or `OFF`
  - `TRUE` or `FALSE`
```cs
bool isWaterBlue = true;
bool isWaterRed = false;
```

## Logical Operators

### NOT

- You can inverse a boolean's value by using an exclamation mark `!` (read it as `NOT`)
  - `!true` -> NOT `true` -> `false`
  - `!false` -> NOT `false` -> `true`
  - 
```cs
bool isWaterNotRed = !isWaterRed; // true
```

### AND

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

### OR

- `||` returns `true`, if at least one incoming value is `true`:
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

### Toggling Bool

You can use `!` to Toggle a `bool` value between two states:
- e.g. for a light switch
- or a checkbox in a menu
- or for whether it's the white player's turn in chess

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

### Between two Values

- To find out, whether a value is between two values, two comparisons are necessary:
- 
```cs
bool isMorning = time > 5 && time < 12
```