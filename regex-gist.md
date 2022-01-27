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

In the email example above, `([a-z0-9_\.-]+)` will match any string that contains a-z, 0-9, _, ., or -. The quantifier + means that it has to contain at least one of this in order to have a match.
<br><br>

### OR Operator
Similar to the javascript OR operator ||, the regex OR operator | can be used to match characters or an expression on either the left or right side of the operator.  The email example does not contain an OR operator but please refer to the example below.

#### Example:
* `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This will match where it starts with the #, followed by either a six character long string that contains a combination of a-f letters and 0-9 numbers **OR** a 3 character long string that contains a combination of a-f letters and 0-9 numbers.
<br><br>

### Character Classes

In the email example at the top of the gist, \d will match a single digit character, 0-9, after the @ sign in the email address. 

Additional character classes are:

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
<br><br>

### Flags

There is no flag in the given email example.

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
<br><br>

### Grouping and Capturing

Captureing groups are a way to treat multiple characters as a single unit.  This is accomplished by using parentheses and are numbered by counting their opening parentheses from left to right.

#### Example: 
`((A)(B(C)))`

The above expression has four groups associated with it.

1. `((A)(B(C)))`
2. `(A)`
3. `(B(C))`
4. `(C)`

In the email example, the groups are:

1. `([a-z0-9_\.-]+)`
2. `([\da-z\.-]+)` 
3. `([a-z\.]{2,6})` 
<br><br>

### Bracket Expressions

Brakets indicate a set of characters to match.  Any individual character between the brackets will match.  You can use a hyphen to define a set.

In this snippit from the email example, `[a-z0-9_\.-]` it can contain letters a-z, numbers 0-9, an underscore, hyphen, or period.
<br><br>

### Greedy and Lazy Match

In the given code for matching an email, there isn't a greedy or lazy match included.

'Greedy' means match longest possible string. 'Lazy' means match shortest possible string.  (See also [Quantifiers](#quantifiers).)
<br><br>

### Boundaries

Boundaries are not used in the given matching an email code.

Boundary matches can help find where in the string a match is taking place. Thus makeing your pattern matches more precise. Example: Searching for a particular word, but only if it appears at the beginning or end of a line.  (See also [Anchors](#anchors))

* `^` – Placed before the word to match
* `$` – Placed at the end of a word to match
* `\b` – Checks whether a pattern begin or end on a word boundary
* `\B` – Matches the expression on a non-word boundary
* `\A` – The beginning of the input
* `\G` – Requires to match to occur only at the end of the previous match
* `\Z` – The end of the input but for the final terminator, if any
* `\z` —The end of the input
<br><br>

### Back-references

Back-references are not included in the given code.

Back-references are used to match the same text previously matched by a capturing group.
<br><br>

### Look-ahead and Look-behind

Collectively known as Lookarounds, they are an assertion which are non-capturing and must match (or not match) what comes before (or after) the current location in the input string.

Lookarounds are not used in the given example.
<br><br>

## Author

This gist was created by Leah Fusari as part of an assignment for UCONN Coding Bootcamp. 

[GitHub](https://github.com/LeahFusari)

[LinkedIn](https://www.linkedin.com/in/leah-fusari-79b35821b/)
