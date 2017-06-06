# Read in an Array

### HackerRank

## Question

Given a list of countries, each on a new line, your task is to read them into an array and then display the entire array, with a space between each of the countries' names.

**Recommended References** 

Here's a great <a href="http://www.thegeekstuff.com/2010/06/bash-array-tutorial/">tutorial</a> with useful examples related to arrays in Bash.

**Input Format**

A list of country names. The only characters present in the country names will be upper or lower case characters and hyphens.

**Output Format**

Display the entire array of country names, with a space between each of them.

**Sample Input**
```
Namibia
Nauru
Nepal
Netherlands
NewZealand
Nicaragua
Niger
Nigeria
NorthKorea
Norway
```

**Sample Output**
```
Namibia Nauru Nepal Netherlands NewZealand Nicaragua Niger Nigeria NorthKorea Norway
```

**Explanation**

The entire array has been displayed.

## Solutions

* Bash
```bash
## Given a list of countries, each on a new line, your task is to read them into an array and then display the entire array, with a space between each of the countries' names.
array=($(cat))
echo {array[@]}    ## echo {array[*]}
## or
paste -d' ' -s

## Given a list of countries, each on a new line, your task is to read them into an array. Then slice the array and display only the elements lying between positions  and , both inclusive. Indexing starts from from .
a=($(cat))
echo ${a[*]:3:5}

## You are given a list of countries, each on a new line. Your task is to read them into an array and then filter out (remove) all the names containing the letter 'a' or 'A'.
a=($(cat))
pattern=( ${a[@]/*[Aa]*/} )
echo ${pattern[*]}

## Given a list of countries, each on a new line, your task is to read them into an array. Then, concatenate the array with itself (twice) - so that you have a total of three repetitions of the original array - and then display the entire concatenated array, with a space between each of the countries' names.
array=($(cat))
array3=("${array[@]}" "${array[@]}" "${array[@]}")
echo ${array3[@]}

## Given a list of countries, each on a new line, your task is to read them into an array and then display the element indexed at 3. Note that indexing starts from 0.
array=($(cat))
echo ${array[3]}

## Given a list of countries, each on a new line, your task is to read them into an array and then display the count of elements in that array.
array=($(cat))
echo ${#array[@]}

## You are given a list of countries, each on a new line. Your task is to read them into an array and then transform them in the following way:
The first capital letter (if present) in each element of the array should be replaced with a dot ('.'). Then, display the entire array with a space between each country's names.
array=($(cat))
echo ${array[@]/[A-Z]/.}
```