# Regex Tutorial
A regex, (or regular expression), is a set of characters that defines a search pattern. A regex can be used within code and/or an algorithm to find (or find and replace) specific character patterns within a string. For example, one can identify phone numbers, email addresses, URLs, etc by using a regex. A regex can also be used to validate user input.

This tutorial was created as an assignment for the University of Arizona's coding bootcamp. The purpose of this tutorial is to explain in detail how a specific regex functions by breaking down each part of the expression and describing what it does.

## Summary

This tutorial will examine each character in the following regex in order to explain its overall function:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This regex matches an email. It can therefore be used to find email addresses within a string of text, verify that a user has entered a valid email address, etc.

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

The ^ and $ in the regex are Anchors, as seen in the beginning and end of the expression:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

The ^ beginning anchor is used to match any string that begins with the character(s) following it in the expression. For example, ^Hello would match any string that begins with the word "Hello."

The $ ending anchor is used to match any string that ends with the character(s) proceeding it in the expression. For example, Goodbye$ would match any string that ends with the word "Goodbye."

When a regex contains both beginning ^ and ending $ anchors, a search using the regex will return an exact string match of the characters included between the anchors. For example, ^Hello and Goodbye$ will return any strings that include the exact words "Hello and Goodbye."

In our regex above, the beginning ^ and ending $ anchors indicate that the search must match characters defined by the piece of the expression located between the anchors: ([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6}) We will explain each of these components in their respective sections below.

### Quantifiers

The curly brackets {} in the regex indicate quantifiers, as shown by {2,6} towards the end of the expression:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Quantifiers indicate how many of the proceeding character(s) must exist to return a match. For example, the expression a{1,5} would match all strings in which "a" occurs between 1 and 5 times. Similarly, (ab){1,5} would match all strings in which (ab) occurs between 1 and 5 times.

In our regex above, we can see that any characters represented by ([a-z.] must occur between 2 and 6 times return a match. We will define these components later in the tutorial, but in the meantime it is important to note that this quantifier indicates that the characters after the . are letters between 2 and 6 characters in length. When using this regex to search for email addresses, this part of the expression would indeed match standard email domains such as ".com" and "net."

### OR Operator

Operator in the regex [a-z.] indicates that any letter from a-z or a dot . in this location would return a match. As mentioned in the Quantifiers section above, this refers to the domain at the end of the email address. For example, the characters "com" in the email address "coder123@gmail.com" would return a match as they are comprised of letters from a-z. International or similar domains including an extra dot . such as ".co.jp" would also return a match, as a dot . is included within the OR Operator.



### Character Classes

Character Classes are identified with a backslash \ and can be found proceeding . and d characters in our regex:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Including the backslash before a dot . indicates that we are literally searching for a dot. In our regex above, we want to ensure our search matches email addresses that may include a dot before the @ sign (firstname.lastname@gmail.com) and as part of the domain (.com, '.net, .co.jp). Note: in regular expressions, a dot by itself indicates that we are searching for any character.

The \d Character Class matches a single character that is a digit from 0-9. In our regex above, [\da-z.-] indicates that we are looking for a digit, or a letter from a-z, or a dot . or a dash -. As described above in the OR Operator section, this piece refers to the portion of the email address after the @ sign (gmail, hotmail, etc).

### Flags

Flags are the forward slashes // that begin and end the regex:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Regular expressions, including our regex above, are generally contained within slashes // that simply delimit the search pattern. Some expressions have specific flags that modify the search parameters, such as making the seach case-insensitive, but our regex just includes standard flags.

### Grouping and Capturing

Grouping and Capturing Parentheses () are used in regular expressions to group together pieces of the search. In our regex, our expression is grouped into 3 sections:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

As defined in previous sections above, the first group ([a-z0-9_.-]+) consists of the characters before the @ sign in an email address (coder123, firstname.lastname, etc). The second group ([\da-z.-]+) consists of the characters just after the @ sign in an email address (gmail, hotmail, etc). The third group ([a-z.]{2,6}) consists of the domain after the dot . at the end of the email address (com, net, co.jp, etc).



### Greedy and Lazy Match

Greedy Match A Greedy Match is created when a regex includes a + as we can see twice in our regex below:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

The + basically means "as many as possible" of the previous character(s), For example, A+ would match "A", "AA", "AAA", and so on because it will match as many "A"s that may exist in the location.

In our regex above, the characters directly before the @ sign [a-z0-9_.-] and directly after the @ sign [\da-z.-] are both followed by a +. In the context of this regex, it means there is not a limit to how many characters may exist before and after the @ sign. ''

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
