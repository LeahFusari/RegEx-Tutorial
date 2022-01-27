# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
    Anchors are tokens that don't match any specific characters, but that declare something about the string or the matching process.

#### Examples:
* Caret ^: Matches at the start of the string 
* Dollar $: Matches at the end of the string 

### Quantifiers

A quantifier is used to determine how many times a specific character or group of characters needs to be present in order to have a match. For instance, if we used the following code in regex, xyz+ then this will match any string xy followed by at least one z.

There are many different types of quantifiers and some hold the attributes of being greedy or lazy as shown in the chart below.

| Greedy        | Lazy          |         Description       |
|:-------------:|:-------------:|:-------------------------:|
| *             | *?            | Match zero or more times. |
| +             | +?            | Match one or more times.  |
| ?             | ??            | Match zero or one time.   |
| { n }         | { n }?        | Match exactly n times.    |
| { n ,}        | { n ,}?       | Match at least n times.   |
| { n , m }     | { n , m }?    | Match from n to m times.  |

The difference between a greedy and a lazy quantifier is that greedy causes the regular expression engine to match as many occurrences of particular patterns as possible.  Lazy, on the other hand, causes the regular expression engine to match as few occurrences as possible.

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
