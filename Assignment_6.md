#### 1. In Python, what is the difference between a built-in function and a user-defined function? Provide an example of each.
Built-in Function:
A built-in function is a pre-defined function provided by the Python programming language. These functions are readily available for use without requiring any additional
code or import statements. Built-in functions are implemented in C and are part of Python's standard library. Examples of built-in functions in Python include print(), len(),
and range().
```
print("Hello, world!")
```
User-defined Function:
A user-defined function is created by the user to perform a specific task or set of tasks. These functions are defined using the def keyword followed by a function name,
parentheses for optional parameters, and a colon. 
```
Add = lambda x,y : x + y
print(Add(3,4)
```
#### 2. How can you pass arguments to a function in Python? Explain the difference between positional arguments and keyword arguments.
Positional Arguments:
Positional arguments are the most basic way to pass arguments to a function. They are defined and passed based on their position or order. The function receives the arguments in
the same order as they are passed.
```
def greet(name, message):
    print(f"Hello, {name}! {message}")
greet("Alice","long time, no see.")
```
Keyword Arguments:
Keyword arguments are passed to a function using the name of the argument along with the corresponding value. The order of the arguments doesn't matter, as long as the
argument names are specified correctly.
```
def greet(name, message):
    print(f"Hello, {name}! {message}")
greet(message = "what's up", name = "Ron")
```
#### 3. What is the purpose of the return statement in a function? Can a function have multiple return statements? Explain with an example.
A return statement is used to end the execution of the function call and “returns” the result (value of the expression following the return keyword) to the caller. The statements
after the return statements are not executed. If the return statement is without any expression, then the special value None is returned.
```
def absolute_difference(a, b):
    difference = a - b
    if difference >= 0:
        return diff
    else:
        return -diff

# Calling the function
r1 = absolute_difference(5, 3)
r2 = absolute_difference(3, 5)

print(r1)  
print(r2) 
```
The function 'absolute_difference()' calculates the difference between a and b. The function has two return statements, each associated with a different value. Depending on the input values,
the function will execute the appropriate return statement and return the corresponding result. when a return statement is executed, the function exits immediately, and any code or statements after the return statement within the same block will not be executed.
Therefore, if a function has multiple return statements, only the one corresponding to the executed condition will be reached, and the function will terminate at that point.
#### 4. What are lambda functions in Python? How are they different from regular functions? Provide an example where a lambda function can be useful.











