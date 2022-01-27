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

### OR Operator
Similar to the javascript OR operator ||, the regex OR operator | can be used to match characters or an expression on either the left or right side of the operator.

#### Examples:
* `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This will match where it starts with the #, followed by either a six character long string that contains a combination of a-f letters and 0-9 numbers **OR** a 3 character long string that contains a combination of a-f letters and 0-9 numbers.

### Character Classes

* **Positive character groups:** A character in the input string that must match one of a specified set of characters.
* **Negative character groups:** A character in the input string must not match one of a specified set of characters. 
* **Any character:** The . (dot or period) character in a regular expression is a wildcard character that matches any character except \n.
* **General Unicode category or named block:** A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.
* **A negative general Unicode category or named block:** A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.
* **A word character:** A character in the input string that can belong to any of the Unicode categories that are appropriate for characters in words
* **A non-word character:** A character in the input string can belong to any Unicode category that is not a word character.
* **A white-space character:** A character in the input string can be any Unicode separator character, as well as any one of a number of control characters
* **A non-white-space character:** A character in the input string can be any character that is not a white-space character
* **A decimal digit:** A character in the input string can be any of a number of characters classified as Unicode decimal digits.
* **A non-decimal digit:** A character in the input string can be anything other than a Unicode decimal digit.

### Flags

Flags are tokens that modify the behavior of searching.

<center>

| Flag          | Name          |         Modification       |
|:-------------:|:-------------:|:---------------------------------------------------------:|
| i             | Ignore Casing | Makes the expression search case-insensitively. |
| g             | Global        | Makes the expression search for all occurences. |
| s             | Dot All       | Makes the wild character . match newlines as well.  |
| m             | Multiline     | Makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.    |
| y             | Sticky        | Makes the expression start its searching from the index indicated in its lastIndex property.   |
| u             | Unicode       | Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.  |

</center>

### Grouping and Capturing

Captureing groups are a way to treat multiple characters as a single unit.  This is accomplished by using parentheses and are numbered by counting their opening parentheses from left to right.

#### Example: 
`((A)(B(C)))`

The above expression has four groups associated with it.

1. ((A)(B(C)))
2. (A)
3. (B(C))
4. (C)

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
