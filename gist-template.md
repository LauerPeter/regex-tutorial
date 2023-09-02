# Regex Tutorial: Matching an Email

Regex, which is short for regular expressions, is a potent tool in programming. This tutorial will unravel the components of a regex pattern designed for validating email addresses.

## Summary

The regex pattern we will look at for validating email addresses:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Let's break down each component of the regex pattern for validating emails by reviewing the table of contents found below.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)

## Regex Components

### Anchors

Our regex pattern utilizes two essential anchor components, which are: ^ (caret) and $ (dollar sign)

   ^ (caret) - Starts at the beginning of the expression to start the string value, also the start anchor.
   
   $ (dollar sign) - Ends at the last instance of the expression for the entire string's value, also the end anchor.

      `/"^"([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})"$"/`

### Quantifiers

Quantifiers allow you to specify how flexible the email address validation should be, depending on the specific validation requirements. The quantifiers we will look at are not limited to our regex pattern * (Asterisk), + (Plus Sign), ? (Question Mark), {n} (Exact Quantity), {n,} (Minimum Quantity), and {n,m} (Range).

Examples using real characters - 

    * (Asterisk) - The asterisk matches zero or more occurrences of the current character or group. - example: (abc)* would match "abc" and "abcabc" or even an empty string.
    
    + (Plus Sign) - The plus sign matches one or more occurrences of the current character or group. - example: (abc)+ would match "abc" or "abcabc" but not an empty string.
    
    ? (Question Mark) - The question mark matches zero or one occurrence of the current character or group. - example: (abc)? would match "abc" or just an empty string.
    
    {n} (Exact Quantity) - The {n} allows you to specify exactly how many repetitions are being used. - example: (abc){3} matches "abcabcabc".
    
    {n,} (Minimum Quantity) - The {n,} allows you to specify the minimum repetitions being used. - example: (abc){2,} would match "abcabc","abcabcabc" and so on.
    
    {n,m} (Range) -The {n,m} allows you to specify a range of repetitions being used. - example: (abc){2,4} matches "abcabc," "abcabcabc," or "abcabcabcabc."

In our regex pattern, we are utilizing the plus sign and {n,m} -

  `[a-z0-9_\.-]+"`   -- Matches one or more characters that are either lowercase letters, digits, underscores, periods, or hyphens.

  `[\da-z\.-]+"`   -- Matches one or more characters that are either digits, lowercase letters, periods, or hyphens.

  `[a-z\.]{2,6}`    -- This range is specifying the number of times [a-z\.] is supposed to match up, allowing 2-6 times.
    
### Character Classes

Character classes are used to match character groups. They are single characters preceded by a backslash \ 

 `\d`   -- matches any character digit from 0 to 9.

### Grouping and Capturing

( ) are used for grouping, and they also define capturing groups. You can create sub-patterns out of grouping and capturing, allowing you to extract parts of a matched text. The capturing groups are essential for acquiring specific parts of an email address, examples from the regex pattern -

  `([a-z0-9_\.-]+)`   

  `([\da-z\.-]+)`   

  `([a-z\.]{2,6})`    

### Bracket Expressions

Bracket expressions are a fundamental part of regex patterns, enabling you to specify which characters are valid within specific portions of the text you're trying to match. 

 `[a-z0-9_\.-]`    -- Matches any lowercase letter, digit, underscore, period, or hyphen. It's used in the local part of the email address, allowing for characters like "user_123."

  `[\da-z\.-]`    -- Matches any digit, lowercase letter, period, or hyphen. It's used to match characters in both the local part and domain name of the email address.

  `[a-z\.]`   -- Matches lowercase letters or periods. It is used in the top-level domain (TLD) part of the email address, ensuring that TLDs like "com" or "co.uk" are matched.

### Greedy and Lazy Match

"Greedy" and "lazy" refer to how our quantifiers, such as "+", from our regex pattern, handle matching text.

"+" is a greedy match. It matches one or more occurrences of the preceding element as many times as possible.

`/^([a-z0-9_\.-]"+")@([\da-z\.-]"+")\.([a-z\.]{2,6})$/`

### Boundaries 

The boundaries represented in our regex pattern are the `^` and `$`. They ensure that the email address is matched within the full string without extra characters before or after.

## Author

Peter Lauer - Student at the University of Minnesota's Full-Stack Bootcamp

GitHub URL: [Your GitHub Profile URL]