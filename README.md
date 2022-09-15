# Regex Tutorial: Email Validation

This tutorial will help break down the parts of a regex that is used to validate email addresses.

## Summary

Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

For this tutorial we will be breaking down the regex for matching an email. Emails usually contain three parts of a string of characters with @ and . seperating the three strings. Example: example@email.com

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

For this tutorial we will be using literal notation. Since this is going to be a literal we need to include the slash characters (/) in the starting and end of our literal. 

```/```^([a-z0-9_\\.-]+)@([\da-z\\.-]+)\\.([a-z\\.]{2,6})$```/```

### Anchors

Anchors are denoted by `^` and `$`. The `^` tells the starting point of the string and the `$` tells the endpoint of the string. 

For this example the email validation notation starts with `^` and ends with `$`. 

/```^```([a-z0-9_\\.-]+)@([\da-z\\.-]+)\\.([a-z\\.]{2,6})```$```/

### Quantifiers

Quantifiers are used to make limits for your regex when it comes to matching. 

For this example we just want to make sure the part of the string after . is between 2 - 6 characters. We need to use ```{ x, y }``` notation and also include the minimum charcters we want (x = 2) and maximum characters we want (y = 6). So our example will be ```{2, 6}```.

/^([a-z0-9_\\.-]+)@([\da-z\\.-]+)\\.([a-z\\.]```{2,6}```)$/

For the first and second part of the string we use ```+``` to match the pattern ```[]``` one or more times.

/^(```[a-z0-9_\.-]+```)@(```[\da-z\.-]+```)\\.([a-z\\.]{2,6})$/

### Grouping Constructs

Grouping Constructs are used to break up the regex into sections. The notation used for this is ```()```. 

In our example we have three main sections we want to break up: the string before `@`, string between `@` and `.`, and the string after `.`. We will be using ```()``` to seperate these sections.

/^```([a-z0-9_\.-]+)```@```([\da-z\.-]+)```\\.```([a-z\.]{2,6})```$/

### Bracket Expressions

Bracket Expressions are used to determine what characters we want to match/allow. They are represented by ```[]``` and the contents inside are what characters we want to match. 

In our example the first section of the string we want to allow any lowercase letters between a and z denoted by `a-z` (- being range). We also want to allow any numbers between 0 and 9 denoted by `0-9`. We also want to include `_`, `.`, and `-`. The `.` has to have a `\` before it (`\.`) since `.` on its own is a character class that matches any character expect newline characer. 

/^(```[a-z0-9_\.-]```+)@([\da-z\\.-]+)\\.([a-z\\.]{2,6})$/

In the second section of the string we want to allow any Arabic numeral digits (0-9). This is denoted by `\d`. We also want to allow lowercase letters between a and z. This is denoted by `a-z`. We also want to allow `.` which is denoted by `\.`. Lastly we also want to include `-`. This is denoted by `-`.

/^([a-z0-9_\\.-]+)@(```[\da-z\.-]```+)\\.([a-z\\.]{2,6})$/

In the third section of the string we want to allow any lowercase letters between a and z. This is denoted by `a-z`. We also want to allow `.`. This is denoted by `\.`.

/^([a-z0-9_\\.-]+)@([\da-z\\.-]+)\\.(```[a-z\.]```{2,6})$/

Note: In our regex there is a `@` and `\.` that are not grouped or have bracket expressions. This is to require the email validation to must have `@` and `.` between the three groups/sections.

/^([a-z0-9_\\.-]+)```@```([\da-z\\.-]+)```\.```([a-z\\.]{2,6})$/

### Character Classes

Character classes are different sets of characters. We have seen some in the Bracket Expressions section. For example `\d` is a character class that contains Arabic numeral digits 0-9. We also used the character class `0-9` to get the digits between 0 and 9. Another example is `a-z` is a character class that contains the lowercase letters between a and z.

/^([```a-z0-9```_\.-]+)@([```\da-z```\.-]+)\\.([```a-z```\.]{2,6})$/

### Character Escapes

Character escapes is a backslash `\` that escapes a character so that it would not be interpreted literally. We have seen this in the Bracket Expression section. For example, `\.` was used to be able to allow `.` as a vaild character.

/^([a-z0-9_```\.```-]+)@([\da-z```\.```-]+)```\.```([a-z```\.```]{2,6})$/

### Diana Contreras

I am currently a student at University of California Riverside Extension taking a full-stacks web development boot camp. If you want to contant me or see my GitHub profile my email and profile link is down below!

Email: dcontrer83@yahoo.com

Github: [dcontrer83](https://github.com/dcontrer83)
