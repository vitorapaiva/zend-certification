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
	* Use the substr(string, start, length) fu