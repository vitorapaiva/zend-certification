#Strings & Patterns
 
## Delimited by single or double quotes
	* Double quotes offer more options, including special characters

## Heredoc Syntax (REVISAR)
	* Delimits strings without using quotes (so no need to escape)
	* Start with <<< and an identifier; end wit the same identifier
	* Do not indent ending identifier or add any char

## Nowdoc syntax (REVISAR)
	* Similar to heredoc, but no parsing is conducted
	* Same <<< identifier, but the identifier must be enclosed in single quotes

## Substrings
	* Use the substr(string, start, length) function
	* Return a substring of the given string

## Locating strings:
	* Use the strpos(haystack, needle, offset) function
	* Searches the string, starting at the beginning (or the position (offset) indicated), and return the position of the first occurrence, or returns false if not 

## Comparing strings:

== Sets up comparison, including data type conversion
=== Sets up comparison, including data type check
strcasecmp() case-insensitive comparison
strcmp case-sensitive comparison
similar_text("firstString","secondString") similarity of two strings, returns the number of matching chars
levenshtein("cat","can") //1 levenshtein distance between strings. Defined as minimum number of chars needed to replace, insert or delete to transform string 1 into string 2

## Counting Strings:
	* number of characters use the strlen(String) function
	* number of words use str_word_count(string). str_word_count(string, true) yields an array with all single words

## Phonetic functions (REVISAR)
	soundex() soundex value of a string
	metaphone() metaphone key of a string. Based on english pronunciation rules, so more precision than the soundex() function but of limited use with global sites

## Strings and arrays:
	explode(split string, string) converts a string into array
	implode(glue string, string) converts an array into a string

## Formatting output (REVISAR)
	printf() prints a formatted string
	sprintf() returns a formatted string
	vprintf() prints a formatted string, placeholder values supplied as an array
	vsprint() returns a formatted string, placeholder values supplied as an array
	fprintf() send a formatted string to a resource

## Formatting characters (REVISAR)
	%b (binary)
	%d (decimal)
	%f (float)
	%o (octal)
	%e (scientific notation)
	%s (string)
	%nd (N is the number of digits)
	%.nf (n is the number of decimal places)

## Regular Expressions (REVISAR)
	* Describe a pattern
	* PCRE (Perl Compatible regular expression)
	* Del*imiter
		* Usually "/","#" or "!"
		* Used at beginning and end of each pattern
	* Literals are any characters
	* Boundaries (Examples)
		^ Start of a line
		$ End of a line
		\A start of a string
		\Z end of a string
	* Character classes delimited with []
		* Built-in character classes; capitalization indicates absence (Example)
			\d digit
			\D no digit
	* "Greediness"
		* Maximum match is returned
		* Usually need to use parentheses with alternatives
	* Quantifiers (Examples)
		* Any number of times
		+ Any number of times, but at least once
		? 0 or 1
		Combination of ? with * or + makes non-greedy
	* Pattern matching
		* Use the preg_match(pattern,string) function
		* Returns number of matches
		* Optional third param defines match
		* preg_match_all() returns all matches
		* Returns all matches in an array
	* Replacing
		preg_replace(search pattern, replace pattern, string)

## Encodings (REVISAR)
	* Some language character sets can be represented with singlebyte encodings (based on 8-bit values; ex: latin-based languages) and others require multibyte encodings because of their complexity (ex: chinese logographic character set)

	* Operating with strings in multibyte encoding requires using special functions (mbstring extension) or the characters will display incorrectly

	* Existing applications built in a singlebyte environment, that utilize functions like substr() and strlen(), will not work properly in multibyte environments

	* Need to employ function overloading, to convert singlebyte function awareness to a multibyte equivalent, such as mb_substr() and mb_strlen()

	* mstring Module
		* Handles character encoding conversion
		* Designed for unicode-based (UTF-8,UCS-2) and some single-byte encodings (php manual has complete list)
		* Module must be enabled using the configure option (not a default extension)
		* Mb_check_encoding() will verify whether the string is valid for the specified encoding