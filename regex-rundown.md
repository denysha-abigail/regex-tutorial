


WHEN I read through each section of the tutorial
THEN I find a detailed explanation of what a specific component of the regex does
WHEN I reach the end of the tutorial
THEN I find a section about the author and a link to the author’s GitHub profile


# Regex Rundown

Regular Expressions, or more commonly abbreviated as Regex, are powerful, case-sensitive patterns composed of single or a combination of single and special characters for the purpose of searching through and extracting information from text through matching, validating, locating, parsing, replacing, and/or managing target strings. 

## Summary

In this Regex Rundown tutorial, we will be discussing validating a strong password by breaking down each component of the syntax below. 

```^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\$%\^&\*])(?=.{8,})```

To satisfy the password strength criteria, a password must contain:

* At least 1 lowercase alphabetical character: ```(?=.*[a-z])```
* At least 1 uppercase alphabetical character: ```(?=.*[A-Z])```
* At least 1 numeric character: ```(?=.*[0-9])```
* At least 1 special character: ```(?=.*[!@#$%^&*])```
* A minimum of 8 characters: ```(?=.{8,})```

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

### Anchors: ^

Anchors do not match any characters, but rather match a position before, after, or between characters. In single-line mode, the ```^``` anchor matches the beginning of the string.

An input of ```abc123``` would pass if tested against the expression ```/^abc/``` because the three letters are positioned at the beginning of the string, in their respective order.

In the case of the password strength validation Regex, the ```^``` is simply ensuring that a match is positioned at the start of the string. The anchor in this scenario is essentially determining that any syntax component succeeding will pass if inputted at the beginning of the string (whether it be a lowercase, uppercase, numeric, or special character).

### Quantifiers: * {}

Quantifiers specify how many instances of a character, group, or character class an input must have in order for a match to be found. 

The ```*``` quantifier (```*[a-z]```, ```*[A-Z]```, ```*[0-9]```, and ```*[!@#\$%\^&\*]```) matches a password that has 0 or more instances of any syntax component succeeding it. 

A quantifier of ```{8}``` would only match a password of 8 characters in length. A quantifier of ```{8, 16}``` would match any password between 8 and 16 characters.

In the case of the password strength validation Regex, the ```{}``` quantifier (```{8,}```) matches a password that has AT LEAST 8 characters. 

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

### Resources
* https://regexr.com/
* https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
* https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial
* https://www.thepolyglotdeveloper.com/2015/05/use-regex-to-test-password-strength-in-javascript/
* https://regexland.com/regex-anchors-a-complete-guide/
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Cheatsheet
* https://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions

## Author

Written by Denysha Guerrios-Armaiz, a software engineer specializing in full-stack web development. To explore open-source projects created by this author please visit: https://github.com/denysha-abigail
