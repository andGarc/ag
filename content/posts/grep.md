+++
title = 'grep'
date = 2021-02-23T19:11:34-05:00
draft = false
tags = ['unix']
Description = 'A popular unix command line utility for searching plain text in files. '
ShowToc = true
weight = 0
+++

Simple use  
`grep wordToSearchFor fileName`

You can take the output from a previous command and pipe it to grep    
`cat fileName | grep wordToSearchFor`

You can also look at multiple files using grep   
`grep word *.fileExtension`

## The Grep Basics
At its core, grep is simple. You tell it the **word to search for** and 
the **file to search in**  
`grep wordToSearchFor fileName`  

For example, to find all lines containing "error" in the file "server.log", you'd use:  
`grep error server.log`

### Flags
Flags to fine-tune your search  

#### Counting occurrences
Use `-c` to see how many times a word appears 
`grep -c warning system.log`

#### Case-insensitive search
 Make grep ignore case with `-i`  
`grep -i LOG system.log`  

#### Negating the search
 Find lines without a specific word using `-v`  
`grep -v critical system.log`  

#### Matching entire lines
Only show lines that exactly match the search term with `-x`  
`grep -x "Internal Server Error" error.log`

#### Matching whole words
Ensure the search term is a complete word with `-w`  
`grep -w root /etc/passwd`

## Some Advanced Techniques

### Combining searches
Use `\|` (pipe symbol) to search for multiple options  
`grep '404\|500' access.log`

### Character ranges
Find lines with numbers between 400 and 499  
`grep '4[0-9][0-9]' access.log`

### Anchors

`^`: Matches the beginning of a line  
`grep '^root:' /etc/passwd`

`$`: Matches the end of a line  
`grep 'logout$' user_activity.log`  

`\b`: Matches the beginning or end of a word  
`grep '\berror\b' system.log`

### Peeking around matches

`-B` shows lines **before** the match  
`grep -w -B 2 error system.log`  

`-A` shows lines **after** the match  
`grep -w -A 2 error system.log`  

`-C` shows lines **before and after** the match    
`grep -w -C 3 error system.log`

## Putting it all Together

Imagine you're troubleshooting a web server and suspecting database connection issues. You can use grep to:

1. Search for "database error" messages  
`grep 'database error' error.log`  

2. Count the occurrences  
`grep -c 'database error' error.log`

3. See the surrounding context  
`grep -w 'database error' -C 3 error.log`

---
Future:  
    - How does grep work?





