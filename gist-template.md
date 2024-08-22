# Validate Email Addresses with Regular Expressions in JavaScript

For web developers, validating user inputs in various types of forms is of crucial importance. Since that is the starting point of data being sent between the client and the server, you need to make sure that everything starts off on the right foot - lest you end up with robust validation on the server end, which is oftentimes a bigger hassle than doing it on the front-end. In this article, we'll take a look at how to validate email addresses in JavaScript using Regular Expressions.After this tutorial you will also be able to utilize regular expressions to find and search anything, by creating your own patterns.

## Summary

What is a Regex? It is a short name of Regular Expression. Essentially it is a search pattern used to find, replace or validate user input. This tutorial will go through each part of the expression and will describe what it does to use in matching an email address.For the record I did not come up with this regex pattern myself. I will be using this regex pattern as a teaching example. By breakdown this regex down character for character I will be able to show you the different parts and pieces of a regex.

Now lets get into it, here is the pattern we will be deconstructing:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Simply put, we can separate the following code snippet into three distinct sections. Section one focuses on the first part of an email to the @ symbol. Section two of the code focuses on identifying the domain name, and the last section specifies the extension of that domain.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Because Regex is a literal it has to be written inside of two forward slashes: / Now let's see what are the actual components of this expression.

### Anchors
^ is an anchor that indicates the beginning of a string

$ is an anchor that indicates the ending of a string

Example:
^asdf$ where ^ character indicates the start of a string, and the $ character indicates the end of a string. Matches exact string.
^asdf matches any string that starts with asdf
asdf$ matches any string that ends with asdf
We can see in this regex that the string must start and end with the characters that match the pattern:

[a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]

### Quantifiers
Notice, that {2,6} is not a pattern. It is a special component called Quantifiers, which role is to indicate a range of 2-6 characters for the character set of [a-z\.]

+ Repeats the previous item one or more times

Example:
abc{3,7} matches a string that has ab followed by 3 up to 7 c
abc+ matches a string that has ab followed by one or more c

### Grouping Constructs
There are three groupes in this Regex:

([a-z0-9_\.-]+) indicates email name of a user followed by @
([\da-z\.-]+) indicates domain name floowed by .
([a-z\.]{2,6}) indicates domain extension (for instance, it could be .com .net .org)

### Bracket Expressions
These are character sets between square brackets [] and can include any characters we want to match AND they are case sensitive. In this particular Regex there are three character sets:

[a-z0-9_\.-] includes any LOWER case letters between a and z, any numbers 0-9, underscore _ , hyphen - , and dot .
Example:
asdF9 is not a match because it contains upper case letters
asdf9 is a match because it has lower case letters and number
[\da-z\.-] includes any digit (\d is a character class that will be explained in the next section) 0-9, any LOWER case letters between a and z, hyphen - , and dot .
Example:
asdf% is not a match because it has % character which is not included in the set
asd.f6 is a match because all the characters are within the set
[a-z\.] includes any LOWER case letters between a and z, and dot .
Example:
co-M is not a match because it contains upper case and -
.org is a match because all the characters are within the set

### Character Classes
\d as mentioned earlier it is a character class that is a match to all the Arabic numbers 0-9. Writing \d is the same as writing the bracket expression [0-9].

Example:
it will only match single digit 8
88is not a match

### The OR Operator
The OR operator in regex is |, and means that we can match for a OR b conditions:

a|b accepts strings "a" or "b"
Using a bracket list [ab] would accept any one of the characters within the square bracket, i.e. a or b

### Flags
Regex flags are parameters that can be added to a pattern to modify how it works:

i flag (case-insensitivity): when used, the regex pattern becomes case insensitive, we could add i to the end of the regex to make it case insensitive, if we wanted: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i
g flag (global): when used, finds all matches within a given string, rather than stopping after the first match

### Character Escapes
Character escapes suppress the special meaning of metacharacters and representing characters, and treat them as literals:

Backslash \.: refers to a literal . within the email address. If the dot is not escaped, it denotes a wildcard character
Metacharacters: the dot ., plus sign +, caret ^, hyphen -
Escape sequences: characters that can not be directly typed or represented in a string, starting with a backslash \ and followed by a letter

## Author
Full-stack Software Engineering professional with newly acquired skills from the University of Berkley full-stack boot camp. Experienced in JavaScript, HTML, CSS, JQuery, Bootstrap, Node.js, MySQL, MongoDB, Express.js, and React.js. Able to grasp new concepts quickly and implement them immediately to solve problems effectively. Ready to take on any challenge and do whatever it takes; to effectively solve big picture problems. Great leadership abilities and can bring the best out of their team. Also equipped with an eagerness to listen, learn and follow the direction of a project manager to fit any role a team needs.

Questions about this this gist? Please contact me: [@aniraannu](https://github.com/aniraannu)

View more of my work on my  profile: [@aniraannu](https://github.com/aniraannu)
