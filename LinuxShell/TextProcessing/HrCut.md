# Cut

### HackerRank

## Question

**Objective** 

In this challenge, we practice using the cut command to get and print characters from a file.

**Resources** 

<a href="http://www.folkstalk.com/2012/02/cut-command-in-unix-linux-examples.html">Click</a> here for a tutorial discussing the ways that cut may be used to print characters at a particular position in a file or print columns from a file of delimiter separated values. The latter is particularly useful when dealing with tabulated data (e.g.: *.tsv, *.csv, etc).

**Tasks** 

Given N lines of input, print the 3rd character from each line as a new line of output. It is guaranteed that each of the n lines of input will have a 3rd character.

**Input Format**

A text file containing N lines of ASCII characters.

**Constraints**

* 1 <= N <= 100

**Output Format**

For each line of input, print its 3rd character on a new line for a total of N lines of output.

**Sample Input**
```
Hello
World
how are you
```

**Sample Output**
```
l
r
w
```

## Solutions
```bash
Bash1
#!/bin/bash

## each of the n lines of input will have a 3rd character
cut -c3 /dev/stdin

## Each line should contain just two characters at the  and the  position of the corresponding input line
cut -c2,7 /dev/stdin

## Display a range of characters starting at the  position of a string and ending at the  position (both positions included).
cut -c2-7 /dev/stdin

## Display the first four characters from each line of text.
cut -c-4 /dev/stdin

## Given a tab delimited file with several columns (tsv format) print the first three fields.
cut -d $'\t' -f-3 /dev/stdin
cut -f-3 /dev/stdin
cut -f-3

## Print the characters from thirteenth position to the end.
cut -c13- /dev/stdin

## Given a sentence, identify and display its fourth word. Assume that the space (' ') is the only delimiter between words.
cut -d ' ' -f4

## Given a sentence, identify and display its first three words. Assume that the space (' ') is the only delimiter between words.
cut -d ' ' -f-3

## Given a tab delimited file with several columns (tsv format) print the fields from second fields to last field.
cut -f2-
```