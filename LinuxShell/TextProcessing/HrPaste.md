# Paste

### HackerRank

## Question

The paste command is used for merging lines of a given file. It may be used for merging data from one or more files. Some common uses of the command and its various flags and variations have been listed over <a href="http://www.theunixschool.com/2012/07/10-examples-of-paste-command-usage-in.html">here</a>.

**Task** 

Given a CSV file where each row contains the name of a city and its state separated by a comma, your task is to replace the newlines in the file with tabs as demonstrated in the sample.

**Input Format**

You are given a CSV file where each row contains the name of a city and its state separated by a comma.

**Output Format**

Replace the newlines in the input with tabs as demonstrated in the sample.

**Sample Input**
```
Albany, N.Y.
Albuquerque, N.M.
Anchorage, Alaska
Asheville, N.C.
Atlanta, Ga.
Atlantic City, N.J.
Austin, Texas
Baltimore, Md.
Baton Rouge, La.
Billings, Mont.
Birmingham, Ala.
Bismarck, N.D.
Boise, Idaho
Boston, Mass.
Bridgeport, Conn.
```

**Sample Output**
```
Albany, N.Y.    Albuquerque, N.M.   Anchorage, Alaska   Asheville, N.C.Atlanta, Ga. Atlantic City, N.J. Austin, Texas   Baltimore, Md.  Baton Rouge, La.    Billings, Mont. Birmingham, Ala.    Bismarck, N.D.  Boise, Idaho    Boston, Mass.   Bridgeport, Conn.
```

**Explanation**

The delimiter between consecutive rows of data has been transformed from the newline to a tab.

## Solutions

* Bash
```bash
#!/bin/bash

## Given a CSV file where each row contains the name of a city and its state separated by a comma, your task is to replace the newlines in the file with tabs as demonstrated in the sample.
paste -s

## Given a CSV file where each row contains the name of a city and its state separated by a comma, your task is to restructure the file in such a way, that three consecutive rows are folded into one, and separated by tab.
paste - - -

## You are given a CSV file where each row contains the name of a city and its state separated by a comma. Your task is to replace the newlines in the file with semicolons as demonstrated in the sample.
paste -d';' –s

## You are given a CSV file where each row contains the name of a city and its state separated by a comma. Your task is to restructure the file so that three consecutive rows are folded into one line and are separated by semicolons.
paste -d';' - - -
```