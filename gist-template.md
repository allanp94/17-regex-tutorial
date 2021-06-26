# Regular Expression(Regex) Email Address Validation

The following tutorial will explain how a **regular expression** is composed in order to verify an email address. Each component of the regular expression will be broken down and discussed in detail and then put back together piece by piece in order for you understand how a sequence of characters is called a regular expression, also known as **regex**.

## Summary

The Regex that will be used to validate an email address is composed of 3 parts, a) the part before the @, b) the @ symbol, and c) the part after the @ that includes the domain. The first part can include any alphaNumeric characters including "-", ".", "\_", the second needs to be an @ sign, followed by a sequence of alpaNumeric characters that could have a "-" or a "." as well, that seperates the last 3 charactes with a "." .

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Character Classes](#character-classes)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator ](#or-operator)
- [Grouping and Capturing](#grouping-and-capturing)
- [Regex Breakdown](#regex-breakdown)

## Regex Components of `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Character Classes

    Character classes are used to match any symbols from a given set, either alphanumeric, numbers, or just spaces.

        The number character class is denoted by \d and corresponds to any single digit.  \d could be a 0 or a 9.

        The alphanumeric class is denoted by \w and corresponds to any single alpanumeric character including an underscore. \w could be e, z, 8, or _ .


        The whitespace space character class that includes tabs and line breaks denotes that a space is expected in the search.

### Anchors

The two anchors in our regex are **^** and **$** .

      The first anchors purpose ^ is to identify any string of characters that follow right after the anchor.

        ^allan will match any string that begins with a set of characters e.x. allan

      The purpose of the second anchor $ is to identify any string of characters that end before the anchor.

        .com$ will match any strings that end with .com

### Quantifiers

    Quantifiers, *, +, ?, {"someNumber"}, ("someSequence"),  are quite interesting as the allow you to denote how many charactes of a specific character class will be stringed together.

    \d{3} means that three numbers will be searched e.x 567

    ^\d{3} means that it will search for a sting that BEGINS with three numbers

    \d{3}$ means that it will search for strings that END with three numbers

    \d\w+ means that it will search for a number that is followed by ONE OR MORE alphanumeric characters e.x. 7e, 7ewwq, 77, 7_

    \d\s? means that it will search for a number followed by a ZERO OR ONE SPACE, so the "?" states that it is optional

    \d{2}\s?\d means that it will search for two numbers that MAY have a space after it, followed by another number e.x 72 4, 771,

    a\d{4,8} means that it will search for the letter "a" followed by 4 AND UP TO 8 NUMBERS e.x a5555, a999999, a66666666

    \+ \$ \^ \. mean that we literally are looking for the respective symboles of "+", "$", "^", or "." .

### OR Operator

    The OR operator [] is used to show that some length of string could either have alphanumeric, spaces, or other characters

          [-.] means that a character can either be a "-" or "." . The "-" in the or operator is REQUIRED to come first or last or else its meaning changes.

          [a-z\d\s] means that the character could be in between "a" and "z", or a number, or a space. So if the "-" is not first then it's not considered a literal "-" .

          ^\d{3}[-.]\d{3}[-.]\d{4}$ means that we are searching for a string of characters that STARTS with 3 numbers, followed by EITHER a "-" or a ".", followed by 3 numbers, followed by EITHER a "-" or a ".", and that ENDS with 4 numbers

### Grouping and Capturing

    Grouping and Capturing groups characters that are in between parenthesis and captures their values regardless of whatever else is going on inside them

        a(\d){2} means that it will search for the letter "a" followed by two numbers that is captured

        a(?:\d){2} using ?: will disable the capturing of the copy of the two numbers

    When something is matched it is always captured at GROUP 0, so when something is additionaly captured by placing ( ) around an expected set of characters, moving from left to right it is saved as GROUP 1, GROUP 2 and so on depending on how many substrings a user is trying to capture.

### Regex Breakdown

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

    So we start off our regular expression that says that we are looking for a string that starts, ^ , with multiple occurances (at least one) + , of either [ ], string that is from a to z, 0 to 9, maybe an underscore, a fullstop, or a dash.

    That string has to be followed by a "@" and then again a string with mulitple occurances (at least one) +, of either [ ], that could have a number, \d , a character from a to z, a fullstop, or a dash.

    Then that has to followed by a fullstop, because we have a backdash \ and a fullstop together, which means a LITERAL fullstop. Then after that it is expected to end, $ , with a string from the range of 2 to 6,  {2,6} , of either [ ] , that could have a string of characters from a to z and a fullstop.

## Author

    Hello, my name is Allan Pirillis a computer science graduate that loves to learn and share my personal perspective of how I view and comprehend various topics. This is my first exposure to making a tutorial and curious to see how it turns out.

    Would love to hear about any feedback that you might have! Contact me at allan.p94@gmail.com
