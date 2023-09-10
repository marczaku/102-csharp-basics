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

## Negating Logical Operators:

### NOT
- The negation of "Not allowed to play"
- Is "Allowed to play"
```cs
!(!A) = A
```

### AND
- The negation of "Touches Ground" AND "Press Jump"
- Is "Does Not Touch Ground" OR "Does not press Jump"
```cs
!(A && B) = !A || !B
```

### OR
- The negation of "Has ID" OR "Has Passport"
- Is "Has NO ID" AND "Has No Passport"
```cs
!(A || B) = !A && !B
```

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

```cs
bool isMorning = time > 5 && time < 12
```

### Negation of Comparison Operators

- You can simplify the negation of comparison operators:

```cs
!(money > 100) /* same as */ money <= 100;
!(money < 100) /* same as */ money >= 100;
!(money == 100) /* same as */ money != 100;
```

Think about it:

- What is the opposite of having more than 100 Gold?
- It's not having less than 100 Gold.
- It's having less than or exactly 100 Gold.

| Input Gold | Gold > 100 | Gold < 100 | Gold <= 100 |
|:----------:|:----------:|:----------:|:-----------:|
|     50     |     ❌      |     ✅      |      ✅      |
|    100     |     ❌      |     ❌      |      ✅      |
|    150     |     ✅      |     ❌      |      ❌      |

You can read them both ways, because:
- the opposite of the opposite of a statement is the original statement:

```cs
!(!(A)) /* same as */ A;
```

```cs
!(!(true))
/* = */ !(false)
/* = */ true
```

## Combining Both

### Negation

```cs
bool canBuyBeer = age >= 20 && money > 5;
```

```cs
bool canNotBuyBeer = !(age >= 20 && money > 5);
bool canNotBuyBeer = age < 20 || money <= 5;
```

### Simplification

```cs
bool jump = (canJump && pressSpace) || (canJump and click);
bool jump = canJump && (pressSpace || click);
```

```cs
bool canBuy = hasMoney || (!hasMoney && canTakeLoan);
bool canBuy = hasMoney || canTakeLoan;
```