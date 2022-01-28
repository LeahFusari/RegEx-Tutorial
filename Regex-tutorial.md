# Explaining the RegEx Basics

The purpose of this gist is to explain the different components of a Regular Expresson (Regex) and their basic uses.  There are, of course, exceptions, special cases and more elaborate uses and syntax but for the porposes of this assignment, a high-level overview is what will be discussed.  

Regex is typically used for identifying/extracting information, specifically characters or character groups located in specific code.  It is also  used for validation purposes.  For example, ensureing a user supplies an email address and not a random string.

## Summary

# Matching an email

The following Regex will be used in (most) examples of this gist along with some additional info about the given Regex components.  It is an example of how we can validate an email format.

`/^([a-z0-9_\.-]+)@([\d0-9\.-]+)\.([a-z\.]{2,6})$/`


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
<br>

### Anchors

 In the email match example above the anchors are the `^` and the `$`.  What this means is that it is looking for something that starts with `^([a-z0-9_\.-]+)` and ends with `.([a-z\.]{2,6})$.`  What the actual parameters we are looking for in these expressions will be explained further in this gist.
 <br><br>
 
### Quantifiers

A quantifier is used to determine how many times a specific character or group of characters needs to be present in order to have a match. 

There are many different types of quantifiers and some hold the attributes of being greedy or lazy as shown in the chart below.

<center>

| Greedy        | Lazy          |         Description       |
|:-------------:|:-------------:|:-------------------------:|
| *             | *?            | Match zero or more times. |
| +             | +?            | Match one or more times.  |
| ?             | ??            | Match zero or one time.   |
| { n }         | { n }?        | Match exactly n times.    |
| { n ,}        | { n ,}?       | Match at least n times.   |
| { n , m }     | { n , m }?    | Match from n to m times.  |

</center>

The difference between a greedy and a lazy quantifier is that greedy causes the regular expression engine to match as many occurrences of particular patterns as possible.  Lazy, on the other hand, causes the regular expression engine to match as few occurrences as possible.

In the email example above, `([a-z0-9_\.-]+)` will match any string that contains a-z, 0-9, _, ., or -. The quantifier + means that it has to contain at least one of these characters in order to have a match.
<br><br>

### OR Operator

Similar to the javascript OR operator `||`, the regex OR operator `|` can be used to match characters or an expression on either the left or right side of the operator.  The email example does not contain an OR operator but please refer to the example below.

#### Example:

 `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This will match where it starts with the #, followed by either a six character long string that contains a combination of a-f letters and 0-9 numbers **OR** a 3 character long string that contains a combination of a-f letters and 0-9 numbers.
<br><br>

### Character Classes

In the email example at the top of the gist, \d will match a single digit character, 0-9, after the @ sign in the email address. 

Additional character classes are:

>* **Positive character groups:** A character in the input string that must match one of a specified set of characters.
>* **Negative character groups:** A character in the input string must not match one of a specified set of characters. 
>* **Any character:** The . (dot or period) character in a regular expression is a wildcard character that matches any character except \n.
>* **General Unicode category or named block:** A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.
>* **A negative general Unicode category or named block:** A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.
>* **A word character:** A character in the input string that can belong to any of the Unicode categories that are appropriate for characters in words
>* **A non-word character:** A character in the input string can belong to any Unicode category that is not a word character.
>* **A white-space character:** A character in the input string can be any Unicode separator character, as well as any one of a number of control characters
>* **A non-white-space character:** A character in the input string can be any character that is not a white-space character
>* **A decimal digit:** A character in the input string can be any of a number of characters classified as Unicode decimal digits.
>* **A non-decimal digit:** A character in the input string can be anything other than a Unicode decimal digit.

>source: https://docs.microsoft.com/
<br><br>

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

