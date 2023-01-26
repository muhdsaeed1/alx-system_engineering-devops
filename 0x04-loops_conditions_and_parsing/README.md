Introduction

	The for loop is an essential programming functionality that goes through a list of elements. For each of those elements, the for loop performs a set of commands. The command helps repeat processes until a terminating condition.

Whether you're going through an array of numbers or renaming files, for loops in Bash scripts provide a convenient way to list items automatically.


	Bash Script for Loop
Use the for loop to iterate through a list of items to perform the instructed commands.

The basic syntax for the for loop in Bash scripts is:


for <element> in <list>
do
	<commands>
done



	Bash For Loop Examples
Below are various examples of the for loop in Bash scripts. Create a script, add the code, and run the Bash scripts from the terminal to see the results.


	Individual Items
Iterate through a series of given elements and print each with the following syntax:




#!/bin/bash
# For loop with individual numbers
for i in 0 1 2 3 4 5
do
   echo "Element $i"
done



#!/bin/bash
# For loop with individual strings
for i in "zero" "one" "two" "three" "four" "five"
do
   echo "Element $i"
done



	Range
Instead of writing a list of individual elements, use the range syntax and indicate the first and last element:

#!/bin/bash
# For loop with number range
for i in {0..5}
do
        echo "Element $i"
done


	Reference


https://youtu.be/T7hVOiTsSUU




