A regular expression is a sequence of characters that define a search pattern, mainly for use in pattern matching with strings. Ruby regular expressions i.e. Ruby regex for short, helps us to find particular patterns inside a string. Two uses of ruby regex are Validation and Parsing. Ruby regex can be used to validate an email address and an IP address too. Ruby regex expressions are declared between two forward slashes.

Syntax:

# finding the word 'hi'
"Hi there, i am using gfg" =~ /hi/
This will return the index of first occurrence of the word ‘hi’ if present, or else will return ‘ nil ‘.

Checking if a string has a regex or not
We can also check if a string has a regex or not by using the match method. Below is the example to understand.
Example :


# Ruby program of regular expression
  
# Checking if the word is present in the string
if "hi there".match(/hi/)
    puts "match"
end
Output:

match
Checking if a string has some set of characters or not
We can use a character class which lets us define a range of characters for the match. For example, if we want to search for vowel, we can use [aeiou] for match.
Example :

# Ruby program of regular expression
  
# declaring a function which checks for vowel in a string
def contains_vowel(str)
  str =~ /[aeiou]/
end
  
# Driver code
  
# meek has vowel at index 1, so function returns 1
puts( contains_vowel("meek") )
  
# bcd has no vowel, so return nil and nothing is printed
puts( contains_vowel("bcd") )
Output:

Different regular expressions
There are different short expressions for specifying character ranges :

\w is equivalent to [0-9a-zA-Z_]
\d is the same as [0-9]
\s matches white space
\W anything that’s not in [0-9a-zA-Z_]
\D anything that’s not a number
\S anything that’s not a space
The dot character . matches all but does not match new line. If you want to search . character, then you have to escape it.
Example :

# Ruby program of regular expression
   
a="2m3"
b="2.5"
# . literal matches for all character
if(a.match(/\d.\d/))
    puts("match found")
else
    puts("not found")
end
# after escaping it, it matches with only '.' literal
if(a.match(/\d\.\d/))
    puts("match found")
else
    puts("not found")
end
   
if(b.match(/\d.\d/))
    puts("match found")
else
    puts("not found")
end   
Output:

match found
not found
match found
Modifiers for regex
For matching multiple characters we can use modifiers:

+ is for 1 or more characters
* is for 0 or more characters
? is for 0 or 1 character
{x, y} if for number of characters between x and y
i is for ignores case when matching text.
x is for ignores whitespace and allows comments in regular expressions.
m is for matches multiple lines, recognizing newlines as normal characters.
u,e,s,n are for interprets the regexp as Unicode (UTF-8), EUC, SJIS, or ASCII. the regular expression is assumed to use the source encoding, If none of these modifiers is specified.


