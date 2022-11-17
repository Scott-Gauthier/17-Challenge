# Regex Password Validation

	A regular expressions, or regex specifies a sequence of characters that can be used for a search, set criteria,
	or be used for input validation.

## Summary

	I am going to be talking about the password validation regex below:

			/^[a-zA-Z0-9!#$%&()*+,-./:;<=>?@[]^_~]{8,}$/

	the purpose of the above password regex is to refactor my week 03 homework assignment and make it more efficient.
	In general a password validation regex is useful so that you make make sure a password selected by a user meets
	minimum requirements and is harder to break into the system and make it more secure.

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

	(/^						//references the beginning
	(?=.*\d)					//should contain at least one digit
	(?=.*[a-z])					//should contain at least one lower case
	(?=.*[A-Z])					//should contain at least one upper case
	(?=.*[!#$%&()*+,-./:;<=>?@[]^_~])	//should contain at least one special character
	{8,}						//should contain at least 8 from the mentioned characters
	$/)						//references the ending


### Anchors

	The caret "^" and dollar "$" sign are both considered anchors with the caret referencing the beginning
	and the dollar sign the ending of the expression. If brackets “[“ or “]” (described later) are excluded it
	will give an exact match and is case sensitive. If we took the sentence:
							“How many sheep jumped over the fence?”
	and used the “^how” it would not provide a match, because the “H” is capitalized. “^How” would
	return a match. The same is true with the “$” as “$fence” would not return a match; whereas “fence?” would
	return a match.

### Quantifiers

	What quantifiers do is match the most occurrences of a particular pattern and can set a max and min number of characters to look for.
	An example is the "{ }" curly brackets set the min, max or number of times a pattern is matched.
		{ n } will match exactly n number of times.
		{ n, } will be at least n number of times.
		{ n, x } will be min n number of times up to a max of x.
		You can switch it from matching the max number of occurences to the fewest by using the quesiton mark ? symbol.
	
### Grouping Constructs

	If you need to have multiple search critiera and need to make your regular expression more complex you need to use parentheses "( )".
	This makes it so that you are able to have subsections or subexpressions and match parts of a string. An example is if you need to match
	an email address the regular expression would be ()@() with whatever search criteria (see below bracket expressions) you decide in the
	parentheses and the literal character @ inculded in the middle of the expression.

### Bracket Expressions

	Brackets "[ ]" are used to represent a range of characters.
		[a-z] will match lowercase letters
		[A-Z] uppercase letters
		[a-zA-Z] will return any letter and makes it not case sensitive.
		[0-9] numbers
		[!#$%&()*+,-./:;<=>?@[]^_~]] will match the special characters inbetween the brackets as an example.
		[^] will return the negative expression and return strings that do not match.


### Character Classes

	A character class is special notation that matches a character against a class that is choosen. A capital will inverse the class and give the opposite results.
		\d 	=> any number 0-9
		\w 	=> any letter in the alphabet a-z, number 0-9, and includes the underscore "_"
		\s 	=> a single white space (space, tab, enter, or other rare space between characters.)
		\t 	=> horizontal tab
		\r 	=> beginning of a line of text or carriage return
		\n 	=> enter or new line
		[\b]	=> backspace

### The OR Operator

	If you include the character "|" it functions as the word "or" does in a sentence. If I wanted to search for a phone number I could write the
	expression "[0-9](.|-)[0-9](.|-)[0-9]", which would return phone numbers in the 123.456.7890, 123-456-7890, 123.456-7890 or any combination of those
	formats.

### Flags

	There are only 6 of them in JavaScript:

		i => is case-insensitive
		g => all matches, without it – only the first match is returned.
		m => Multiline mode
		s => “dotall” mode, which allows a dot "." to match newline character "\n"
		u => full Unicode support.
		y => “Sticky” mode or search at that exact position in the text

### Character Escapes

	A backslash "\" makes it so that a character means exactly as read by a human and its plain meaning definition whereas without the backslash it would
	mean what is defined by the coding language choosen. An example is a * means to match a pattern zero of more times whereas a \* would mean the
	literal character "*".

## Author

	This was created by Scott Gauthier and you can find his github profile at https://github.com/Scott-Gauthier.
