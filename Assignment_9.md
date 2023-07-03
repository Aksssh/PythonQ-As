#### 1. What is a lambda function in Python, and how does it differ from a regular function?
A lambda function is an anonymous function (i.e., defined without a name) that can take any number of arguments but, unlike normal functions, evaluates and returns only one expression. Unlike a normal function, we don't surround the parameters of a lambda function with parentheses. There is no return keyword defined explicitly because the lambda function does return an object by default.
- Lambda Function
    - Defined using the lambda keyword followed by the parameter list.
    - Typically used for simple, one-line operations.
    - Can be used inline within other code or passed as arguments.
    - Shorter and more concise syntax.
    - Anonymous functions with no explicit function name.
    - eg: lambda x: x + 1
- User-defined functions
    - Defined using the def keyword and a function name.
    - Used for more complex operations and reusable code.
    - Usually defined separately and called by their function name.
    - Longer syntax with more explicit function definition.
    - Functions defined with a specific name.
    - Eg: def increment_by_one(x):
               return x + 1
#### 2. Can a lambda function in Python have multiple arguments? If yes, how can you define and use them?
Python lambda can be used with multiple arguments and these arguments are used in evaluating an expression to return a single value. For a lambda function with multiple arguments, the input parameters are separated by a comma. The corresponding arguments follow the same order at the time of execution.
```
fn = lambda x, y, z: x**2 + y**2 + z**2
fn(1,2,3)
```
Output:
```
14
```
There are three args used in the example above.
#### 3. How are lambda functions typically used in Python? Provide an example use case.
In Python, we generally use Lambda Functions as an argument to a higher-order function (a function that takes in other functions as arguments). Lambda functions can have any number of arguments but they have only one expression. First of all, the expression is evaluated and then returned.
- The syntax of the lambda function, as shown above, has three elements:
    - The keyword “lambda” — is analogous to ‘def’ in user-defined functions
    - parameters — analogous to arguments in normal functions
    - expression — it is the operation that gets evaluated to arrive at the result.
```
double = lambda x: x * 2
```
#### 4. What are the advantages and limitations of lambda functions compared to regular functions in Python?
- The main ways lambda expressions are different from def:
    - They can be immediately passed around (no variable needed)
    - They can only have a single line of code within them
    - They return automatically
    - They can’t have a docstring and they don’t have a name
    - They use a different and unfamiliar syntax
- Pros of Lambda Functions:
    - Concise Syntax: Lambda functions have a compact and concise syntax, allowing you to define functions in a single line. This can make your code more concise and readable, especially for simple operations.
    - Functional Programming: Lambda functions align well with functional programming principles. They are often used with higher-order functions like map(), filter(), and reduce(), enabling a more functional programming style.
    - Inline Usage: Lambda functions can be defined and used inline within other code, such as passing them as arguments to other functions. This reduces the need for creating separate named functions, making your code more compact and expressive.
    - Reduced Name Clutter: Since lambda functions are anonymous, they don't require a specific name. This can be advantageous when you only need a short-lived function without cluttering the namespace with unnecessary names.
- Cons of Lambda Functions:
    - Limited Functionality: Lambda functions are limited to a single expression and cannot contain multiple statements or complex logic. This restriction makes them unsuitable for more intricate tasks that require additional logic or control flow.
    - Lack of Readability for Complex Operations: While lambda functions can improve readability for simple operations, they can become less readable as complexity increases. Writing a regular function with a clear name and appropriate indentation can enhance code understandability.
    - Lack of Reusability: Lambda functions are generally not reusable since they are anonymous and don't have a specific name. If you need to reuse a function in multiple places or want to provide meaningful documentation, regular functions with explicit names are preferable.
    - Limited Flexibility: Lambda functions lack certain features available in regular functions, such as default arguments, variable annotations, and the ability to use statements like a return or yield inside the function body. This restricts their flexibility for more complex scenarios.
#### 5. Are lambda functions in Python able to access variables defined outside of their own scope? Explain with an example.
Lambda functions in Python can access variables defined outside of their own scope. This behavior is known as lexical scoping or closure. 
```
def myfunc(n):
  return lambda a : a * n

mydoubler = myfunc(2)

print(mydoubler(11))
```
We can change the function such that it triples the number sent in.
```
mytripler = myfunc(3)

print(mytripler(11))
```
Lambda functions can access and "remember" variables from their enclosing scopes, making them useful in scenarios where you want to create functions with access to specific variables without explicitly passing them as arguments.
#### 6. Write a lambda function to calculate the square of a given number.
```
sq = lambda x: x ** 2
sq(5)
```
Output:
```
25
```
#### 7. Create a lambda function to find the maximum value in a list of integers.
```
my_list = [34, 5, 7, 90, 6, -2, -91, 0]
max_val = max(my_list, key = lambda x: x)
print(max_val)
```
#### 8. Implement a lambda function to filter out all the even numbers from a list of integers.
```
my_list = [34, 5, 7, 90, 6, -2, -91, 0]
even_list = filter(lambda x: x % 2 == 0, my_list)
print(list(even_list))
```
#### 9. Write a lambda function to sort a list of strings in ascending order based on the length of each string.
```
my_list = ['manifesting', 'good', 'day', 'for', 'all those', 'who', 'read this code']
sort_string = sorted(my_list, key = lambda x: len(x))
print(list(sort_string))
```
#### 10. Create a lambda function that takes two lists as input and returns a new list containing the common elements between the two lists.
```











