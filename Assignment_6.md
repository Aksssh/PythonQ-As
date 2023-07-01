#### 1. What are keywords in Python? Using the keyword library, print all the Python keywords.
Python keywords are special reserved words that have specific meanings and purposes and can't be used for anything but those specific purposes. These cannot be used as variable names, function names, or any other identifiers. 
```
import keyword
keywords = keyword.kwlist
for keyword in keywords:
    print(keyword)
```
#### 2. What are the rules to create variables in Python?
- Rules for variable names in Python:
    - A variable name must start with a letter or the underscore character.
    - A variable name cannot start with a number.
    - A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
    - Variable names are case-sensitive (age, Age, and AGE are three different variables)
    - For Eg: List1, MU, and mu are all possible variable names.
#### 3. What are the standards and conventions followed for the nomenclature of variables in Python to improve code readability and maintainability?  
- Don’t use names that look too general or wordy. Maintain a fine line between the two.
- Use CamelCase only when it makes sense.
- Global variable and Instance variable names normally follow lowercase convention.
- Constant names must be fully capitalized and underscore can add new words to these constants.
- The underscore should be used as a separator while forming a variable with multiple words.
- Do not use Python reserved keywords as variable names (e.g., if, for, while, etc.).
#### 4. What will happen if a keyword is used as a variable name?
Keywords  have a special meaning decided by the language. So we cannot use them as a variable as we cannot assign any value to them. In Python, keywords are case-sensitive so we can use "NOT" as a variable but not "not".
not is a keyword and we will be attempting to use it as a variable name in the code below.
```
not = "Hello world!"
print(not)
```
Output:
```
not = "Hello world!"
        ^
SyntaxError: invalid syntax
```
#### 5. For what purpose def keyword used?
The def keyword is used to create, (or define) a function. All the code that you put between the def function_name(parameters) and end will be executed every time you call the function_name later.
```
def greet(name, message):
    print(f"Hello, {name}! {message}")

greet("Alice", "long time, no see.")
```
Output:
```
Hello, Alice! long time, no see.
```
#### 6. What is the operation of this special character ‘\’?













