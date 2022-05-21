# Regex. How and Why.

A regular expression (Regex) are a sequence of characters used to find matching character combinations in text. The MDN web docs describe it as, "Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp, and with the match(), matchAll(), replace(), replaceAll(), search(), and split() methods of String."("Regular expressions," 2021).

## Summary

We will be working with the regex to evaluate HEX color values with alpha. <br>
`\B#(?:[a-fA-F0–9]{6}|[a-fA-F0–9]{3})\b`<br>
Below there will be details on the components of regular expressions, to gain a better understanding. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
These are special sequences, which match an empty substring. Meaning they themselves do not match anything, just denote something about the string, such as beginning or end. They are case sensitive.
<ul>
    <li>^, indicates the beginning of the string. Example (/^a, matches a. /^A, matches A)</li>
    <li>$, indicates the end of the string. Example (/a$, matches a in the sequece cba)</li>
    <li>\b, matches a boundry. Example (/ee\b/, will not match with green because there is an n after the ee)</li>
</ul>

### Quantifiers
Quantifies specify the number of charcters to match
<ul>
    <li>*, Matches pattern zero or more times. Example (/a*, matches with <strong>a</strong>ll instances of <strong>a</strong> <strong>a</strong>long the string) </li>
    <li>+, Matches the preceding itme 1 or more times. Example (/o+/, matches o in to, and all o's in mooooooo)</li>
    <li>{}, Matches exactly the number of occurances or the preceding item. Example (/a{3}, will not match aah, but will match aaah). If stated {1,2} will match at least 1 occurance and at most 2 occurances.</li>
</ul>

### Grouping Constructs
Grouping constructs help narrow down search
<ul>
    <li>[], Matches the first occurance of expression. Example ([ijk] will match the j in jace)</li>
    <li>|, Will match either occurance passed. Example (/dog|cat/, will find dog and cat in sentance, "the cat doesn't like the dog.")</li>
    <li>(), Matches the exact occurance. Example ((abc), matches abc, but not acb)
</ul>

### Bracket Expressions
Use brackets to create character set. Example ([abcde], will match a in tar)

### Character Classes
Character classes distinguish character types to search for.

<ul>
    <li>\d, matches any digit</li>
    <li>\w, matches any alphanumeric character</li>
    <li>\s, matches single white space</li>
</ul>

### The OR Operator
|, is the or operator. Example(^a|b$|c*, matches a starting a string, b ending a string, or all instances of c)


### Flags
Added to end of expression for additional functionality
    <ul>
        <li>g, will look globally</li>
        <li>i, removes case sensitivity</li>
    </ul>


### Character Escapes
\, allows us to search for character that is used in regex. Example(/\^a, will search for instance of ^a in string)


### Hex Value
/\B#([a-fA-F0-9]{6}|[a-fA-F0-9]{3})\b/g. This will be our regex to find hex color values. To break it down further: <br>
<ul>
<li>#, needs to begin with #</li>
<li>[a-fA-f0-9]{6}, lowercase character range from a to f, uppercase character range from A-F, numerical range from 0-9, must match 6 times.</li>
<li>[a-fA-f0-9]{6}, lowercase character range from a to f, uppercase character range from A-F, numerical range from 0-9, must match 3 times.</li>
<li>g, global search
</ul>

## Author

Jace Feinstein. Find me at https://github.com/jacef790
