For each button inside the menu a button permission can be set. The permission is coded to the end of a NC name and is surrounded by `{}`. It contains KEYWORDS and OPERATORS.

## OPERATORS (listed in order of their precedence)

| Operator | Description         |
|----------|---------------------|
| `!`      | means a logical NOT |
| `&`      | means a logical AND |
| `~`      | means a logical OR  |

Operators may be surrounded by spaces
## KEYWORDS (case insensitive)

| Keyword          | Description                            |
|------------------|----------------------------------------|
| `owner`          | checks if the user is the object owner |
| `group`          | checks if the active group of the user is equal to the group of the object |
| `seated`         | checks if the user is seated           |
| any integer      | counts as a seatNumber: checks if the user is sitting on the seat with the specified number |
| any other string | counts as a permission registered by a plugin, see [[User Defined Permission]] |

## Examples:

`SET:Button{1~3}`  
The Button is shown if the user is seated on seat number 1 or 3

`SET:Button{owner~2}`  
The Button is shown to the object owner and also to anyone sitting on seat number 2

`SET:Button{owner & !victim}`  
The button is shown to the object owner, but only if he/she isn't a victim (victim is a [[User Defined Permission]] used by the new RLV+ plugin)

`SET:Button{1 ~ 3 & group}`  
The button is shown to the user on seat 1.The button is also shown to the user on seat 3 if he/she has the same active group as the Object.

`SET:Button{seated ~ owner}`  
The button is shown to anybody who sits and also to the object owner.

##Hints

- you can add a button permission to the root menu. For example: `BTN{owner}`
- Button Permissions are inheritable
- Button Permissions must be the last thing to appear in NC name.  They cannot appear in the middle somewhere.