# Regex Tutorial

Regex (regular expression) is sequence of characters that define a logical pattern and can be used to confirm character combinations, such as those used to match email addresses, url's, and sensitive data like social security numbers.

## Summary

In this tutorial we will be using the following string as our example `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` along with other small examples listed in the upcoming sections.

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

- In our example `^` and `$` are anchors. They are used to match a position before of after characters.

### Quantifiers

- In our example, `+` and `{2,6}` are the quantifiers. They tell the regex engine how many instances of a certain character, character class, or character group must be input by the end user in order to return the match as true.
  - The `+` quantifier tells the engine to look for at lease 1 preceeding expression enclosed in the `[]`.
  - The `{2,6}` quantifier that tells the engine to look between 2 intances and 6 intances of the preceeding character or character class which in the exaple are `[a-z/.]`.

### OR Operator

- The `|` operator, known as the OR operator or (alternation) gives the user the option to match 2 different patterns.
- Event though it is not used in our example we could potentially use it to between our string and a second string that would also return a true statement. As long as one string returns true the statement is true.
- Consider the following example : `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`
  - Written as : `/^#?([a-f0-9]{6}`|`[a-f0-9]{3})$/`
  - Read as : `/^#?([a-f0-9]{6}` OR `[a-f0-9]{3})$/`

### Character Classes

- In our example, `\d` located in `[\da-z\.-]` notes the character class.
- It matches a specific character from a certain character set, in this case the digit class.
  - `\d` looks for a match to single `d`igit
  - `\s` would look for a match with white `s`pace including tabs and line breaks
  - `.` would look for any character matches
  - `\w` would look for a match tha is a `w`ord character

### Flags

- Flags work as settings in regex. They change or modify the engines searh behavior.
- Exmaples of flags:
  - `i` flags the search so it is not case sensitive
  - `g` global match, searches for all occurances
  - `m` would look for multi-line search matches, when enabled the `^` and `$` characters will match the start and end of the line instead of the whole string
  - `y` enables 'sticky' mode which helps search at the exact position in the text.

### Grouping and Capturing

- The parentheses`()` in our example are used to group or capture a string.
- The text beween the parentheses is considered a group and is added to an array.
- We can see it a few times in our example
  - `([a-z0-9_\.-]+)`
  - `([\da-z\.-]+)`
  - `([a-z\.]{2,6})`
- This allows us to get a partial match as a separate item in the resulting array.
- The quantifier after that parentheses will apply the match to everything in the parentheses.
- Other examples:
  - `(?:)` disables the capture group
  - `(?<>)` puts a name to the group

### Bracket Expressions

- The `[]` note a group of characters that we are trying to match.
- The characters enclosed in the brackets will return true if the engine matches them.
  - In our example, `[a-z0-9_\.-]` will try to match any letters `a-z` and any number between `0-9` as well as the characters ` _ - .`
- Other bracket examples:
  - `[]%` matches the string to the charcater inside the brackets but before the `%`
  - `[^]` matches any string that doesn't include the characters in the brackets

### Greedy and Lazy Match

- Greedy match will try and match the longest possible match.
- Lazy match will try to match the shortest possible match
  - In our example, `+` and `{}` are greedy searches because they try to expand the match as far as they can.
  - `*` is another character that can be used for expanding a greedy search or a lazy match

### Boundaries

- Boundaries a positions between characters
  - `\b` a word boundary, or where a word starts and ends. It denotes a place between a word and non-word character
  - `\B` a non-word boundary, will match any position opposite of word boundary
  - `*` matches between a word and word character, as well as between a non-word and non-word character

### Back-references

- A back reference identifies a previously captured matched group and matches it again.
  - For instance, in `([abc])/1`, the back reference is `/1` and will match the same text that was matched by the first capturing group.

### Look-ahead and Look-behind

- Known as 'lookaround', look-ahead and look-behind, will find matches for patterns that are followed or preceeded by a different pattern.
  - For instance, the following `X(?=Y)` tells the engine to look for `X`, but only if it followed by `Y`.

## Author

My name is Idzel Jaimes. Thank you for reading this tutorial!

I hope you found it helpful, and if you would like to checkout more of my work follow the link below!

<https://github.com/irjaimes>
