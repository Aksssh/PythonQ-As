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
A lambda function is a small anonymous function. A lambda function can take any number of arguments, but can only have one expression.The power of lambda is better shown when you use them as an anonymous function inside another function. For eg:
```
def fun(n):
    return lambda a : a ** n


x = fun( 2)
print(x(2))
```
Lambda functions are defined within an expression and have a limited scope. They are often used as inline functions or passed as arguments to other functions. Regular functions, on the other hand, have their own namespace and can be called from various parts of a program. Lambda functions are typically used for simple, one-line operations. Regular functions, on the other hand, can be more complex and contain multiple lines of code.
Despite these differences, both lambda functions and regular functions can perform similar tasks. The choice between using a lambda function or a regular function depends on the specific requirements and coding style of the program.
#### 5. How does the concept of "scope" apply to functions in Python? Explain the difference between local scope and global scope.
Python Global variables are those which are not defined inside any function and have a global scope whereas Python local variables are those which are defined inside a function and their scope is limited to that function only. local variables are accessible only inside the function in which it was initialized whereas the global variables are accessible throughout the program and inside every function. 
```
def f():

    s = "Local variable"
    print(s)

f()
print(s)
```
NameError: name 's' is not defined pops up when we try to print variable "s" as it is only defined within the function. 
```
g = "Global variable"
print(g)
```
Here, "g" is a Python global variable.
#### 6. How can you use a Python function's "return" statement to return multiple values?
In Python, you can return multiple values by simply separating them with commas in the return statement.
```
def f():
    s = "Local variable"
    return 's is a', s
```
#### 7. What is the difference between the "pass by value" and "pass by reference" concepts when it comes to function arguments in Python?
In the pass-by-value model, when you call a function with a set of arguments, the data is copied into the function. This means that you can modify the arguments however you please and that you won't be able to alter the state of the program outside the function.This looks like the pass-by-value model because we gave it a 3, changed it to a 4, and the change wasn't reflected on the outside (a is still 3).
```
def foo(x):
    x = 4

a = 3
foo(a)
print(a)
```
In a true pass-by-reference model, the called function gets access to the variables of the callee! Sometimes, it can look like that's what Python does, but Python does not use the pass-by-reference model.
def main():
        arg = 4
        square(arg)
        print(arg)
   
    def square(n):
        n *= n

    main()
4
In this case, the arg variable is not altered in place. It seems that Python treats your supplied argument as a standalone value rather than a reference to an existing variable.
Python passes arguments neither by reference nor by value, but by assignment. 
#### 8. Create a function that can intake integer or decimal value and do following operations:
#### a. Logarithmic function (log x)
#### b. Exponential function (exp(x))
#### c. Power function with base 2 (2x)
#### d. Square root
```
import math
def fn():
    num = float(input("Enter number: "))
    log = math.log(num)
    exp = math.exp(num)
    po = math.pow(2,num)
    sq = math.sqrt(num)
    print(f'The log of {num} is {log}')
    print(f'The exponent of {num} is {exp}')
    print(f'The power of {num} with base 2 is {po}')
    print(f'The square root of {num} is {sq}')

fn()
```
#### 9. Create a function that takes a full name as an argument and returns first name and last name.
```
def sep_names():
    fullname = str(input("Please enter your full name: "))
    list1 = fullname.split()
    firstname = list1[0]
    if len(list1) > 1:
        secondname = list1[1]
    if len(list1) > 2:
        thirdname = list1[2]
    print(f'first name : {firstname}')
    if len(list1) == 2:
        print(f'last name : {secondname}')
    elif len(list1) == 3:
        print(f'last name : {thirdname}')
    elif len(list1) == 1:
        print(f'last name not mentioned')
        

sep_names()        
```
