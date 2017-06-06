# Grep

### HackerRank

## Question

**Objective** 

In this challenge, we practice using the grep command to find specified strings or regular expressions.

**Resources** 

Grep is a multi-purpose search tool that is used to find specified strings or regular expressions. A variety of options exist that makes it possible to use this command in several different ways and to handle many different situations. For example, one might opt for a case-insensitive search, or to display only the fragment matching the specified search pattern. The command could also be used to display only the line number of an input file where the specified string or regular expression has been found.

Before using grep, we recommend becoming familiar with regular expressions to be able to harness the command to its fullest.

More details about common examples of grep usage can be found <a href="http://tldp.org/LDP/abs/html/textproc.html">here</a>.

<a href="http://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/">15 Practical Grep Command Examples</a>

<a href="http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_04_02.html">TLDP Examples for Grep</a>

**Task** 

You are given a text file that will be piped into your command through STDIN. Use grep to display all the lines that contain the word the in them. The search should be sensitive to case. Display only those lines of the input file that contain the word 'the'.

**Input Format**

A text file will be piped into your command through STDIN.

**Output Format**

Output only those lines that contain the word 'the'. The search should be case sensitive. The relative ordering of the lines in the output should be the same as it was in the input.

**Sample Input**
```
From fairest creatures we desire increase,
That thereby beauty's rose might never die,
But as the riper should by time decease,
His tender heir might bear his memory:
But thou contracted to thine own bright eyes,
Feed'st thy light's flame with self-substantial fuel,
Making a famine where abundance lies,
Thy self thy foe, to thy sweet self too cruel:
Thou that art now the world's fresh ornament,
And only herald to the gaudy spring,
Within thine own bud buriest thy content,
And tender churl mak'st waste in niggarding:
Pity the world, or else this glutton be,
To eat the world's due, by the grave and thee.
When forty winters shall besiege thy brow,
And dig deep trenches in thy beauty's field,
Thy youth's proud livery so gazed on now,
Will be a tattered weed of small worth held:
Then being asked, where all thy beauty lies,
Where all the treasure of thy lusty days;
To say within thine own deep sunken eyes,
Were an all-eating shame, and thriftless praise.
How much more praise deserved thy beauty's use,
If thou couldst answer 'This fair child of mine
Shall sum my count, and make my old excuse'
```

**Sample Output**
```
But as the riper should by time decease,
Thou that art now the world's fresh ornament,
And only herald to the gaudy spring,
Pity the world, or else this glutton be,
To eat the world's due, by the grave and thee.
Where all the treasure of thy lusty days;
```

**Explanation**

We have retained and displayed only those lines that contain the word 'the'. A little bit of extra care might be required to avoid retaining cases where 'the' is a suffix or prefix of some other word within the sentences!

## Solutions

* Bash
```bash
#!/bin/bash

## You are given a text file that will be piped into your command through STDIN. Use grep to display all the lines that contain the word the in them. The search should be sensitive to case. Display only those lines of the input file that contain the word 'the'.
grep -w "the"

## The search should NOT be sensitive to case. 
Display only those lines of the input file that contain the word 'the'.
grep -i -w "the"

## Use grep to remove all those lines that contain the word 'that'. The search should NOT be sensitive to case.
grep -i -w -v "that"

## use grep to display all those lines which contain any of the following words in them: the that then those 
The search should not be sensitive to case. Display only those lines of an input file, which contain the required words.
#grep -i -w -e "the" -e "that" -e "then" -e "those"
grep -i -w "the\|that\|then\|those"

## Given an input file, with N credit card numbers, each in a new line, your task is to grep out and output only those credit card numbers which have two or more consecutive occurences of the same digit (which may be separated by a space, if they are in different segments). Assume that the credit card numbers will have 4 space separated segments with 4 digits each.
## If the credit card number is 1434 5678 9101 1234, there are two consecutive instances of 1 (though) as highlighted in box brackets: 1434 5678 910[1] [1]234
## Here are some credit card numbers where consecutively repeated digits have been highlighted in box brackets. The last case does not have any repeated digits: 1234 5678 910[1] [1]234 
2[9][9][9] 5178 9101 [2][2]34 
[9][9][9][9] 5628 920[1] [1]232 
8482 3678 9102 1232

grep -P '(\d) *\1+'
#grep -P '(\d) *\1'
```