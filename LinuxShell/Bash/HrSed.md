# Sed command

### HackerRank

## Question

**Objective** 

In this challenge, we will practice using the sed command to parse and transform text.

**Resources**

Sed is a popular tool that enables quick parsing and transformation of text.
Examples of sed in action:

Substitute the first occurrence of 'editor' with 'tool':
```
`$:~/hackerrank/bash/grep/grep1$` echo "My favorite programming editor is Emacs. Another editor I like is Vim." | sed -e s/editor/tool/
```

My favorite programming tool is Emacs. Another editor I like is Vim.

Substitute all the occurrences of 'editor' with 'tool':
```
`$:~/hackerrank/bash/grep/grep1$` echo "My favorite programming editor is Emacs. Another editor I like is Vim." | sed -e s/editor/tool/g
```

My favorite programming tool is Emacs. Another tool I like is Vim.  

Substitute the second occurrence of 'editor' with 'tool':
```
`$:~/hackerrank/bash/grep/grep1$` echo "My favorite programming editor is Emacs. Another editor I like is Vim." | sed -e s/editor/tool/2
```

My favorite programming editor is Emacs. Another tool I like is Vim.

Highlight all the occurrences of 'editor' by wrapping them up in brace brackets:
```
`$:~/hackerrank/bash/grep/grep1$` echo "My favorite programming editor is Emacs. Another editor I like is Vim." | sed -e s/editor/{\&}/g
```

My favorite programming {editor} is Emacs. Another {editor} I like is Vim.
The following links are useful to learn about sed: 

<a href="http://www.grymoire.com/Unix/Sed.html">Sed - An Introduction and a tutorial</a> 

<a href="http://tldp.org/LDP/abs/html/x23170.html">The TLDP Guide</a>

<a href="http://www.folkstalk.com/2012/01/sed-command-in-unix-examples.html">Some Practical Examples</a>

**Task **

For each line in a given input file, transform the first occurrence of the word 'the' with 'this'. The search and transformation should be strictly case sensitive.

**Input Format**

A text file will be piped into your command through STDIN.

**Output Format**

Transform the text as specified by the task.

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
From fairest creatures we desire increase,
That thereby beauty's rose might never die,
But as this riper should by time decease,
His tender heir might bear his memory:
But thou contracted to thine own bright eyes,
Feed'st thy light's flame with self-substantial fuel,
Making a famine where abundance lies,
Thy self thy foe, to thy sweet self too cruel:
Thou that art now this world's fresh ornament,
And only herald to this gaudy spring,
Within thine own bud buriest thy content,
And tender churl mak'st waste in niggarding:
Pity this world, or else this glutton be,
To eat this world's due, by the grave and thee.
When forty winters shall besiege thy brow,
And dig deep trenches in thy beauty's field,
Thy youth's proud livery so gazed on now,
Will be a tattered weed of small worth held:
Then being asked, where all thy beauty lies,
Where all this treasure of thy lusty days;
To say within thine own deep sunken eyes,
Were an all-eating shame, and thriftless praise.
How much more praise deserved thy beauty's use,
If thou couldst answer 'This fair child of mine
Shall sum my count, and make my old excuse'
```

**Explanation**

The line:
```
"But as the riper should by time decease,"
```
has been transformed to:
```
"But as this riper should by time decease,"  
```
The line:
```
"To eat the world's due, by the grave and thee."    
```
has been transformed to:
```
"To eat this world's due, by the grave and thee." 
```

## Solutions

* Bash
```bash
## For each line in a given input file, transform the first occurrence of the word 'the' with 'this'. The search and transformation should be strictly case sensitive.

Sed ‘s/\bthe\b/this/’

## For each line in a given input file, transform all the occurrences of the word 'thy' with 'your'. The search should be case insensitive, i.e. 'thy', 'Thy', 'tHy' etc. should be transformed to 'your'.
sed ‘s/\bthy\b/your/Ig’

## Given an input file, in each line, highlight all the occurrences of 'thy' by wrapping them up in brace brackets. The search should be case-insensitive.
sed ‘s/thy/{&}/Ig’

## Given n lines of credit card numbers, mask the first 12 digits of each credit card number with an asterisk (i.e., *) and print the masked card number on a new line. Each credit card number consists of four space-separated groups of four digits. For example, the credit card number 1234 5678 9101 1234 would be masked and printed as **** **** **** 1234.
sed 's/[0-9]\+ /**** /g'
#sed 's/[0-9]\{4\} /**** /g'
#sed -r 's/[0-9]{4} /**** /g'

## Given an input file, with N credit card numbers, each in a new line, your task is to reverse the ordering of segments in each credit card number. Assume that the credit card numbers will have 4 space separated segments with 4 digits each.
If the original credit card number is 1434 5678 9101 1234, transform it to 1234 9101 5678 1434.
#sed -r 's/(.... )(.... )(.... )(....)/\4 \3\2\1/'
#sed -r 's/([0-9]{4} )([0-9]{4} )([0-9]{4} )([0-9]{4})/\4 \3\2\1/'
sed -r 's/(.+ )(.+ )(.+ )(....)/\4 \3\2\1/'
```