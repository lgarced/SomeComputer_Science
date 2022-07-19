Regex Tutorial on Matching a URL


![alt text](./Assets/computerscience)


Regular expressions, per definition, are a series of special characters that define a search pattern. Always defined in a string, they can be used to find and replace sequence characters and validate inputs.
Summary
In this tutorial I'll be decribing how the regex for matching a URL works. The key topics that will be reflected on are the Anchors, Quantifiers, Grouping Constructs, Bracket Expressions, Character Classes, The OR Operator, Flags, and Character Escapes.
Regex for Matching a URL : /^(https?://)?([\da-z.-]+).([a-z.]{2,6})([/\w .-])/?$/.

🟦 Table of Contents
    🟪	Anchors
    🟪	Quantifiers
    🟪	Grouping Constructs
    🟪  Bracket Expressions
    🟪  Character Classes
    🟪  The OR Operator
    🟪  Flags
    🟪  Character Escapes

🟦 Regex Components

      ⏹ Anchors

    The anchors used to contain this regular expression are: ^ to start, and $to finish.
    For our expression the start is looking for an http://

      ⏹ Quantifiers

    Quantifiers set the limits of the string that your regex can match too. They frequently include the minimum and maximum number of characters that your  regex is looking for.
    In this regex the quantifiers are ? after the s that in the first grouping, which is saying there may be 1 or 0 s after the http, + inside the second  grouping, which is saying at least one or more of the characters in [\da-z\.-] may be present, {2,6} inside the third grouping, which matches the pattern from a minimum of 2 and a maximum of 6 number of times, and * inside the forth grouping, which is saying [\/\w \.-] may come up zero or more times

      ⏹ Grouping Constructs

    The primary way you group a section of a regex is by using parentheses (). Breaking up the regex helps fulfil more complicated regex to check multiple parts of a string.
    In this expression there are four brackets: (https?:\/\/), ([\da-z\.-]+), ([a-z\.]{2,6}), ([\/\w \.-]*)

     ⏹ Bracket Expressions

    Anything inside the set of square brackets [] represents a range of characters that needs to be matched. These Bracket Expressions are also known as Positive Character Groups because they outline the character we want to include.
    This regex includes multiple Bracket Expressions, an example of one would be [\da-z\.-] in the second grouping or [a-z\.] in the third grouping. The   [a-z\.] expression is saying to included anything from a-z and add a . add the end.

Character Classes
Character classes are used to define character in regex which can occur in an input string to fulfil a match. Bracket expressions are a character class frequently used to define positive or negative character groups.
In our URL matching regex, ([\da-z\.-]+) we are using the character class /d to find any digit
OR Operator
In Bracket Expressions you are not required to meet all of the requirements in the pattern. This means that [a-z.] searches alphabetically for characters or one special character included in the pattern.
If you want to add the same effect to a grouping with () you use the OR operator |. For example [abc] and (a|b|c) are the same thing

Flags

In our example the regex is wrapped in slash characters. In most instances this is the proper look of a regex, but the one exception is flags. Flags are placed at the end of a regex to define additional functionality or limits inside the regex. The most common forms of flags are: g (Global search: the regex should be tested against all possible matches in a string), i (Case-insensitive search: case should be ignored while attempting a match in a string), and m (Multi-line search: a multi-line input string should be treated as multiple lines).
For example, /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/ will capture a url as a string by itself www.example.com. While /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/i can capture www.example.com and www.Example.com

Character Escapes

The backslash \ in a regex escapes a character that would be interpreted literally. For example, the open curly brace { is used to begin a quantifier, but adding a backslash before the open curly brace { means that the regex should look for the open curly brace character instead of beginning to define a quantifier.
In our regex example, the \/\/ in the first grouping is add // in front of http(s)
