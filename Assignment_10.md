#### 1. What is the role of try and exception block?
When an error occurs, or exception as we call it, Python will normally stop and generate an error message. These exceptions can be handled using the try exception block.
The try block is used to check some code for errors i.e the code inside the try block will execute when there is no error in the program.
Whereas the code inside the except block will execute whenever the program encounters some error in the preceding try block. Without the try block, the program will crash and raise an error. 
```
try:
    x = int(input("Enter an integer: "))
    print(x)
except ValueError:
    print("This is not an integer")
```
Here the except block prints the statement "This is not an integer", when the input is not an integer.
#### 2. What is the syntax for a basic try-except block?
```
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print("The result is:", result)
except ValueError:
    print("Invalid input. Please enter a valid integer.")
except ZeroDivisionError:
    print("Error: Division by zero occurred.")
```
- The try keyword starts the try block and is followed by a colon (:). Inside the try block, you write the code that you suspect might raise an exception.
- If an exception occurs within the try block, Python immediately jumps to the except block without executing any remaining code in the try block.
- The except keyword is followed by the specific exception type you want to catch. You can replace ExceptionType with the specific exception you want to handle, such as ValueError, TypeError, or FileNotFoundError. Alternatively, you can omit the exception type to catch all exceptions, but it is generally recommended to catch specific exceptions whenever possible.
- After the exception type, you write a colon (:). Inside the except block, you write the code to handle the exception. This code will be executed if the corresponding exception occurs in the try block.
#### 3. What happens if an exception occurs inside a try block and there is no matching except block?
If there is no matching except block to handle that specific exception, the exception will propagate up the call stack until it is caught by an appropriate except block or until it reaches the top-level of the program. This is known as an unhandled exception. If the exception is not caught and handled anywhere in the program, it will typically result in the termination of the program's execution.
The program will print an error message, commonly referred to as a stack trace or traceback, which provides information about the unhandled exception and the sequence of function calls that led to it.
#### 4. What is the difference between using a bare except block and specifying a specific exception type?
When you use a bare except block, without specifying any exception type, it catches all exceptions that occur within the try block, regardless of the specific exception type. This can be problematic because it makes it harder to understand and debug the code. It can also inadvertently catch and handle exceptions that you didn't anticipate or intend to handle. Using a bare except block is generally discouraged, as it can lead to silent failures and make it difficult to diagnose and fix issues.
Alternatively, specifying the type of exception you want to catch using the except statement allows you to handle a particular exception type while letting other exceptions propagate up the call stack.
#### 5. Can you have nested try-except blocks in Python? If yes, then give an example.
We can have nested try-except blocks in Python. In this case, if an exception is raised in the nested try block, the nested except block is used to handle it. In case the nested except is not able to handle it, the outer except blocks are used to handle the exception.
```
try:
   print("outer try block")
   try:
       print("Inner try block")
       print(10/0)
   except NameError:
       print("Inner except block")
   finally:
       print("Inner finally block")
except:
   print("outer except block")
finally:
   print("outer finally block")
```
Output:
```
outer try block
Inner try block
Inner finally block
outer except block
outer finally block
```
This code executes the outer try block, followed by the inner try block. There's no exception in this case so goes to the inner finally block followed by the exception
handled by the outer except block and then executes the outer finally block.
#### 6. Can we use multiple exception blocks, if yes then give an example.
One can handle different exceptions all using a single block of code, they can be grouped together in a tuple as shown in the code given below:
```
try:
    f = open(filename)
except (FileNotFoundError, PermissionError):
    ...
```
#### 7. Write the reason due to which the following errors are raised:
- EOFError - "End of File Error", it is a type of exception that occurs when an input operation tries to read beyond the end of a file or stream. It is raised when there is no more data to be read from a file or an input source.
```
try:
    user_input = input("Enter a value: ")
except EOFError:
    print("End of input reached.")
```
- FloatingPointError - Floating-point operations include mathematical calculations involving floating-point numbers, such as division, multiplication, addition, and subtraction. The FloatingPointError exception is specifically raised when an error occurs during these operations, typically due to special floating-point values like infinity, NaN (Not a Number), or when the result of a calculation is too large or too small to be represented accurately. This exception is derived from the built-in ArithmeticError class.
```
try:
    result = 1.0 / 0.0 
except FloatingPointError:
    print("A FloatingPointError occurred. Please check your calculations.")
```
- IndexError - This type of exception in Python that is raised when you try to access an index of a sequence (such as a list, tuple, or string) that is out of range. It occurs when you attempt to access an element at an invalid index or when an operation expects a certain index that does not exist in the sequence.
```
my_list = [1, 2, 3]
try:
    value = my_list[5] 
except IndexError:
    print("An IndexError occurred. The index is out of range.")
```
- MemoryError -  This type of exception in Python that is raised when an operation fails due to insufficient memory. It occurs when a program tries to allocate more memory than is available. 
```
try:
    data = [0] * (10 ** 9) 
except MemoryError:
    print("A MemoryError occurred. Insufficient memory.")
```
- OverflowError - This type of exception in Python that is raised when a calculation exceeds the maximum limit of a numeric type. It occurs when an arithmetic operation results in a value that is too large to be represented by the numeric type being used.
```
try:
    result = 10 ** 1000 
except OverflowError:
    print("An OverflowError occurred. The calculation result is too large.")
```
- TabError - This type of exception in Python that is raised when there is an issue with the indentation of code using tabs and spaces inconsistently. It occurs when the Python interpreter encounters an indentation error due to mixing tabs and spaces or inconsistent use of indentation.
```
try:
    if condition:
    \tprint("Indented line")  # Indentation using a tab character
except TabError:
    print("A TabError occurred. Check the indentation in your code.")
```
- ValueError - This type of exception in Python that is raised when an operation or function receives an argument of the correct data type but an inappropriate value. It occurs when the input value is of the correct type, but the value itself does not conform to the requirements of the operation.
```
import math

try:
    math.sqrt(-100)
except ValueError:
    print('Positive number expected for square root operation')
```
#### 8. Write code for the following given scenario and add try-exception block to it.
#### a. Program to divide two numbers





