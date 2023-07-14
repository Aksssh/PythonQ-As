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



















