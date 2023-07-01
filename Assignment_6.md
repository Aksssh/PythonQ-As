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
In Python, the backslash '' serves as an escape character and has several uses.
1. Some commonly used escape sequences include:
- '\n' represents a newline character.
- '\t' represents a tab character.
- '\r' represents a carriage return character.
- '\' represents a literal backslash character.
2. Multi-Line Strings: The backslash can be used to indicate that a string literal spans multiple lines. When you end a line with a backslash, it signifies that the string continues on the next line without including a newline character. This is useful when you want to write long strings without line breaks.
3. Raw Strings: The backslash can be used to create raw strings by prefixing a string literal with 'r'. In a raw string, escape sequences are treated as literal characters and are not interpreted. This is particularly useful when working with regular expressions or file paths, as it allows you to avoid escaping backslashes.
```
raw_string = r"C:\path\to\file.txt"
```
#### 7. Give an example of the following conditions:
#### (i) Homogeneous list
#### (ii) Heterogeneous set
#### (iii) Homogeneous tuple
```
(i) int_list = [1,2,3,4]
(ii) het_list = [1,2,3,"hi",9.2,[2,4]]
(iii) hom_tup = ("Apple","Mango","Avocado")
```
#### 8. Explain the mutable and immutable data types with proper explanations & examples.
There are 3 mutable data types in Python:
1. List: A list data structure is an ordered sequence of elements in Python, that is mutable, or changeable.
```
my_list = [1,2,3,4,5]
my_list.append(10)
print(my_list)
```
Output:
```
[1,2,3,4,5,10]
```
2. Dictionary: It is an unordered collection of items. Each item of a dictionary has a key/value pair, using which we can access a particular key or value of a dictionary. Keys in dictionaries are unique in nature. We can modify, remove or add values of existing items in a dictionary using the assignment operator.
```
my_dict = {"state":"WB", "Capital":"Kolkata"}
my_dict['Country'] = "India"
print("Dictionary after adding a new key-value pair = ",my_dict)
```
Output:
```
Dictionary after adding a new key-value pair =  {'state': 'WB', 'Capital': 'Kolkata', 'Country': 'India'}
```
3. Set: This is an unordered collection of items in Python. All the elements of the set are unique in nature, that is, there are no duplicates in a set. Also, the elements of the set are immutable in nature, that is, they cannot be changed. However, a set itself is mutable in Python. That means we can add or remove elements from a set in Python. Hence, we can perform operations in a set that can modify the overall set.
```
my_set = {1,2,6,5,7,11}
my_set.add(16)
print("Set after adding a value: ",my_set)
```
Output:
```
Set after adding a value:  {16, 1, 2, 5, 6, 7, 11}
```
Immutable data types: These are objects that cannot be modified or altered after they have been created. These objects become permanent once created and initialized, and they form a critical part of data structures used in Python. Python is used in numbers, tuples, strings, frozen sets, and user-defined classes with some exceptions. They cannot change, and their values and it remains permanent once they are initialized hence called immutable. Eg: Int, Float, Tuple, etc.
#### 9. Write a code to create the given structure using only for a loop.
```
    *
   ***
  *****
 *******
*********
```
```
n = 5
for i in range(1,n+1):
    string = ''
    for j in range(n-i):
        string = string + ' '
    for j in range(2*i-1):
        string = string + '*'
    print(string)
```
#### 10. Write a code to create the given structure using while loop    
```
n = 5
i = n
while i>0:
    print(' '*(n-i) + "|"*(2*(i) - 1))
    i-=1
```












