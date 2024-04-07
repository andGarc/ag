+++
title = 'Switch Case Replacement in Python'
date = 2023-06-13
draft = false
tags = ['python']
description = 'How-to implement a switch case in python'
+++

## TL;DR 
- Before version 3.10, Python never had a feature similar to the switch statement in other programming languages  
- Dictionary mapping can be used as a work around
- Keys act as cases in a switch statement  

>Why did the Python dictionary break up with the JS object?  
>Because the dictionary found the object too "undefined"   

## Implementing a switch case replacement using Python dictionary mapping 

A switch statement in Java might look like this:
```java
// switch case to get the string representation of month number
int month = 1;
String monthString;
switch(month) {
    case 1: month = "January";
            break;
    case 2: month = "February";
            break;
    .
    .
    .
    default: month = "Invalid Month";
            break;
}

System.out.println("Month " + month + " is " + monthString);
// Month 1 is January
```

Python dictionaries contain `key:value` pairs.  
The dictionary keys act as cases in a switch statement.   

Switch case replacement in Python:  
```python
# Function to get the string representation of a month number
def month_num_to_string(month):
    switcher = {
        1: 'January',
        2: 'February',
        .
        .
        .
    }

    # get() returns the value of a key,
    # otherwise the default value is returned
    return switcher.get(month, 'Invalid Month')

month = 1
print(f"Month #{month} is month_num_to_string(month)}") 
# Month 1 is January
```

