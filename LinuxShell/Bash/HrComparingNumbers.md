# Comparing Numbers

### HackerRank

## Question

Given two integers, X and Y, identify whether X<Y or X>Y or X=Y.

Comparisons in a shell script may either be accomplished using `regular operators (such as < or >)` or using `(-lt, -gt, -eq, i.e. less than, greater than, equal to) for POSIX shells`. This <a href="https://stackoverflow.com/questions/18668556/comparing-numbers-in-bash">discussion</a> on stack overflow contains useful information on this topic.

**Input Format**

Two lines containing one integer each (X and Y, respectively).

**Output Format**

Exactly one of the following lines: 

- X is less than Y 
- X is greater than Y 
- X is equal to Y

**Sample Input 1**
```
5  
2  
```

**Sample Output 1**
```
X is greater than Y  
```

**Sample Input 2**
```
2
2  
```

**Sample Output 2**
```
X is equal to Y  
```

**Sample Input 3**
```
2
3  
```

**Sample Output 3**
```
X is less than Y  
```

**Reference Resources**

A relevant and interesting discussion on Stack-Exchange for those getting started with handling numbers and arithmetic operations in Bash.

These discussions on stack overflow and geeksforgeeks contains useful information on <a href="http://www.thegeekstuff.com/2010/06/bash-conditional-expression/">this topic</a>.

## Solutions

* Bash1
```bash
#!/bin/bash

read X 
read Y
if (( X > Y )); then
    echo "X is greater than Y"
elif (( X < Y )); then
    echo "X is less than Y"
else
    echo "X is equal to Y"
fi
```

* Bash2
```bash
#!/bin/bash

read X 
read Y
if [ "$X" -gt "$Y" ]; then
    echo "X is greater than Y"
elif [ "$X" -lt "$Y" ]; then
    echo "X is less than Y"
else
    echo "X is equal to Y"
fi
```

## Explanation
```bash
-eq # equal
-ne # not equal
-lt # less than
-le # less than or equal
-gt # greater than
-ge # greater than or equal
``