# Understanding Regular Expression: A Comprehensive Guide to Regex

Welcome to my first Gist: A beginner friendly tutorial on the infamous Regex! 

Regular expressions, commonly known as regex, are powerful and versatile tools used for pattern matching and text manipulation. Wtih this, you can validate text input, search/replace text within a file, batch rename files, test for pattern strings, validate email addresses, and much more. 

This tutorial is deisgned to introduce you to the fundamentals of regular expressions, covering essential concepts and syntax. By the end of this guide, you'll have a solid understanding of how to use regex in your programming projects, enabling you to handle complex text processing tasks with ease.

## Summary

The following in an example of a regex expression:

`^\d{3}-\d{2}-\d{4}$`


The is the regex pattern used to validate a U.S Social Secutity number!
Throughout this tutorial I will break each part down.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components



### <ins> Anchors </ins>

Anchors in regular expressions are used to specifify the position of the pattern in relation to a line of text. They help in defining the boundaries of the pattern you are looking for.
Common Anchors include the Caret (`^`) and the Dollar Sign (`$`). 
The Caret matches the position at the start of a string.

Lets take a look at our regex expression:
`^\d{3}-\d{2}-\d{4}$`


The `^` tells regex we are at the beginning of the string, and the `$` tells regex we are at the end.

<br></br>

### <ins> Quantifiers </ins>

Quantifiers are essential for speficying the number of occurences and can make regex patters much more flexible and powerful.
They specify how many times a particular character, group, or character class must occur.
It allows you to repeat characters,  and metacharacters.

There are two general types of quantifiers, Greedy and Lazy.
Here are some examples of the two:

<ins>Greedy Quantifiers </ins> : These quantifiers try to match as much as possible.

- `*` : Matches zero or more occurences of the preceeding element. Can match anything.


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a*` matches `""`, `a`, `aa`, `aaa`, etc.


- `+` : Matches the previous element one or more times. There are no limits on how many times it can match, but must match at least one time or will fail the match.


&nbsp;&nbsp;&nbsp;&nbsp;  Example : `a+` matches `a`, `aa`, `aaa`, but not `""`.


- `?` : Matches the previous element zero or one time. Only allows one instance of the match to be found.


&nbsp;&nbsp;&nbsp;&nbsp; Example : `a?` matches `""` and `a`.


- `{n}` : Used to specifiy the exact number of matches. Matches exactly 'n' occurences of the preceeding element.


&nbsp;&nbsp;&nbsp;&nbsp;  Example: `a{3}` matches `aaa` but not `aa` or `a`. 


- `{n,}` : Used to specifiy approximate number of matches. Matches the previous element at least 'n' times.


&nbsp;&nbsp;&nbsp;&nbsp;  Example: `a{3,}` matches `aaa`, `aaaa`, `aaaaa`, and so on. 


<ins>Lazy Quantifiers</ins> : These quantifiers try to match as little as possible.

- `*?` : Matches zero or more occurences of the preceeding element, but only as few as possible.


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a*?` matches `""` in the smallest way.


- `+?` : Matches one or more occurences of the preceeding element, but as few as possible.


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a+?` matches `a` in the smallest way possible.


<br></br>

Lets take a look at our expression and see what types of quantifiers we have:


&nbsp;&nbsp;&nbsp;&nbsp; `^\d{3}-\d{2}-\d{4}$`

<br></br>
In our regex expression, the quantifiers are `{3}`, `{2}`, and `{4}`.

Lets break it up even further.


`\d{3}`


&nbsp;&nbsp;&nbsp;&nbsp;   `\d` : Matches any digit equivalent to [0-9]. (The `\d` indicates any digit, but we will explore that further in a bit.)

&nbsp;&nbsp;&nbsp;&nbsp;  `{3}` : Specifies that the preceding element (a digit) must occur exactly 3 times. This is how a quantifier works!


So this portion of the expression is saying "match exactly 3 digits in a row".

- `"123"` matches `"123"`.
- `"4567"` matches `"456"`, the fourth digit is not included in the match.
- `"89"` matches none.
- `"abc123def"` matches the substring `"123"`, even though it's surrounded by non-digit characters.



<br></br>


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
