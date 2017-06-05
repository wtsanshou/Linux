# Tr Command

### HackerRank

## Question

**Objective** 
In this challenge, we practice using the tr command because it is a useful translation tool in Linux.

**Resources** 

**For example:** 

`e` being transformed to `E`
```bash
$ echo "Hello" | tr "e" "E"
HEllo
```

Spaces being transformed to hyphens
```bash
$ echo "Hello how are you" | tr " " '-'
Hello-how-are-you
```

Digits (numerals) being deleted
```bash
$ echo "Hello how are you 1234" | tr -d [0-9]
Hello how are you 
```

**Task** 

In a given fragment of text, replace all parentheses `()`  with box brackets `[]` .

**Input Format**

A block of ASCII text.

**Output Format**

Output the text with all parentheses `()`  with box brackets `[]` .

**Sample Input**
```
int i=(int)5.8
(23 + 5)*2
```

**Sample Output**
```
int i=[int]5.8
[23 + 5]*2
```

**Recommended References**

This <a href="http://www.thegeekstuff.com/2012/12/linux-tr-command/">tutorial</a> shows various ways that the tr command may be used for transforming or translating characters or character classes. It can also be used to delete, complement, remove or squeeze characters.

## Solutions
```bash
#!/bin/bash

## In a given fragment of text, replace all parentheses `()`  with box brackets `[]` .
tr "()" "[]"
tr "(" "[" | tr ")" "]"

## In a given fragment of text, delete all the lowercase characters a-z.
tr -d [a-z]

## In a given fragment of text, replace all sequences of multiple spaces with just one space.
tr -s ' '
tr -s " "
```

