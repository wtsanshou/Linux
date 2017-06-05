# Cut 1

### HackerRank

## Question

**Objective** 

In this challenge, we practice using the cut command to get and print characters from a file.

**Resources** 

<a href="http://www.folkstalk.com/2012/02/cut-command-in-unix-linux-examples.html">Click</a> here for a tutorial discussing the ways that cut may be used to print characters at a particular position in a file or print columns from a file of delimiter separated values. The latter is particularly useful when dealing with tabulated data (e.g.: *.tsv, *.csv, etc).

**Task** 

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

cut -c3 /dev/stdin
```