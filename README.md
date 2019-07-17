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
- `gr[ae]y`: match g followed by r, followed by either an e or an a followed by a y.
