# Operations

## Operands and Operators

An **operand** is a value that is operated on by an **operator**. For example, in the expression `1 + 2`, the operands are `1` and `2`, and the operator is `+`.

## Arithmetic Operators

The following table lists the arithmetic operators in Python. The first four operators are the basic arithmetic operators. The last two operators are the floor division and modulo operators, respectively.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `+` | Addition | `1 + 2` | `3` |
| `-` | Subtraction | `1 - 2` | `-1` |
| `*` | Multiplication | `1 * 2` | `2` |
| `/` | Division | `1 / 2` | `0.5` |
| `//` | Floor Division | `1 // 2` | `0` |
| `%` | Modulo | `1 % 2` | `1` |

## Comparison Operators

The following table lists the comparison operators in Python. These operators compare two operands and evaluate to either `True` or `False`.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `==` | Equal To | `1 == 2` | `False` |
| `!=` | Not Equal To | `1 != 2` | `True` |
| `>` | Greater Than | `1 > 2` | `False` |
| `>=` | Greater Than or Equal To | `1 >= 2` | `False` |
| `<` | Less Than | `1 < 2` | `True` |
| `<=` | Less Than or Equal To | `1 <= 2` | `True` |



## Logical Operators

The following table lists the logical operators in Python. These operators combine two or more boolean expressions and evaluate to either `True` or `False`.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `and` | Logical AND | `True and False` | `False` |
| `or` | Logical OR | `True or False` | `True` |
| `not` | Logical NOT | `not True` | `False` |

## Bitwise Operators

The following table lists the bitwise operators in Python. These operators combine two or more bit patterns and evaluate to a new bit pattern.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `&` | Bitwise AND | `0b101 & 0b110` | `0b100` |
| `|` | Bitwise OR | `0b101 | 0b110` | `0b111` |
| `^` | Bitwise XOR | `0b101 ^ 0b110` | `0b011` |
| `~` | Bitwise NOT | `~0b101` | `0b010` |
| `<<` | Bitwise Left Shift | `0b101 << 1` | `0b1010` |
| `>>` | Bitwise Right Shift | `0b101 >> 1` | `0b10` |

## Assignment Operators

The following table lists the assignment operators in Python. These operators assign a value to a variable.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `=` | Assignment | `x = 1` | `1` |
| `+=` | Addition Assignment | `x += 1` | `2` |
| `-=` | Subtraction Assignment | `x -= 1` | `1` |
| `*=` | Multiplication Assignment | `x *= 2` | `2` |
| `/=` | Division Assignment | `x /= 2` | `1` |
| `//=` | Floor Division Assignment | `x //= 2` | `0` |
| `%=` | Modulo Assignment | `x %= 2` | `1` |
| `&=` | Bitwise AND Assignment | `x &= 0b101` | `0b101` |

## Identity Operators

The following table lists the identity operators in Python. These operators compare the memory addresses of two operands and evaluate to either `True` or `False`.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `is` | Identity | `1 is 1` | `True` |
| `is not` | Non-Identity | `1 is not 1` | `False` |

## Membership Operators

The following table lists the membership operators in Python. These operators evaluate to either `True` or `False` depending on whether a value is a member of a sequence.

| Operator | Description | Example | Result |
| --- | --- | --- | --- |
| `in` | Membership | `1 in [1, 2, 3]` | `True` |
| `not in` | Non-Membership | `1 not in [1, 2, 3]` | `False` |

## Operator Precedence

The following table lists the operator precedence in Python. Operators with higher precedence are evaluated before operators with lower precedence. Operators with the same precedence are evaluated from left to right.

| Operator | Description |
| --- | --- |
| `()` | Parentheses |
| `**` | Exponentiation |
| `~` | Bitwise NOT |
| `*`, `/`, `//`, `%` | Multiplication, Division, Floor Division, Modulo |
| `+`, `-` | Addition, Subtraction |
| `<<`, `>>` | Bitwise Left Shift, Bitwise Right Shift |
| `&` | Bitwise AND |
| `^` | Bitwise XOR |
| `|` | Bitwise OR |
| `==`, `!=`, `>`, `>=`, `<`, `<=`, `is`, `is not`, `in`, `not in` | Comparison, Identity, Membership |
| `not` | Logical NOT |
| `and` | Logical AND |
| `or` | Logical OR |
| `=` | Assignment |
| `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `&=`, `^=`, `|=`, `<<=`, `>>=` | Assignment Operators |

## Operator Associativity

The following table lists the operator associativity in Python. Operators with left associativity are evaluated from left to right. Operators with right associativity are evaluated from right to left.

| Operator | Associativity |
| --- | --- |
| `**` | Right |
| `~` | Right |
| `*`, `/`, `//`, `%` | Left |
| `+`, `-` | Left |
| `<<`, `>>` | Left |
| `&` | Left |
| `^` | Left |
| `|` | Left |
| `==`, `!=`, `>`, `>=`, `<`, `<=`, `is`, `is not`, `in`, `not in` | Left |
| `not` | Right |
| `and` | Left |
| `or` | Left |
| `=` | Right |
| `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `&=`, `^=`, `|=`, `<<=`, `>>=` | Right |

## Operator Overloading


## Operator Overloading Methods

The following table lists the operator overloading methods in Python. These methods are called when an operator is used on an object.

| Operator | Method | Description |
| --- | --- | --- |
| `+` | `__add__` | Addition |
| `-` | `__sub__` | Subtraction |
| `*` | `__mul__` | Multiplication |
| `/` | `__truediv__` | Division |
| `//` | `__floordiv__` | Floor Division |
| `%` | `__mod__` | Modulo |
| `**` | `__pow__` | Exponentiation |
| `<<` | `__lshift__` | Bitwise Left Shift |
| `>>` | `__rshift__` | Bitwise Right Shift |
| `&` | `__and__` | Bitwise AND |
| `^` | `__xor__` | Bitwise XOR |
| `|` | `__or__` | Bitwise OR |
| `==` | `__eq__` | Equality |
| `!=` | `__ne__` | Inequality |
| `<` | `__lt__` | Less Than |
| `<=` | `__le__` | Less Than or Equal To |
| `>` | `__gt__` | Greater Than |
| `>=` | `__ge__` | Greater Than or Equal To |
| `()` | `__call__` | Call |
| `[]` | `__getitem__` | Index |
| `[]` | `__setitem__` | Index Assignment |
| `[]` | `__delitem__` | Index Deletion |

## Operator Overloading Examples

The following table lists the operator overloading examples in Python. These examples show how to use the operator overloading methods.

| Operator | Example | Method | Description |
| --- | --- | --- | --- |
| `+` | `1 + 2` | `__add__` | Addition |
| `-` | `1 - 2` | `__sub__` | Subtraction |
| `*` | `1 * 2` | `__mul__` | Multiplication |
| `/` | `1 / 2` | `__truediv__` | Division |
| `//` | `1 // 2` | `__floordiv__` | Floor Division |
| `%` | `1 % 2` | `__mod__` | Modulo |
| `**` | `1 ** 2` | `__pow__` | Exponentiation |
| `<<` | `1 << 2` | `__lshift__` | Bitwise Left Shift |
| `>>` | `1 >> 2` | `__rshift__` | Bitwise Right Shift |
| `&` | `1 & 2` | `__and__` | Bitwise AND |
| `^` | `1 ^ 2` | `__xor__` | Bitwise XOR |
| `|` | `1 | 2` | `__or__` | Bitwise OR |
| `==` | `1 == 2` | `__eq__` | Equality |
| `!=` | `1 != 2` | `__ne__` | Inequality |
| `<` | `1 < 2` | `__lt__` | Less Than |
| `<=` | `1 <= 2` | `__le__` | Less Than or Equal To |
| `>` | `1 > 2` | `__gt__` | Greater Than |
| `>=` | `1 >= 2` | `__ge__` | Greater Than or Equal To |
| `()` | `f(1, 2)` | `__call__` | Call |
| `[]` | `a[1]` | `__getitem__` | Index |
| `[]` | `a[1] = 2` | `__setitem__` | Index Assignment |
| `[]` | `del a[1]` | `__delitem__` | Index Deletion |



