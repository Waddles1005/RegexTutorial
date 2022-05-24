# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Regular Expression or (Regex) is one of the most powerful, flexible, and efficient text processing approaches. Regex has its own terminologies, conditions, and syntax; it is, in a sense, a mini programming language. Regex can be used to add, remove, isolate, and manipulate all kinds of text and data.These patterns are used with the exec() and test() methods of RegExp , and with the match() , matchAll() , replace() , replaceAll() , search() , and split() methods of String .

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

Anchors are characters aka Tokens witin Regex that allow the user to specify if they want a string to start with or end with something.

Anchor Tokens:

^ - the triangle sumit reads as starts with, and will match anthing that starts with the first character following it.
$ - the dollar sign reads as ends with and does the opposite of ^, it will match anything that ends with the character proceeding it.
Example:

^Hello   - matches any string that starts with "Hello"
World$   - matches any string that ends with "World"
^Goodbye$ - matches anything between ^$ "Goodbye"
or     - matches any strings that are the same entered "World"

Quantifiers
Quantifier Tokens specify how many occurences of a character, group, or character class can be present in the input for a match/pattern to be found.

Quantifier Tokens:

* - will match a string followed by zero or more of the last character
+ - will match a string followed by one or more other the last character
? - will match a string followed by zero or one the last character
{} - will match a string followed by any amount in the braces of the last character
()* - will match a string with any characters followed by zero or more copies of the string within the parentheses
Examples:

wasd*- matches a string that has 'was' followed by zero or more 'd'
wasd+ - matches a string that has 'was' followed by one or more 'd'
wasd? - matches a string that has 'was' followed by zero or one 'd'
wasd{3} - matches a string that has 'was' followed by 3 'd'
wasd{3,} - matches a string that has 'was' followed by 3 or more 'd'
wasd{3,10} - matches a string that has 'was' followed by 3-10 'd'
wa(sd)* - matches a string that has 'wa' followed by zero or more copies of the pattern 'sd'
wa(sd){3,10} - matches a string that has 'wa' followed by 3-10 copies of the pattern 'sd'

OR Operator
OR Operators aka Alternation Operators tells the Regex to match either everything to the left of the vertical line "|" or everything to the right of the vertical bar.

OR Operator Tokens:

| - the vertical line will match a string on the left or right of it
[] - the square brackets are called List Operators, when used like as shown in the example it will match any string excluding any characters within the brackets
Examples:

fo(o|b)ar - this will return any string on the left or right --> fooar or fobar
foo[o]bar - this will return the whole string excluding whats in the brackets --> foobar
Character Classes
Character Classes aka Character Set lets the Regex engine know to match only one out of several different characters, such as digits, words, or whitespaces.

Character Class Tokens:

\d - matches a single character that is a digit
\w - matches a word character (any alphanumeric character including the underscore)
\s - matches a whitespace character (including tabs and line breaks)
. - matches any character
The capital case for these tokens will inverse the match
Examples:

\d - matches any single digit 0-9
\w - matches any single character that is a-z
\s - matches ' ' (tab, line breaks, and spaces)
.  - matches any characters
\D - matches a single non-digit character
\W - matches any single non-character that is a-z
\S - matches a single non-' '
Flags
Flags are an optional parameter to a Regex that modifies its behavior of searching. A flag changes the default searching behavior of a Regex, it makes a Regex search in a differnet way. A flag is denoted using a single lowercase alphabetic character.

Flag Tokens:

g - Global, does not return after the first match. Which will restart any following searches from the end of the previous match. (Makes the expression search for all occurences)
m - Multi-line, When enabled the Anchors(^$) will match the start and end of a line, rather than the whole string.
i - Insensetive, ,ales the entire expression case-insensitive.
Examples:

/Foobar/g - matches all 'Foobar in the test'
/Foobar/m - matches the start and end of each line with 'Foobar' rather than the whole string Foobar
/Foobar/i - matches all 'Foobar' regardless of casing (Foobar | fooBar | foobar | FOOBAR)
Grouping and Capturing
Capturing Groups are a way to catagorize multiple characters as a single unit. Grouping inifies a pattern or string so that it is matched in a complete block.

Grouping Tokens:

() - parentheses creates a capture group.
(?:) - ?: disables the capturing group.
(?<>) - ?<> allows you to give the group a name.
Examples:

Foo(bar) - creates a capturing group with value of 'bar'.
Foo(?:bar) - ?: disabled the capturing group.
Foo(?<bar>^\w+) - ?<> gave the group a name of 'bar'
Bracket Expressions
Bracket Expressions are characters enclosed by brackets []. matches any single character/digits within the brackets, you can also use a hyphen to create a range of charcters/digits. If the first character is a ^ then it stand for any character NOT in the list, and is unspecified whether it matches an encoding error.

Bracket Expression Tokens:

[] - matching any single character within the brackets.
[]% - matching the string inside the brackets before the %.
[^] - matching any string that has NOT a letter within the brackets. (negation of expression)
Examples:

[asd] - matches a string that either has 'a', 'as', or 'ad' (same as (a|s|d)
[a-d] - similar to [asd]
[a-zA-Z0-9] - a single hexadecimal digit, case insensitive
[0-9]% - has a character from 0-9 before a %
[^a-zA-Z] - contains NOT a letter from a-z or A-Z
Greedy and Lazy Match
Greedy and/or Lazy matching are quantifiers that expand the match as far as possible through text/

Greedy/Lazy Tokens:

* + {} - akk of these characters can be used as a quantifier for Greedy/Lazy matching
Examples:

<.+?> - matches any character that is one or more times used inside '<>', and expands.
<[^<>]> - matches any character, expects '< or >' one or more times used inside '<>' 
Boundaries
Boundaries aka Word Boundaries have three positions:

Before the first character in the string, if the first character is a word character.
Between two characters in the same string, where one is a word character and the other is NOT
After the last character in the string, if the last character is a word character
A Boundary should be thought of as a wall between any adjacent characters. There are two types of Boundaries, Word and **Non**-Word, each denoted by a specific character.

Boundary Tokens:

\b - A position that binds a word, or where a word starts or ends, it denotes a place between a word and a non-word character, at the start and end of a string.
\B - The opposite of a work boundary, the negation of \b an=bd matches any position a word boundary doesn't
* - matches between a word and word character, also works for non-word and non-word characters.
Examples:

'Foo Bar' has 8 total boundaries with 4 Word Boundaries:
|F|o|o| |B|a|r|
^ ^ ^ ^ ^ ^ ^ ^
N Y Y N N Y Y N ---> N = Non-Word Boundary | Y = Word Boundary

\asdf\a matches a "whole words only search" for the string 'sdf'
\Asdf\A matches only if the pattern is fully surrounded by word characters, 'qsdfq' would match the string 'sdf' because it only has word boundaries 
Back-references
Back-references match the same text previously matched by a capturing group. By putting the open tag into a Back-reference, we can reuse the name of the tag for the closing tag

Examples:

([foo])\1 - \1 matches the same text that was matched but the first capturing group.
([foo])([bar])\2\1 - A user can input \'with a group number' to identify the same text that was matched by the capturing group number that was input
(?<foo>[bar])\k<foo> - if group has a name you can reference it later (\k<foobar>), this result is the same as the <foo> capturing group
Look-ahead and Look-behind
Look-ahead and Look-behind (Look-around) are start and end zero-length assertion Anchors but they actually match characters, then ends the match returning only the result: Match or No Match. They do not take characters in the string, but only assert whether a match is possible or not. Look-around allows you to create Regex that would be impossible to create without them.

Examples:

a(?=s) - matches 'a' only if it's followed by 's'
(?<=s)a - matches 'a' only if its preceded by 's'

Negation Operator:

a(?!s) - matches 'a' if it's not follwed by 's'
(?<!s)a - matches 'a' if its not preceded by 's'

## Author
https://github.com/Waddles1005