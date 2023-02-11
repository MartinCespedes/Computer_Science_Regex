## ![License](https://img.shields.io/badge/License-MIT-yellow.svg)

Copyright (c) 2023 Martin Cespedes

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


## Link to Github Gist

[GithubGist](https://gist.github.com/MartinCespedes/22bf4c22c1d31e7c7e36f717af1adc2d)

## Regex Tutorial

- A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

- For example, the following regular expression can be used to verify that user input is a valid email address:

- /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Regex Components](regex-components)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-contructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Matching an Email Address](#matching-an-email)
- [Conclusion](#conclusion)
- [Author](#author)

## Introduction

The Regular Expression
/^ - Asserting the start of the string
([a-z0-9_\.-]+) - Matching the username part of the email address
@ - Matching the "@" symbol
([\da-z\.-]+) - Matching the domain name part of the email address
\. - Matching the "." symbol
([a-z\.]{2,6}) - Matching the top-level domain (TLD) part of the email address
$/ - Asserting the end of the string

## Regex Components

A regular expression consists of two types of characters:

- Literal characters

- These are the characters that match themselves, such as letters, numbers, and punctuation.
  Meta characters: These are special characters that have a special meaning in Regex, such as the ., \*, and ^ characters.
  Anchors
  Anchors are used to match the position of a string, rather than the characters themselves. There are two main types of anchors:

- ^ matches the start of a line.
- $ matches the end of a line.
- For example, the expression ^A matches any string that starts with the letter 'A', while the expression end$ matches any string that ends with the word "end".

## Anchors

- Anchors are used to specify the position of the pattern in the text being matched. The two most commonly used anchors are the start-of-line anchor (^) and the end-of-line anchor ($).

- For example, the regular expression /^A/ would match any line that starts with the letter "A". On the other hand, the regular expression /A$/ would match any line that ends with the letter "A".

## Quantifiers

- Quantifiers are used to specify how many times a pattern should be matched. For example, the regular expression /A{3}/ would match any line that contains the letter "A" repeated three times.

- There are several different quantifiers available, including:

{n} - Matches exactly n occurrences of the pattern
{n,} - Matches at least n occurrences of the pattern
{n,m} - Matches at least n and at most m occurrences of the pattern

- - Matches zero or more occurrences of the pattern

* - Matches one or more occurrences of the pattern
    ? - Matches zero or one occurrence of the pattern

## Grouping Constructs

- Grouping constructs are used to group patterns together. This allows you to apply quantifiers to the entire group, instead of just a single character.

- For example, the regular expression /(A|B){3}/ would match any line that contains either the letter "A" or the letter "B" repeated three times. The grouping construct makes it possible to apply the quantifier {3} to the entire group of characters "A" or "B", rather than just one individual character.

- Grouping constructs can also be used for capturing parts of the match for use later. For example, the regular expression /^(A|B)/ would capture either the letter "A" or "B" if it appeared at the start of a line.

- There are two types of grouping constructs in regular expressions:

- Capturing groups ((...)) - Captures the matched text for later use.
  Non-capturing groups ((?:...)) - Groups patterns together, but does not capture the matched text.

## Bracket Expressions

- Bracket expressions are used to match a range of characters. They consist of a set of characters enclosed in square brackets ([]).

- For example, the regular expression /[A-Z]/ would match any uppercase letter. Bracket expressions can also be used to specify a range of characters, such as [A-Za-z0-9] which would match any letter or digit.

- In addition to matching ranges of characters, bracket expressions can also be used to match characters that are not in the range. This is done by including a caret (^) as the first character inside the brackets. For example, the regular expression /[^a-z]/ would match any character that is not an uppercase letter.

## Character Classes

- Character classes are predefined sets of characters that are used to match specific types of characters. For example, the character class \d matches any digit, and the character class \s matches any whitespace character.

There are several different character classes available, including:

\d - Matches any digit (0-9)
\w - Matches any word character (A-Za-z0-9\_)
\s - Matches any whitespace character (space, tab, newline)
\D - Matches any non-digit character
\W - Matches any non-word character
\S - Matches any non-whitespace character

## The OR Operator

- The OR operator (|) is used to match multiple patterns. For example, the regular expression /A|B/ would match any line that contains either the letter "A" or the letter "B".

- The OR operator can be used in combination with other regular expression components, such as quantifiers, grouping constructs, and character classes, to match more complex patterns.

## Flags

- Flags are used to modify the behavior of the regular expression. There are several different flags available, including:

- i - Makes the regular expression case-insensitive
- m - Makes the regular expression match across multiple lines
- s - Makes the "." character match newline characters
- u - Makes the regular expression use Unicode
- x - Allows the regular expression to contain comments and whitespace for improved readability

## Character Escapes

- Character escapes are used to match special characters that have a specific meaning in regular expressions. For example, the regular expression /\*/ would match the literal character "_", instead of matching any number of characters (as the _ quantifier would normally do).

- There are several different character escapes available,
  including:

\ - Escapes the following character, so it is treated as a literal character rather than having its special meaning in the regular expression
\d - Matches any digit (0-9)
\w - Matches any word character (A-Za-z0-9\_)
\s - Matches any whitespace character (space, tab, newline)
\D - Matches any non-digit character
\W - Matches any non-word character
\S - Matches any non-whitespace character
Using character escapes can be useful when you want to match a special character, such as . or \*, that would otherwise have a special meaning in the regular expression.

## Matching an Email

- The following regular expression can be used to match an email address: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. This regular expression can be broken down into the following components:

- ^ - Matches the start of the line
- ([a-z0-9_\.-]+) - Matches one or more characters that are lowercase letters, digits, underscores, dots, or hyphens, and captures this as the first group
- @ - Matches the at symbol
- ([\da-z\.-]+) - Matches one or more characters that are digits, lowercase letters, dots, or hyphens, and captures this as the second group
- \. - Matches a dot
- ([a-z\.]{2,6}) - Matches 2-6 characters that are lowercase letters or dots, and captures this as the third group
- $ - Matches the end of the line
- This regular expression uses several of the components and techniques covered in this tutorial, including anchors, grouping constructs, character classes, and character escapes.

## Conclusion

- In conclusion, regular expressions are a powerful tool for matching and manipulating strings. By understanding the various components and techniques that make up regular expressions, you can use them to solve a wide range of text-related problems in your programs.

## Author

- Martin Cespedes - [Link to Github](https://github.com/MartinCespedes)
