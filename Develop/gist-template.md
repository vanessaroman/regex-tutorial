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

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
