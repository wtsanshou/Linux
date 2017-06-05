# Tail of a Text File

**Objective** 
In this challenge, we practice using the tail command to display the last n characters of a text file.

**Resources**

By default, it displays the last 10 lines when used in the following form:

`tail [filename]`

We can also use it to display the last n lines/words/characters/etc by using different flags. For example:
```
tail -n 11 [filename]  # Last 11 lines  
tail -c 20 [filename]  # Last 20 characters  
```

We can also specify a certain number of lines to be displayed and list multiple filenames as well. It may also be used to display a specified number of bytes from an input file. Click here for more details about using the tail command.

**Task**

Display the last 20 characters of an input file.

**Input Format**

A text file.

**Output Format**

Output the last 20 characters of the text file.

**Sample Input**
```
New York is a state in the Northeastern and Mid-Atlantic regions of the United States. 
New York is the 27th-most extensive, the third-most populous populated of the 50 United States. 
New York is bordered by New Jersey and Pennsylvania to the south.
About one third of all the battles of the Revolutionary War took place in New York.
Henry Hudson's 1609 voyage marked the beginning of European involvement with the area.
```

**Sample Output**
```
ent with the area.
```

## Solutions

* Bash1
```bash
## Display the last 20 lines of an input file.
tail -20
tail -n20

## Display the last 20 characters of an input file.
tail -c 20
tail -c20
```