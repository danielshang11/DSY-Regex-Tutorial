# Regex Tutorial - Matching a URL
## Summary

This gist tutorial is trying to explain how we match a URL using regular expression
 ![exp](https://cms-assets.tutsplus.com/cdn-cgi/image/width=850/uploads/users/1251/posts/93367/image-upload/url_regex_check.jpg)
- Pattern:
````
 /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
 ```` 
 It's a good way when users need to validate a URL which is in the applications such as nodejs.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Back-references](#back-references)
- [Author](#author)

## Regex Components

### Anchors
- `^` and `$` indicate the start and end of the string respectively.
- `^` anchor will indicate the first character of the regex string pattern.
    - If it's starting `^Apple` then `"Apple pie"` and `"Apple"` would match
    - However, `"apple"` and `"apple pie"` won't match
- `$` anchor will indicate the end character of the regex string pattern.
- In the case below:
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```
1. `^` anchor indicates the `h` in `https` preceding the `https` is the beginning of the pattern string. If the `h` in `https` were missing, ex: `ttps`, the regex would not function
2. `$` anchor is the end of the string and line, so any additional trailing white spaces or other characters are ignored.
### Quantifiers
- `+`,`*`,`?`and `{n}` are considered as quantifier symbols
- The `+` quantifier matches the preceding element one or more times.
    - For example:
```
abc+        matches a string that has ab followed by one or more c
```
- The `*` quantifier matches the preceding element zero or more times.
    - For example:
```
abc*        matches a string that has ab followed by zero or more c
a(bc)*      matches a string that has a followed by zero or more copies of the sequence bc
```
- The `?` quantifier matches the preceding element zero or one time.
    - For example:
```
abc?        matches a string that has ab followed by zero or one c
```
- The `{}` Curly brackets can provide three different ways to set limits for a match:
    - `{n}` Matches the pattern exactly n number of times
    - `{n,}` Matches the pattern at least n number of times
    - `{n,x}` Matches the pattern from a minimum of n number of times to a maximum of x number of times
    - For example:
```
abc{2}      matches a string that has ab followed by 2 c
abc{2,}     matches a string that has ab followed by 2 or more c
abc{2,6}    matches a string that has ab followed by 2 up to 6 c
a(bc){2,6}  matches a string that has a followed by 2 up to 6 copies of the sequence bc
```
### OR Operator
- `|` or `[]` is considered as OR Operators Symbols.
- There is an Example:
```
a(b|c)     matches a string that has a followed by b or c (and captures b or c)
a[bc]      same as (b|c), but without capturing b or c
```

### Character Classes
- `.`,`\d`,`\w`,`\s` those are some of the character classes
- Inside the pattern we can find `\d`,`\w` and `.`
````
 /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
 ```` 
- `.` Matches any character except the newline character (\n), `.`is a wildcard for any character, unless preceded by a backwards slash `\.`, then it's a required dot.
    - inside the pattern, `\.` refers to a required dot
- `\d` Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9]. `\d` allows the domain name to contain digits

- `\w` Matches any alphanumeric character from the basic Latin alphabet, including the underscore `(_)`. This class is equivalent to the bracket expression [A-Za-z0-9_].

- `\s` Matches a single whitespace character, including tabs and line breaks


### Grouping and Capturing
- Inside the pattern we can find 
    
````
 /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
````
1. `[]` is the symbol thatis under grouping and capturing
2. `[a-z\.]` in the third grouping allows for any lowercase alphabetic characters from a through z, appended by a dot. 
### Bracket Expressions
- We had given an example in [Quantifiers](#quantifiers)
- `[]` is the symbol
- `[abc]` means it's either a ,b, or c
- `[a-c]` same as `[abc]`or we can do `(a|b|c)`
- Inside the pattern we can find 
    - `[a-z\.]` in the third grouping allows for any lowercase alphabetic characters from a through z, appended by a dot.
````
 /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```` 


### Greedy and Lazy Match
- Greedy and Lazy Match contains 3 symbols which are `*`, `+`, and `{}`
- Inside the pattern we can find 
    - the second grouping ([\da-z\.-]+) the `+` operator is greedy as it allows character matching from one to an infinite amount of times.
````
 /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```` 


### Back-references
https://code.tutsplus.com/tutorials/8-regular-expressions-you-should-know--net-6149
https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
https://regexr.com/
## Author

[Daniel's Github Link](https://github.com/danielshang11)

