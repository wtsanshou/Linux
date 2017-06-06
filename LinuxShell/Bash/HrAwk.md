# Awk

### HackerRank

## Question

An Introduction to 'awk'

There are a lot of quick tricks which may be accomplished with the 'awk' interpreter. Among other things, awk may be used for a lot of text-munging and data-processing tasks which require some quick scripting work.

**Examples with awk**

<a href="http://www.thegeekstuff.com/2010/01/awk-introduction-tutorial-7-awk-print-examples/">Print Examples</a> 

<a href="http://www.thegeekstuff.com/2010/02/awk-conditional-statements/">Conditionals with Awk</a>

**Task** 

You are provided a file with four space-separated columns containing the scores of students in three subjects. The first column, contains a single character (A-Z) - the identifier of the student. The next three columns have three numbers (each between 0 and 100, both inclusive) which are the scores of the students in English, Mathematics and Science respectively.

Your task is to identify the performance grade for each student. If the average of the three scores is 80 or more, the grade is 'A'. If the average is 60 or above, but less than 80, the grade is 'B'. If the average is 50 or above, but less than 60, the grade is 'C'. Otherwise the grade is 'FAIL'.

**Input Format**

There will be no more than 10 rows of data. 

**Each line will be in the format: 

`[Identifier][Score in English][Score in Math][Score in Science]`

**Output Format**

For each row of data, append a space, a colon, followed by another space, and the grade. Observe the format showed in the sample output.

**Sample Input**
```
A 25 27 50
B 35 37 75
C 75 78 80
D 99 88 76
```

**Sample Output**
```
A 25 27 50 : FAIL
B 35 37 75 : FAIL
C 75 78 80 : B
D 99 88 76 : A
```

**Explanation**

* A scored an average less than 50 => FAIL Same for B C scored an average between 60 and 80 => B 

* D scored an average between 80 and 90 => A

##Solutions

* Bash
```bash
##
awk '{
    total=($2+$3+$4)/3
    if (total >= 80)
        print $1,$2,$3,$4,": A"
    else if (total >= 60 && total <80)
        print $1,$2,$3,$4,": B"
    else if (total >= 50 && total <60)
        print $1,$2,$3,$4,": C"
    else
        print $1,$2,$3,$4,": FAIL"
}'

## Concatenate every 2 lines of input with a semi-colon.
awk 'ORS=NR%2? ";":"\n"'
or
paste -d ';' - -

## Concatenate every 2 lines of input with a semi-colon.
awk 'ORS=NR%2? ";":"\n"'
or
paste -d ';' - -

## identify those lines that do not contain all three scores for students.
awk '$2=="" || $3=="" || $4=="" { print "Not all scores are available for", $1}'
#awk '$4=="" { print "Not all scores are available for", $1}'
#awk '!$4 { print "Not all scores are available for", $1}'
#awk 'NF<4 { print "Not all scores are available for", $1}'

## A student is considered to have passed if (s)he has a score 50 or more in each of the three subjects.
awk '{
    if ($2 >=50 && $3 >= 50 && $4 >= 50)
        print $1,": Pass"
    else
        print $1,": Fail"
}'
```