#Json & Ajax (REVISAR)

* Definition
	* Json is an acronym for javascript object notation
	* Data-interchange format
	* Extenson loaded in PHP by default

* Set of predefined constants available
	* Available when dynamically loaded at runtime or them compiled into PHP
	* Partial List
		JSON_ERROR_NONE Confirms whether error occurred or not
		JSON_ERROR_SYNTAX indicates syntax error JSON_ERROR_UTF8 aids in detecting encoding issues
		JSON_FORCE_OBJECT aids in ensuring the receiving end gets an object when an empty array is passed
* Functions
	* Decodes a json strings 
		json_decode($json,$assoc=false,$depth=512,$options=0)
	* Returns the json representations of a value
		json_encode($value,$options=0,$depth=512)
	where

	$assoc: Indicates whether objects should be converted into associative arrays(boolean)
	$value: can be of any type except a resource
	$depth: nesting depth
	$options: decoding options
	
