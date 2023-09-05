# REGEX for Common File types

Today We will be going over Regualr Expression to search through string and return results of files. Some examples may be `SampleSong.mp4`, `meme.jpg`, `Resume.docx`, or even `Regex-Tutorial.md`

## Summary

In order for us to properly find strings of file type, we must first go over the characteristics of the text format we are looking for. For our sample, lets break down this example:

`Example-file1.txt` 

using this regular expression:

`/^[A-Za-z0-9_-]+\.(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)$/`

Follow the Table of Contents below for a more in-depth explaination.

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

`/^`[A-Za-z0-9_-]+\\.(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)`$/`

* `^` and `$`: These are anchors that ensure the regex matches the entire string from start to finish.
* `^`: This is the start anchor. It signifies that the pattern should match from the start of the string.
* `$`: This is the end anchor. It signifies that the pattern should match until the end of the string.

### Quantifiers

/^[A-Za-z0-9_-]`+`\\.(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)$/

* `[A-Za-z0-9_-]+`: This part matches the base name of the file. It allows one or more alphanumeric characters, underscores, or hyphens in the base name. This should cover `Example-file1`.txt

* `+`: This Quantifier follows the character class `[A-Za-z0-9_-]` and means "one or more" of the preceding character class. It allows matching multiple alphanumeric characters, underscores, or hyphens in the base name. 

### Grouping Constructs

/^[A-Za-z0-9_-]+\.`(?:`jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md`)`$/

* `(?: ... )` that lists common file extensions you want to match. You can extend this list with other extensions as needed, separating them with | you can find a larger list of common file types [here](https://fileinfo.com/filetypes/common#:~:text=Common%20File%20Types.%20Common%20file%20extensions%20that%20are,Document.PAGES%3A%20Apple%20Pages%20Document.RTF%3A%20Rich%20Text%20Format%20File).

* `(?: ... )`: This is a non-capturing group. It groups the characters within it but doesn't capture them as separate groups. In this case, it groups the file extension "txt."

### Bracket Expressions

/^`[A-Za-z0-9_-]`+\\.(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)$/

* `[A-Za-z0-9_-]`: This is a character class or bracket expression. It matches any single character that is an uppercase letter (A-Z), a lowercase letter (a-z), a digit (0-9), underscore (_), or hyphen (-).

* Alternatively, you can also use `[\w-]` as a shorthand which matches any word character (letters, digits, or underscore), and the hyphen - is included separately to allow it in the base name.

### Character Classes

/^[A-Za-z0-9_-]+`\.`(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)$/

* `\.` : This character class specifies there is a ".". This should cover Example-file1`.`txt

* `[A-Za-z0-9_-]`: This character class matches one or more characters that fall into the following categories:

  * `A-Z`: Uppercase Letters
  * `a-z`: Lowercase Letters
  * `0-9`: Digits (0-9)
  * `_` & `-` : the underscore and hypen characters

* `(?:jpg|jpeg| ...)` : each string such as `jpg` are specific character classes that are exact matches to the given string. For our example file name, this should cover Example-file1.`txt`

### The OR Operator

/^[A-Za-z0-9_-]+\\.(?:jpg`|`jpeg`|`png`|`gif`|`mp4`|`mp3`|`pdf`|`doc`|`docx`|`txt`|`md)$/

* `|`: The pipe character is used as the OR operator within the non-capturing group. It will split the group into multiple correct results. 

### Character Escapes

/^[A-Za-z0-9_-]+`\.`(?:jpg|jpeg|png|gif|mp4|mp3|pdf|doc|docx|txt|md)$/

* `\.` : This will match a literal dot '.' in your regex pattern by using a '\\' before a special character 


## Author

If you have any questions about the repo, please open an issue report or contact me directly at w.andrew.loverde@gmail.com. You can explore more of my work at [wloverde](https://github.com/wloverde/).
