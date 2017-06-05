# Looping and Skipping

### HackerRank

## Qeustion

for loops in Bash can be used in several ways: 

- iterating between two integers,  and  
- iterating between two integers,  and , and incrementing by  each time 
- iterating through the elements of an array, etc.

Your task is to use for loops to display only odd natural numbers from  to .

**Input** 

There is no input.

**Output**
```
1
3
5
.
.
.
.
.
99  
```

**Recommended Resources**

A quick but useful tutorial for bash newcomers is <a href="http://www.panix.com/~elflord/unix/bash-tute.html">here</a>. 

Handling input is documented and explained quite well on <a href="http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_08_02.html">this page</a>. 

Different ways in which for loops may be used are explained with examples <a href="http://www.cyberciti.biz/faq/bash-for-loop/">here</a>. 

## Solutions

#!/bin/bash
```bash
for i in {1..99..2}
do
    echo $i
done
```
