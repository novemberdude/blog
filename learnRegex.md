# 1. Basic Concepts of String Manipulation

### Introduction to string manipulation

+ String manipulation vs String formatting

### String operations

### Finding and replacing

+ search target string for a specified substring
	`string.find(substring, [start, end])` --> return the lowest index in the string, if none return -1
	`string.index` if none raise value exception, 
	`string.count`, 
	`string.replace(old,new[,count])` 

# 2. Formatting Strings

### Positional formatting
- What is string formatting?
+ also call String interpolation
+ Insert a custom string or variable in predefined text:
- Methods for formatting
+ Positional formatting: x = 'this is a string {} {2}'; x.format
+ Formatted string literals
+ template method
- Formatting datetime
	`from datetime import datetime
	print(datetime.now())`

	message = "Good morning. Today is {today:%B %d, %Y}. It's {today:%H:%M} ... time to work!"
	print(message.format(today=get_date))

	ký hiệu: %d(day), %B (monthname), %m (monthnumber), %Y(year), %H (hour) and %M(minutes)

### Formatted string literal
+ f-strings
+ type conversion
	!s (string version)/ !r (string containing a printable representation, e.e. with quotes)/ !a (some as !r but escape the non-ASCII characters)
+ format specifiers:
	e (scientific notation), d (digit), f (float)
	vd. {number:.2f}
	my_today = datetime.now()
	{my_today:%B %d, %Y}

### Template strings

# 3. REGular EXpressions for Pattern Matching
`String containing a combination of normal characters and special metacharacters that describes patterns to find text or positions within a text`

+ The re module
  -> re.findall(r'regex', string)
  -> split string at each match: re.split(r'regex', string)
  -> replace one or many matches with a string: re.sub(r'regex',new,string)
  suported metacharacter: \d, \D, \w, \W, \s, \S --> nên dùng \s khi pattern có space (The difference is that specifically matches a space, while \s will match any whitespace character (\r, \n, \t, \f and \v).)

### Repetitions
