# A Personalized Echo

### HackerRank

## Question

Write a Bash script which accepts  as input and displays a greeting: "Welcome (name)"

A Quick Introduction to `Echo`

This is the equivalent of common output commands in most programming language (print or puts statements).

**For Example:**

`echo "Greetings"`

This outputs just one word "Greetings" (without the quotation marks).

`echo "Greetings $USER, your current working directory is $PWD"`

This picks up the values of the environment variables  and  and displays something like:

**Greetings prashantb1984, your current working directory is /home/prashantb1984**

The above message, of course, will vary from system to system, depending on the setting of environment variables.

**Accepting Inputs**

This can be accomplished using the read statement.
```bash
read number
echo "The number you have entered is $number"  
```

If the user provides an input 4, the output is:

`The number you have entered is 4` 

Consider this snippet:
```bash
read name
echo "The name you have entered is $name"  
```

If the user provides an input `Max`, the output is:

`The name you have entered is Max` 

**Input Format**

One line, containing a .


**Output Format**

One line: "Welcome (name)" (quotation marks excluded). 

The evaluation will be case-sensitive.

**Sample Input 0**
```
Dan  
```

**Sample Output 0**
```
Welcome Dan  
```

**Sample Input 1**
```
Prashant
```

**Sample Output 1**
```
Welcome Prashant
```

## Solutions

* Bash1
```bash
#!/bin/bash

read NAME
echo "Welcome $NAME"
```