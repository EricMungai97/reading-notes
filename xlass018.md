# Regular Expressions

[Source](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)

Regex is a sequence of characters used to check whether a pattern exists in a given text(string) or not.

Regex is uses include:

1. Validating the format of email addresses.

2. used for parsing text data files to find, replace or delete certain strings.

To use regex you have to import the regex inbuilt standard library.

`re.macth` returns a match object if the text matches the pattern otherwise it returns none.

example

```
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")
```
the `r` at the start of the pattern is called a raw string literal. 

Its purpose is to change how the string literal is interpreted.

`\w `- Lowercase 'w'. Matches any single letter, digit, or underscore.

`\W` - Uppercase 'W'. Matches any character not part of \w (lowercase w).

`\s` - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.

`\S` - Uppercase 'S'. Matches any character not part of \s (lowercase s).

`\d` - Lowercase d. Matches decimal digit 0-9.

`\D` - Uppercase d. Matches any character that is not a decimal digit.

`\t` - Lowercase t. Matches tab.

`\n` - Lowercase n. Matches newline.

`\r` - Lowercase r. Matches return.

`\A` - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.

`\Z` - Uppercase z. Matches only at the end of the string.

`\b` - Lowercase b. Matches only the beginning or end of the word.

`+` - Checks if the preceding character appears one or more times starting from that position.

`*` - Checks if the preceding character appears zero or more times starting from that position.

`?` - Checks if the preceding character appears exactly zero or one time starting from that position.

`{x}` - Repeat exactly x number of times.

`{x,}` - Repeat at least x times or more.

`{x, y}` - Repeat at least x times but no more than y times.

Example code 
```
re.search(r'\d{9,10}', '0987654321').group()
output #'0987654321'
```

The + and * qualifiers are said to be greedy.

`{ }`	Checks for an explicit number of times.

`( )`	Creates a group when performing matches.

`< >`	Creates a named group when performing matches.

`findall()`	Returns a list containing all matches

`search()`	Returns a Match object if there is a match anywhere in the string

`group` returns a string matched by the re

`split()`	Returns a list where the string has been split at each match

`sub()`	Replaces one or many matches with a string

## Shutil

[Source](https://pymotw.com/3/shutil/)

The shutil module includes high-level file operations such as copying and archiving.

`copyfile()` copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.

 To copy a directory from one place to another, use `copytree()`. It recurses through the source directory tree, copying files to the destination.
 
To move a file or directory from one place to another, use `move().`

The `which()` function scans a search path looking for a named file.

Use `make_archive()` to create a new archive file

Extract the archive with `unpack_archive()`

## Things I want to know more about

I need to delve deeper on how to use Shutil methods.

Watchdog Library methods

