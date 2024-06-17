# Match Hex
 1. How to match Hex values in pattern?
	--pattern "|FE 00 86 11|"
	
	2. How to match Hex values with PCRE?
	--pcre "/\x2e\x2e\x2f/"
	
	3. Match one character
	--pcre "/[abc]/"
	
	4. Match a group of characters
	--pcre "/(abc|hello|ninja)/"
	
	5. Negative Match: String not starting with Java
	-- pcre "/^(?!java)/"

# Negative Match
	1. Caret (^) Symbol
	e.g. [^0-9]: any character that is not a digit
	
	2. Negative lookaheads: specify a pattern that should not be present after the current position
	Syntax: (?!pattern)
	e.g., -- pcre "/^(?!java)/"
	
	3. Pipe (|) symbol: Specify multiple patterns by the pipe symbol, allowing you to match any pattern except the ones specified
e.g. ^(?!dog$ | cat$): match any word not dog or cat
