# Learning RegEx 

### Resources
[RegEx Blog](http://web.archive.org/web/20091217101142/http://immike.net/blog/2007/04/06/the-absolute-bare-minimum-every-programmer-should-know-about-regular-expressions/)

### Metachars
`^[]().*?\|+$` and sometimes `-`
### Line anchors `^` and `$`
The `^` and `$` metachars. represent the start and end of a line of text
- `^`: beginning of text
- `$`: end of text

### Examples
- `^mike`: will match lines that start with `mike`
- `mike$`: will match lines that end with `mike`
- `^mike$`: will match lines that contain only the word `mike`
- `^$`: will match empty lines

### Charcter Class: `[]`
Square brackets, called `character class` let you matcg any one of several characters. Supposed you want to match the word `gray`, but also want to find it if it was spelled `grey`. A character class will allow you to match either:
#### Example
- `gr[ae]y`: match g followed by r, followed by either an e or an a followed by a y.

If you use `[^...]` instead of `[...]` the result will be a `regex` that matches a char class that does not include the chars followed by the `^` which is interesting because the `^` has a different result then using it outside of a `character class` which would match at the begining of the line.

### Character Class Metacharacter: `-`
Within a `character class` the character `-` indicates a range of chars. Instead of `[0123456789ABCDEF]` we can write `[0-9a-fA-F]`. The `-` is only a metachar only within a `character class`. 
#### Exception: When the `-` metachar. is the first char used in a `character class` it is not considered a metachar.

### Matching any character with: `.`
The `.` metachar is shorthand for a char class that matches any char. It is very convenient when you want to match  any char at a particular position in a string. 
#### Exception: When the `.` is inside a `character class` it is not a meta char.

### Alternation Metacharacter: `|`
The `|` metacharacter means "or". It allows combining multiple expressions into a single one that matches any of the individual ones. The subexpressions are calles `alternatives`.
#### Examples:
- `Mike|Michael`: this would match `Mike` and `Michael`

### Matching optional items: `?`
The `?` metacharacter means `optional`. It is placed after a char. that is allowed, but not required, at a certain point in an expression. The question mark attaches only to the immediate preceding char.
#### Example:
- `flavou?r`: this will match every letter but has a conditional `u` 

### Quantifiers: `+` and `*`
Like the question mark the `+` and `*` metachars. affect the number of times the preceeding char can appear in the expression. The metachar `+` matches one or more immediately preceding item, while `*` matches any number og the preceding item, including 0
#### Example:
- `go+al`: will match goal and goooooooooooooal but not gal
Name quantifiers (`?+*`) because they influence the quantity of the item they are attached to.

### Interval Quantifier: `{}`
The `{min, max}` metasequence allows you to specify the number of times a particular item can be matched by providing your own `min` and `max`.
#### Example:
- `go{1,5}al`: matches the goal string with up to 5 goals. The sequence `{0,1}` is the same as `?`

### Escape Character: `\`
The `\` metachar. is used to escape metachars. that have special meaning so you can match in patterns. For example, if you would like to match `?` or `\` chars you can precede with a `\`, which removes their meaning `\\` or `\?`

### Parenthesis for matching: `()`
Most RegEx tools will allow you to capture a particular subset of an expression with parens. 
#### Example:
- `http://([^/]+)`
    - begining of the RegEx matches up to `http://`
    - the rest of the expression matches the character up to a `/`: `http://blog.com/blogpost1/image` would only match `http://blog.com`


