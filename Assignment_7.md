#### 1. Create two int type variables, apply addition, subtraction, division, and multiplications and store the results in variables. Then print the data in the following format by calling the variables:
#### First variable is __ & second variable is __.
#### Addition: __ + __ = __
#### Subtraction: __ - __ = __
#### Multiplication: __ * __ = __
#### Division: __ / __ = __
```
def calc():
    x = float(input("Enter first number: "))
    y = float(input("Enter second number: "))
    print(f'First variable is {x} & second variable is {y}')
    print(f'Addition: {x} + {y} = {x+y}')
    print(f'Subtraction: {x} - {y} = {x-y}')
    print(f'Multiplication: {x} * {y} = {x*y}')
    print(f'Division: {x} / {y} = {x/y}')
calc()
```
#### 2. What is the difference between the following operators:
#### (i) ‘/’ & ‘//’
#### (ii) ‘**’ & ‘^’
(i) In Python, the operators '/' and '//' are both used for division, but they behave differently depending on the operand types and the desired output.
- '/' Operator (Regular Division): The '/' operator performs regular division, also known as floating-point division. It returns the result as a float, regardless of the data types of the operands.
```
result = 7 / 2
print(result)  # Output: 3.5
```
- '//' Operator (Floor Division): The '//' operator performs floor division. It divides the operands and rounds the result down to the nearest whole number (integer), regardless of the operand types.
```
result = 7 // 2
print(result)  # Output: 3
```
(ii) In Python, the operators '**' and '^' are both used for exponentiation, but they have different behaviors and purposes.
- '**' Operator (Exponentiation): It raises the left operand to the power of the right operand.
```
result = 2 ** 3
print(result)  # Output: 8
```
- '^' Operator (Bitwise XOR): The '^' operator is the bitwise XOR (exclusive OR) operator in Python. It performs a bitwise XOR operation between the binary representations of the operands.
```
result = 5 ^ 3
print(result)  # Output: 6
```
#### 3. List the logical operators.
There are three types of logical operators in Python:
- And Operator: used to verify where both conditions associated with it are True Simultaneously. It is represented as "X and Y".
The conditions that can occur are:
  - If Both are True, then the result is True.
  - If one is True and the other is False, the result is False.
  - If both are False, the result is False.

- Or Operator: used to verify that either of the associated conditions is true. It is represented as "X or Y". The conditions that can occur are:
  - If Both are True, the result is True.
  - If One is True and the other is False, the result is True.
  - If both are False, the result is False.
- Not Operator: is associated with a single condition. It inverts the results, i.e., true is changed to false, and false is changed to true. It is represented as "not X". The conditions that occur are:
  - If the condition is True, the result is False.
  - If the condition is False, the result is True.











