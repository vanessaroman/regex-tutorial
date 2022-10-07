# Matching URL Regex Tutorial

Welcome to my Regex tutorial! In this tutorial you will learn how to use a Regular Expression to find/match URLs within code.

Just fyi, Regular Expressions are a series of characters that define a search pattern.

## Summary

The Regex we will learn about is the following:

    /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

This Regex will help us search for specific strings in code that match the specifications of a URL.

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
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors help Regular Expressions match a certain position before, after, or en between characters. The character ^ helps match with a string that begins with whatever character follows it. The character $ helps match strings that end with whatever character that is in front of it.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see that ^ is specifying the Regex to find any string that starts with the group (denoted by "()") (https?:\/\/). And we see that $ is telling our Regex to match any strings that end with a question mark.

### Quantifiers

Quantifiers help set a character limit for groups or full strings. They can help match a minimun and maximun amount of characters, a specific number of characters, or a minimun number of characters. See a list below of all the different quantifiers.

- "*" matches zero or more times
- "+" matches one or more times
- "?" matches zero or more times
- "{n}" matches exactly n times
- "{n,}" matches at least n times
- "{n,m}" matches n to m times 

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see that ? is trying to match a combination of characters that starts with p followed by zero or one instance of the letter s. 

We can see that ? is trying to match any grouping that matches https:// zero or one times.

We can see that + is matching one or more of the character set that matches any digit character between a and z followed by a literal period and a - 

We can see that {2,6} is matching between 2 to 6 occurrences of a string that contains any lowercase letter between a–z followed by a literal period.

We can see that in "([ \ / \w \ .-]*)" * is matching zero or more of the preceding set.

We can see that in "([ \ / \ w \ .-]* ) * \ / ?" * is matching zero or more of the preceding capturing set and ? is matching anywhere from 0 to 1 of the preceding /.

### OR Operator

OR Operators " | " match characters or expression to either left or right of the |.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see there are no OR operators in the string.

### Character Classes

A character class or character set is denoted by [] will help match whatever characters or expressions are inside the []. The order of the characters inside does not matter.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see the following character sets:

* [\ d a-z \ . -]
* [ a - z \ . ]
* [ \ / \ w \ . -]

### Flags

Flags change the search behavior of a Regex. They are denoted with single lowercase alphabetical characters. Flags are placed after the closing slash in an full regex. A list of flags used for Regex is found below:

* i - Ignore casing
* g - Global
* s - DotAll
* m - Multiline
* y - Sticky
* u - Unicode

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

we can see there are no flags in our string.

### Grouping and Capturing

Parenthesis are used for grouping characters that are part of a Regex together. When parenthesis group multiple tokens together that is referred to as capturing.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see the fallowing groups: "(h t t p s ? : \ / \ / )" , "( [ \ d a - z \ . - ] + )" group capturing , "( [ a - z \ . ] { 2 , 6 } )" group capturing, "( [ \ / \ w  \ . - ] * )" group capturing.

### Bracket Expressions

Bracket Expressions define any individual characters to match.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We see the following bracket expressions: "[ \ d a - z \ . - ]", "[ a - z \ . ]", and "[ \ / \ w \ . - ]"

### Greedy and Lazy Match

Greedy matches will try to match as much as possible. By having a regex like <.+>, and code like < e m >Hello World< / e m > we might assume the regex will only match the < e m > < / e m > tags, but in truth it will match from the first < to the last >, including the plain text in between.

Lazy matches tell the Regex to look for as little as possible. In our example above, adding a ? to our Regex like so: < . + ? >, will communicate that we want as few matches as possible and as soon as it reads the first > it will stop.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We see ? quantifier telling our Regex to look for zero to one matches of "( h t t p s ? : \ / \ / )" and "/" towards the end of the Regex.

### Boundaries

\b boundaries help searches define what can be matched to the left and right of the current position. \b is a word boundary that matches strings where one side is a word character and the other side is not.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see there are no word boundaries.


### Back-references

Back-references match the same text already matched by a capturing group.When looking at a Regex with multiple capturing groups we can tell it to re-match a capturing group by adding \n to the Regex. The n will be defined by the position of the capturing group wanted.

Looking at our Regex below, 

      /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

We can see there are no back-references, but as an example, if we wanted to re-match the second capturing group we can add \2 to the Regex.

### Look-ahead and Look-behind

Collectively called "lookaround" are added at the start and end of line and word expressions. Lookarounds look for matches but do not bring them up, they just make an assertion about whether or not there is a match. Below is a list of the different lookarounds available.

* (?=foo) - look ahead
* (?<=foo) - look behind
* (?!foo) - negative look ahead
* (?<!foo) - negative look behind

## Author

Vanessa is a full-stack software developer and artist living in Colorado. 

[Vanessa's Github](https://github.com/vanessaroman)

