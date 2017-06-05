# The World of Numbers

### HackerRank

## Question

Given two integers, X and Y, find their sum, difference, product, and quotient.

**Input Format** 

Two lines containing one integer each (X and Y, respectively).

**Input Constraints** 

* -100 <= X,Y <= 100
* Y != 0

**Output Format** 

Four lines containing the sum `(X+Y)`, difference `(X-Y)`, product `(X*Y)`, and quotient `(X/Y)`, respectively. 

(While computing the quotient, print only the integer part.)

**Sample Input**
```
5  
2
```

**Sample Output**
```
7
3
10
2
```

**Reference Resources** 

A <a href="https://unix.stackexchange.com/questions/93029/how-can-i-add-subtract-etc-two-numbers-with-bash">relevant and interesting discussion</a> on Stack-Exchange for those getting started with handling numbers and arithmetic operations in Bash.

## Solutions
* Bash1
```bash
#!/bin/bash

read X
read Y
echo $(($X+$Y))
echo $(($X-$Y))
echo $(($X*$Y))
echo $(($X/$Y))
```
