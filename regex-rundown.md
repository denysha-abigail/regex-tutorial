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
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy Match](#greedy-match)
- [Positive Look-Ahead](#positive-look-ahead)
- [Resources](#resources)
- [Author](#author)

## Regex Components

### Anchors

Anchors do not match any characters, but rather match a position before, after, or between characters. In single-line mode, the ```^``` anchor matches the beginning of the string.

An input of ```abc123``` would pass if tested against the expression ```/^abc/``` because the three letters are positioned at the beginning of the string, in their respective order.

In the case of the password strength validation Regex, the ```^``` is simply ensuring that a match is positioned at the start of the string. The anchor in this scenario is essentially determining that any syntax component succeeding will pass if inputted at the beginning of the string (whether it be a lowercase, uppercase, numeric, or special character).

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class an input must have in order for a match to be found. 

The ```*``` quantifier (```*[a-z]```, ```*[A-Z]```, ```*[0-9]```, and ```*[!@#\$%\^&\*]```) matches a password that has 0 or more instances of any syntax component succeeding it. 

A quantifier of ```{8}``` would only match a password of exactly 8 characters in length. A quantifier of ```{8, 16}``` would match any password between 8 and 16 characters.

In the case of the password strength validation Regex, the ```{}``` quantifier ```{8,}``` matches a password that has AT LEAST 8 characters. 

### Character Classes

Character classes, or character sets, match any character in the set. 

In the case of the password strength validation Regex, the ```.``` will match any character.

### Grouping and Capturing

Capturing groups allow mulitple characters to be treated as single separate units by encapsulating them inside a set of parantheses. 

In the case of the password strength validation Regex: ```^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\$%\^&\*])(?=.{8,})``` notice how the lowercase, uppercase, numeric, special character, and password length validations are all grouped inside their own set of parentheses. This allows more convenient access to the content of specific groups, if necessary.

### Bracket Expressions

Bracket expressions are composed of characters and/or character classes encompassed within brackets.

In the case of the password strength validation Regex, bracket expressions include ```[a-z]``` and ```[A-Z]``` which match any character from lowercase ```a``` through ```z``` and uppercase ```A``` through ```Z```, respectively. The ```[!@#\$%\^&\*]``` will match any of the special characters within that set as well.

### Greedy Match

All quantifiers (```?```, ```*```, ```+```, ```{m,n}```) are recognized as greedy operators due to their default tendency of grasping as many characters as possible for a match.

In the case of the password strength validation Regex, the ```.*``` before every bracket expression will try to match any amount of anything.

### Positive Look-ahead

Positive look-aheads are used after a ```^``` anchor in order to validate a condition by triggering each look-ahead one by one at the beginning of the string. 

In the case of the password strength validation Regex, the ```(?=.*[A-Z])``` for example, matches that the password must contain at least one uppercase ASCII letter after any zero or more characters. 

## Resources
* https://regexr.com/
* https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
* https://www.thepolyglotdeveloper.com/2015/05/use-regex-to-test-password-strength-in-javascript/
* https://regexland.com/regex-anchors-a-complete-guide/
* https://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions
* https://www3.ntu.edu.sg/home/ehchua/programming/howto/Regexe.html
* https://vhudyma-blog.eu/2020-05-12-capturing-groups-in-regular-expressions/
* https://mariusschulz.com/blog/why-using-the-greedy-in-regular-expressions-is-almost-never-what-you-actually-want
* https://unix.stackexchange.com/questions/672794/regex-what-is-the-use-of-positive-lookahead-at-the-beginning-of-regex

## Author

Written by Denysha Guerrios-Armaiz, a software engineer specializing in full-stack web development. 

To explore projects created by this author please visit: https://github.com/denysha-abigail
