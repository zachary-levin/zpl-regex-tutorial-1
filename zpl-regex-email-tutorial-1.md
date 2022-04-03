# zpl-regex-email-tutorial-1
In this tutorial, I will be looking at a regex (short for regular expression) used for matching an email address. I will be explaining and breaking down the components found in this regex, highlighting the instances for each component and where they are in the expression, as well as what they do in their context.

## Summary

The regex I will be describing is a regular expression for matching an email address. The regular expression I will be using throughout is `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. The components I will be looking at are anchors, quantifiers, character classes, grouping and capturing, bracket expressions, and greedy and lazy match.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

An anchor is a way to say that your regular expression has to start with and end with something rather than containing something.

For example, in the regular expression for an email address, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the beginning anchor is the carrot `^`.

The ending anchor is the dollar sign `$`. This means the entire string must match this regular expression with nothing before or after the expression.

### Quantifiers

Quantifiers act as a quantitative criteria that requires a preceding pattern to match within the range given in the component.

For example, in the regular expression for an email address, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the quantifier is `{2,6}` and `+`.

In this context, the quantifier requires the preceding pattern to be between 2 and 6 characters.

### Character Classes

Character classes match a character from an established set. Sets can be custom-made by a developer or picked from a list of pre-made ones. The format for a character class varies from set to set, but most sets either are preceded by a backslash `\`. 

In the regular expression for an email address, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there is one character class (`\d`).

In this context, `\d` matches a single character that is a digit from 0 to 9. 

### Grouping and Capturing

Groups take multiple patterns in a row and combine them so they run together in a row. Capturing groups multiple patterns together and creates a capture group for extracting a substring or using a back reference.

For example, in the regular expression for an email address, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the groups present are formatted with (`('code')`), using parentheses.

In this context, the regular expression is grouping all of the character classes using parentheses.

### Bracket Expressions

A bracket expression is a set of characters enclosed within brackets(`[]`). Bracket expressions match any single characters in that list. 

In the regular expression for an email address, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are multiple bracket expressions. We will break the example up into three parts.
The first part (before the @ symbol), the second part (after the @ symbol), and the last part (after the period). The pieces contained within the brackets(`['code']`) are the bracket expressions.

The first part (`/([a-z0-9_\.-]+)`) contains 5 bracket expressions. The first one is `a-z`, which contains lowercase characters from A to Z. The second one is `0-9` which contains numeric characters from 0 to 9. The third is the underscore (`_`), which simply matches an underscore. The fourth bracket expression is `\.` which matches periods, but in this context it's known as an "escaped character." The reason why it's formatted like this is because periods by themselves are considered their own character classes. The last one in this part is the dash (`-`) at the end. This simply matches dash characters. 

The second part(`([\da-z\.-]+)\`) contains three bracket expressions. These three can be found in the first part of the entire regex - (`a-z`), (`\.`), and (`-`) - and act the same way as they do in the first part. 

The third part (`([a-z\.])/`) contains two bracket expressions - (`a-z`) & (`\.`) - and both act the same as they do in the other parts of the regex.

### Greedy and Lazy Match

Greedy and Lazy Match are traits that affect what a quantifier does. Normally, quantifiers are greedy by default, which means they match the longest possible string in a regular expression.

In the email address regular expression, the `{}` and `+` quantifiers are considered greedy. If we were to add a `?` to the `+`, it would become lazy. 

Lazy expressions try to match the shortest possible string. Since we are trying to account for potentially very long email addresses, we do not want to limit users on how long their email address can be.

## Author
My name is Zachary Levin. I am currently going through a programming boot camp, seeking to expand my skillset to become a full-stack web developer. My GitHub profile can be found [here](https://github.com/zachary-levin). 
