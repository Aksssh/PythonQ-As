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
#### 4. Explain the right shift operator and left shift operator with examples.
Shift Operators are used to shift the bits of a number left or right thereby multiplying or dividing the number by two respectively. They can be used when we have to multiply or divide a number by two. 
- Bitwise Left Shift (<<): Shifts the bits of the number to the left and fills 0 on voids right as a result. 
```
a = 5 = 0000 0101 (Binary)
a << 1 = 0000 1010 = 10
```
- Bitwise right shift (>>): Shifts the bits of the number to the right and fills 0 on voids left( fills 1 in the case of a negative number) as a result.
```
a = 10 = 0000 1010 (Binary)
a >> 1 = 0000 0101 = 5
```
#### 5. Create a list containing int type data of length 15. Then write a code to check if 10 is present in the list or not.
```
my_list = []
while len(my_list) <15:
    x = input(f"Enter Number/Numbers (Use Comma seperated values to input multiple digits, takes 1st 15 digits): ")
    y = x
    y.lstrip('-')
    if y.isdigit():
        my_list.append(x)
    elif "," in x:
        num_array = x.split(",")
        i = 0
        while ((len(my_list) < 15) and (i<len(num_array))):
            y = num_array[i].lstrip('-')
            if y.isdigit():
                my_list.append(int(num_array[i]))
            else:
                print(f'{num_array[i]} is not a number')
            i=i+1
    elif not(y.isdigit()):
        print(f'{x} is not a number')
    print(my_list)
if 10 in my_list:
    print("10 is present in the list")
else:
    print("10 not present in the list")
```
