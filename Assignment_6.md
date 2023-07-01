#### 1. What are keywords in Python? Using the keyword library, print all the Python keywords.
Python keywords are special reserved words that have specific meanings and purposes and can't be used for anything but those specific purposes. These cannot be used as variable names, function names, or any other identifiers. 
import keyword
keywords = keyword.kwlist
for keyword in keywords:
    print(keyword)
