# Regular Expression(Regex) Email Address Validation

The following tutorial will explain how a **regular expression** is composed in order to verify that an email address is valid. Each component of the regular expression will be broken down and discussed in detail and then put back together piece by piece in order for you understand how a sequence of characters is called a regular expression, also known as **regex**.

## Summary

The Regex that will be used to valid an email address is composed of 3 parts, a) the part before the @, b) the @ symbol, and c) the part after the @ that includes the domain. The first part can include any alphaNumeric characters and "-", ".", "\_", the second needs to be an @ sign, followed by a sequence of alpaNumeric characters and "-" that seperates the last 3 charactes with a "." .

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Character Classes](#character-classes)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Grouping and Capturing](#grouping-and-capturing)

## Regex Components of `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Character Classes

    Character classes are used to match any symbols from a given set, either alphanumeric, numbers, or just spaces.

        The number character class is denoted by \d and corresponds to any single digit.  \d could be a 0 or a 9.

        The alphanumeric class is denoted by \w and corresponds to any single alpanumeric character including an underscore. \w could be e, z, 8, or _ .


        The whitespace space character class tha includes tabs and line breaks denotes that a space is expected in the search.

### Anchors

The two anchors in our regex are **^** and **$** .

      The first anchors purpose **^** is to identify any string of characters that follow right after the anchor.

        ^allan will match any string that begins with a set of characters e.x. **allan**

      The purpose of the second anchor **$** is to identify any string of characters that end before the anchor.

        .com$ will match any strings that end with **.com**

### Quantifiers

    Quantifiers, *, +, ?, {"someNumber"}, ("someSequence"),  are quite interesting as the allow you to denote how many charactes of a   specific character class will be stringed together.

    \d{3} means that three numbers will be searched e.x 567

    ^\d{3} means that it will search for a sting that **BEGINS** with three numbers

    \d{3} means that it will search for strings that **END** with three numbers

    \d\w+ means that it will search for a number that is followed by **one or more** alphanumeric characters e.x. 7e, 7ewwq, 77, 7_

    \d\s? means that it will search for a number followed by a **zero or one space**, so the ? states that it is optional

    \d{2}\s?\d means that it will search for two numbers that **MAY** have a space after it, followed by another number e.x 72 4, 771,

    a\d{4,8} means that it will search for the letter "a" followed by **4 and up to 8 numbers** e.x a5555, a999999, a66666666

### OR Operator

    The OR operator [] is used to show that some length of string could either have alphanumeric, spaces, or other characters

          [-.] means that a character can either be a "-" or "." . The "-" in the or operator is **required** to come first or else its meaning changes.

          [a-z\d\s] means that the character could be in between "a" and "z", or a number, or a space.

          ^\d{3}[-.]\d{3}[-.]\d{4}$ means that we are searching for a string of characters that **starts** with 3 numbers, followed by **either** a "-" or a ".", followed by 3 numbers, followed by **either** a "-" or a ".", and that **ends** with 4 numbers

### Grouping and Capturing

    Grouping and Capturing groups characters that are in between parenthesis and captures their values regardless of whatever else is going on inside them

        a(\d){2} means that it will search for the letter "a" followed by two numbers that is captured

        a(?:\d){2} using ?: will disable the capturing of the copy of the two numbers

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
