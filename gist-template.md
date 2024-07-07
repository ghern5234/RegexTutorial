# Understanding Regex: A Comprehensive Guide to Regular Expressions

A beginner-friendly tutorial on the notorious regex.

<br></br>
<ins>What is regex?

Regular expressions, commonly known as regex, are powerful and versatile tools used for pattern matching and text manipulation. With this, you can validate text input, search/replace text within a file, batch rename files, test for pattern strings, validate email addresses, and much more. 

This tutorial is deisgned to introduce you to the fundamentals of regular expressions, covering essential concepts and syntax. By the end of this guide, you'll have a solid understanding of how to use regex in your programming projects, enabling you to handle complex text processing tasks with ease.

## Summary

The following in an example of a regex expression:

`^\d{3}-\d{2}-\d{4}$`


The is the regex pattern used to validate a U.S Social Secutity number!
Throughout this tutorial I will break each part down and explain how regex reads these characters.



## Table of Contents


- [Anchors](#anchors)
- [Metacharacters](#escape-characters)
- [Character Classes](#character-classes)
- [Quantifiers](#quantifiers)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components



### <ins>Anchors</ins>

Anchors in regular expressions are used to specifify the position of the pattern in relation to a line of text. They help in defining the boundaries of the pattern you are looking for.
Common Anchors include the Caret (`^`) and the Dollar Sign (`$`). 
The Caret matches the position at the start of a string.

Lets take a look at our regex expression:
`^\d{3}-\d{2}-\d{4}$`


The `^` tells regex we are at the beginning of the string, and the `$` tells regex we are at the end.

<br></br>

### <ins> Metacharacters </ins>
In regular expressions, there are special characters called metacharacters that are used to define complex patterns and control the behavior of the regex engine.

Common Special Characters:
- `.` (Dot)

- `*` (Asterik)
- `+` (Plus)
- `?` (Question Mark)
- `\` (Pipe)
- `^` (Caret)
- `$` (Dollar Sign)

<br>

These are a few examples of special characters. We have already discussed anchors (`^` & `$`) but will go further into detail regarding the other metacharacters that are in our example expression (`^\d{3}-\d{2}-\d{4}$`).

The backslash `\` is as an escape character, which is used to cancel out anything that comes after it. It serves two primary purposes:

1. Escaping Special Characters: It allows you to include characters that are normally treated as special (metacharacters) in a regex pattern. If you want to match metacharacters literally in your text, you will need to escape them using a backslash.
2. Introducing Special Characters: It is also used to introduce special character sequences, which are shorthand notations for commonly used character classes.

In our example expression, we use the second purpose noted above with the special character :`\d`. 

While `d` on its own would match a literal single `d`, when we add the backslash `\`, it now represents a predefined character class that matches any single digit between 0 and 9.

Now our example expression is starting to make more sense! Lets discuss Character Classes in further.

<br></br>

### <ins>Character Classes</ins>
Character classes, also known as character sets, are used to match any one out of a set of characters. They allow you to specify a range or set of characters that you want to match in a single position within your string. You define them by placing the characters to match inside of square brackets `[]` or using predifined shorthand notation.

<br>
Example:

- If you want to match an `a` or an `e`, use [ae]

- Gr`[ae]`y : Matches either `Gray` or `Grey`


A character class matches only a single character. The example above would not match `graay` or `graey`. The order of the characters does not matter. The results are identical. You can find a word even if it is misspelled, such as `char[ae]ct[eo]r`.

To specify a range of characters, we add a hyphen between the two. [0-9] matches a single digit between 0 and 9.

<br>

While we don't have any square bracket Character Classes in our example, we do have the shorthand version which is `\d`.


<br></br>

### <ins> Quantifiers </ins>

Quantifiers are essential for speficying the number of occurences and can make regex patterns much more flexible and powerful.
They specify how many times a particular character, group, or character class must occur.
It allows you to repeat characters,  and metacharacters.

<br>

Let's take a look at quantifiers and how the operate.

<br>

- `*` : In regex, this operator is a quantifier that speicifies that the preceeding element can be matched zero or more times. This means that the element before the `*` can appear any number of times, including not at all. 


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a*` matches zero or more occurences of the letter `a`. 

 &nbsp;&nbsp;&nbsp;&nbsp; `" "`, `a`, `aa`, `aaa`, etc.


- `+` : Matches the previous element one or more times. 
There are no limits on how many times it can match, but must match at least one time or will fail the match.


&nbsp;&nbsp;&nbsp;&nbsp;  Example : `a+` matches `a`, `aa`, `aaa`, etc but not `" "`.


- `?` : This is saying the element before it is optional, and matches the it zero or one time. Only allows one instance of the match to be found.


&nbsp;&nbsp;&nbsp;&nbsp; Example : `ea?` matches `e` and `ea`.


- `{n}` : Used to specifiy the exact number of matches. Matches exactly 'n' occurences of the preceeding element.


&nbsp;&nbsp;&nbsp;&nbsp;  Example: `a{3}` matches `aaa` but not `aa` or `a`. 


- `{n,}` : Used to specifiy approximate number of matches. Matches the previous element at least 'n' times.


&nbsp;&nbsp;&nbsp;&nbsp;  Example: `a{3,}` matches `aaa`, `aaaa`, `aaaaa`, and so on. 




- `*?` : Matches zero or more occurences of the preceeding element, but only as few as possible.


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a*?` matches `""` in the smallest way.


- `+?` : Matches one or more occurences of the preceeding element, but as few as possible.


&nbsp;&nbsp;&nbsp;&nbsp; Example: `a+?` matches `a` in the smallest way possible.


<br></br>

Lets take a look at our expression and see what types of quantifiers we have:


&nbsp;&nbsp;&nbsp;&nbsp; `^\d{3}-\d{2}-\d{4}$`

<br>

In our regex expression the quantifiers are `{3}`, `{2}`, and `{4}`.
<br>

```
`\d{3}`


 `\d` : Match any digit equivalent to [0-9]. 

 `{3}` : Specifies that the preceding element (a digit) must occur exactly 3 times. 

```
So this portion of the expression is saying "match exactly 3 digits in a row".


Examples
```
- `"123"` matches `"123"`.
- `"4567"` matches `"456"`, the fourth digit is not included in the match.
- `"89"` matches none.
- `"abc123def"` matches the substring `"123"`, even though it's surrounded by non-digit characters.
```



<br></br>


### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
