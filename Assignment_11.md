#### 1. What is the role of the 'else' block in a try-except statement? Provide an example scenario where it would be useful.
The 'else' block executes if there's no exception. 
```
def divide(x, y):
    try:
        result = x // y
    except ZeroDivisionError:
        print("Division by Zero.")
    else:
        print("Answer :", result)
```
The code enters the else block only if the try clause does not raise an exception. Else block will execute only when no exception occurs. Example output snippet: divide(3, 2)
```
Answer : 1
```
#### 2. Can a try-except block be nested inside another try-except block? Explain with an example.
Example:
```
def divide_numbers(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        print("Error: Cannot divide by zero.")
    else:
        try:
            if result < 0:
                raise ValueError("Result is negative.")
        except ValueError as ve:
            print(f"Error: {ve}")
        else:
            print(f"The result of the division is: {result}")
```
divide_numbers(10, 2)    
```
The result of the division is: 5.0
```
It starts with the outer try block which is executed, and since there are no errors, it goes to the final 'else' block and prints the result. In the case of divide_numbers(10, 0),
it goes to the first except block which executes the print statement, "Error: Cannot divide by zero." Finally, in the case of divide_numbers(-10, 2), the inner try block is executed
as the if statement raises a ValueError and goes to the nested except statement which prints - "Error: Result is negative."
#### 3. How can you create a custom exception class in Python? Please provide an example that demonstrates its usage.
Python provides an exception-handling method with the help of try-except. Exceptions need to be derived from the Exception class, either directly or indirectly. 
Sometimes we get runtime errors when a standard exception is raised but a generated error does not fall into any category. In such cases, we can "raise" an exception for specific
conditions. 
```
x = int(input("Enter a whole number: "))

if x < 0:
    raise Exception("Number is below zero.")
```
The raise keyword is used to raise an exception. You can define what kind of error to raise, and the text to print to the user.
#### 4. What are some common exceptions that are built-in to Python?
Some common exceptions in Python:
- ArithmeticError: Raised when an error occurs in numeric calculations.
- Exception: Base class for all exceptions.
- EOFError: Raised when the input() method hits an "end of file" condition (EOF)
- ImportError: Raised when an imported module does not exist.
- IndentationError: Raised when indentation is not correct.
- IndexError: Raised when an index of a sequence does not exist.
- KeyError: Raised when a key does not exist in a dictionary.
- SyntaxError: Raised when a syntax error occurs.
- SystemError: Raised when a system error occurs.
- SystemExit: Raised when the sys.exit() function is called.
- TypeError: Raised when two different types are combined.
- ValueError: Raised when there is a wrong value in a specified data type.
- ZeroDivisionError: Raised when the second operator in a division is zero
#### 5. What is logging in Python, and why is it important in software development?
Logging is a way to store information about your script and track events that occur. When writing any complex script in Python, logging is essential for debugging
software as you develop it. Without logging, finding the source of a problem in your code may be extremely time-consuming. Python has a built-in library, logging,
for this purpose. It is simple to create a “logger” to log messages or information that you would like to see. 
The primary purposes of logging in software development are:
- Debugging and Troubleshooting: During the development phase, logging helps developers understand the flow of the program and diagnose issues or bugs. By examining
  the log messages, developers can identify the sequence of events leading to a problem and pinpoint its source more effectively.
- Monitoring and Analysis: In production environments, logging is crucial for monitoring the health and performance of an application. It provides insights into how the
  application is behaving, potential bottlenecks, and areas for optimization.
- Audit Trail: Logging helps create an audit trail of actions and events that occurred in the application. This is valuable for security and compliance purposes,
  as it allows for tracking user activities and changes to critical data.
- Error Reporting: By logging errors and exceptions, developers can gather valuable information about the nature and context of the errors. This information can be used
  to improve error reporting and handle exceptions gracefully, preventing application crashes.
- Documentation and Communication: Logs can serve as documentation of the application's behavior and interactions with external systems. They provide insights into the
  system's overall behavior, which can be useful for communication between development teams, system administrators, and stakeholders.
#### 6. Explain the purpose of log levels in Python logging and provide examples of when each log level would be appropriate.
There are 5 different logging levels that indicate the severity of the logs, shown in increasing severity:

DEBUG: This level is used for detailed and fine-grained information about the application's internal state. It is typically used during development and debugging to track
the flow of the program, variable values, and other debugging information. Example snippet:
```
import logging
logging.basicConfig(level=logging.DEBUG)

def add(x,y):
    logging.debug('variables are %s and %s',x,y)
    return x + y

add(10,3)
```
INFO: The INFO level is used to provide general information about the application's progress and status. It helps indicate the application's normal operational activities
and significant milestones.
```
logging.basicConfig(level=logging.INFO)

def login123(user):
    logging.debug("The user is %s", user)
    return user

login123('Mika')
```
WARNING: This level indicates potential issues that are not severe enough to cause the application to fail but might require attention. Warnings are used to notify developers and
administrators about abnormal situations or potential pitfalls.
```
logging.basicConfig(level=logging.WARNING)

def Balance(amount):
    if amount < 2000:
        logging.debug('Warning! Low balance! your balance is %s', amount)
        
Balance(100)
```
ERROR: The ERROR level is used to report errors that do not prevent the application from functioning but need to be addressed. These could be exceptions caught during the execution
or unexpected behavior that may affect the application's performance.
```
logging.basicConfig(level=logging.ERROR)

def DivByZero(x,y):
    try:
        result = x/y
        print(result)
    except ZeroDivisionError:
        logging.debug('Division by zero')

DivByZero(9,0)
```
CRITICAL: The CRITICAL level is the highest severity level and is used for critical errors that can cause the application to crash or become unusable. These errors require immediate
attention as they represent serious issues.
```
logging.basicConfig(level=logging.CRITICAL)

def CheckSys(x):
    if x != 'ok':
        logging.debug("Your system is about to crash.")
        return x
    
CheckSys('yo')
```
#### 7. What are log formatters in Python logging, and how can you customize the log message format using formatters?
LogFormatters are responsible for converting a LogRecord to (usually) a string which can be interpreted by either a human or an external system. The base Formatter allows a formatting string to be specified. If none is supplied, the default value of '%(message)s' is used, which just includes the message in the logging call. The logging module provides several built-in log formatters, such as logging. Formatter, logging.JSONFormatter, and logging.SimpleFormatter. However, you can also create your custom formatter to meet specific logging requirements.
to create a custom log message format, you can subclass the logging. Formatter class and override its format method to define your desired format. Example:
```
import logging

class CustomFormatter(logging.Formatter):
    def format(self, record):
        return f'[{record.levelname}] {record.name} - {record.message}'
logger = logging.getLogger('my_logger')
logger.setLevel(logging.DEBUG)
custom_formatter = CustomFormatter()
handler = logging.StreamHandler()
handler.setFormatter(custom_formatter)

logger.addHandler(handler)

logger.debug('This is a debug message.')
logger.info('This is an info message.')
```
#### 8. How can you set up logging to capture log messages from multiple modules or classes in a Python application?
To capture log messages from multiple modules or classes in a Python application, you can set up a centralized logging configuration using the logging module. This allows you to have consistent logging behavior across different parts of your application.
1. Creating a logging configuration module
```
import logging

def setup_logging(log_file=None):
    logger = logging.getLogger()
    logger.setLevel(logging.DEBUG)

    formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')

    if log_file:
        file_handler = logging.FileHandler(log_file)
        file_handler.setLevel(logging.DEBUG)
        file_handler.setFormatter(formatter)
        logger.addHandler(file_handler)

    console_handler = logging.StreamHandler()
    console_handler.setLevel(logging.INFO)
    console_handler.setFormatter(formatter)
    logger.addHandler(console_handler)
```
2. Importing the logging configuration module into the application's entry point:
```
# main.py

import log_config
import module1
import module2

if __name__ == "__main__":
    log_config.setup_logging("app.log")

    # Your application code starts here
    module1.some_function()
    module2.another_function()
```
3. Use the logger in other modules and classes:
```
# module1.py

import logging

logger = logging.getLogger(__name__)

def some_function():
    logger.debug('This is a debug message from module1.')
    logger.info('This is an info message from module1.')

# module2.py

import logging

logger = logging.getLogger(__name__)

def another_function():
    logger.debug('This is a debug message from module2.')
    logger.info('This is an info message from module2.')
```
By using __name__ as the logger name, you ensure that each module or class has its own logger instance, making it easier to trace log messages back to their origin. 
This setup captures log messages from multiple modules or classes in your Python application. 
#### 9. What is the difference between the logging and print statements in Python? When should you use logging over print statements in a real-world application?
When you run an algorithm and want to confirm it is doing what you expected, it is natural to add some print() statements at strategic locations to show the program’s state. Printing can help debug simpler scripts, but as your code gets more and more complex, printing lacks the flexibility and robustness that logging has. With logging, you can pinpoint where a logging call came from, differentiate severity between messages, and write information to a file, which printing cannot do. For example, we can turn on and off the message from a particular module of a larger program. We can also increase or decrease the verbosity of the logging messages without changing a lot of code.
#### 10. Write a Python program that logs a message to a file named "app.log" with the following requirements:
#### ● The log message should be "Hello, World!"
#### ● The log level should be set to "INFO."
#### ● The log file should append new log entries without overwriting previous ones.
```
log_file = "app.log"

import logging
logging.basicConfig(level=logging.INFO, format='%(asctime)s:%(levelname)s:%(message)s')
logging.info('Hello World')
```
#### 11. Create a Python program that logs an error message to the console and a file named "errors.log" if an exception occurs during the program's execution. The error message should include the exception type and a timestamp.
```
import logging
import datetime

logging.basicConfig(level=logging.INFO, filename='errors.log', encoding='utf-8')

def log_error_with_timestamp():
    try:
        logging.info('Error message')
        result = 10 / 0
    except Exception as e:
        timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        exception_type = type(e).__name__
        error_message = f"Exception: {exception_type}, Timestamp: {timestamp}"
        logging.error(error_message)

log_error_with_timestamp()

```




