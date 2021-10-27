RegEx Tutorial

RegEx or Regular Expressions is an extremely useful and efficient method of searching and extracting certain patterns out of any text.
This can be used as a tool to 'flag' certain words, numbers or expressions or to code for email address recognition, url and more. 
Regex is widely used, so we better start learning a few things about it. 

## Summary

The best way to demonstrate how Regex is used is to break down a common expression that you may see used often. We will be talking about 
Matching the Email Address and this expression  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. This Regex matches characters to validate 
email address.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)

## Regex Components

### Anchors
Anchors are the 'pieces' of the puzzle that hold expression/s boundaried per say, they tell it where the charecter selection starts and 
where it ends. In this expression our Anchors are CARROT '^' for beginning and a '$' for the end.

### Quantifiers
There are couple of quantifiers used in this expression. First one is the declaration of the length of the input after @ symbol.
We use {2,6} quantifier to 'say' that the lenght of input for the domain extention (stuff after @) has to be MIN of 2 characters and MAX 6. We are using another greedy 
operator '+' to expand the match throughout the whole text. Hence it being GREEDY.

### OR Operator
a(b|c)     matches a string that has 'a' followed by 'b' or 'c', and captures b or c.
a[bc]      matches a string that has 'a', but without capturing b or c
In this expresion we did not have OR operators

### Character Classes
There are a few character classes. 
\d - matches a DIGIT
\w - matches a WORD character, alphanumeric plus underscore
\s - matches WHITE SPACE 
.  - matches ANY character.
The \d and . are used in this example in grouped manner to capture all digits from 0-9. See the next section for example.

### Grouping and Capturing
In our current expression we have 3 different groupings that CAPTURE the matching we want performed. 
Username of the e-mail account [a-z0-9_\.-] Here you can see the '.' (matching ANY character) and a-z0-9 prior to that covering all digits
and numbers, so alphanumerical match with underscore
domain name or e-mail service being used [\da-z\.-] This entire expression is looking for the domain name. For example,
www.google or www.W3School would all be found as this expression is looking for any digit, any letter a-z, and any '.' or '-'.
domain extention (i.e .com or .net) [a-z\.]{2,6} This chunk takes care of the last aphabetic portion like .com, .net, or .org, etc. 
The exression states: ALL aphabetic characters only with 'a-z\.' and has to be MIN 2 and MAX 6 characters.

## Flags
Regex usually is limited by the '/'. We see this at the beginning and end of the expression. The flags appear BEFORE the Anchors.
In Regular Expressions one can set search criteria outside the flags to help mark the expression in 3 ways;
global (g), multi-line (m), or insensitive (i).

### Bracket Expressions
Brackets are borders within borders. If you want to make a specific request within the section of the full expression, you should use brackets.
This will ensure the selection criteria applies only to that particular section. Here are our bracket expressions explaned below. They
correspond with our Grouping

#1: [a-z0-9_\.-] - includes case sensitive characters from a-z, numbers from 0-9 an underscore, periods and hyphens.
#2: [\da-z\.-] - includes all digits, case sensitive characters from a-z, periods and hyphens.
#3: [a-z\.] - includes case sensitive characters from a-z and periods.

### Greedy and Lazy Match
Greedy qualifiers '+' and '{}' are very useful to tell the selection criteria to allow the match to go as long as it needs to the end
of expression. We used them in this expression for email address.
The Lazy qualifiers target shortest match and look like the following expression; 

### Boundaries
One can create word boundaries for particular word by using \b character class and surrounding selected word with it
Ex:'\bword\b' - this expression will select 'word' out of the text.  
We did not have any boundaries in the email expression.

## Author
This tutorial was created by Nellia Fleurova-Charlton and i am excited about Regex
GitHub link (https://github.com/NelliaFC)