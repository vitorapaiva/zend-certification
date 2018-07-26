#XML Basics

* Definition
	* XML is acronym for Extensible Markup Language
	* Data format ("Universal") used for structured document exchange

* Character encodings

	* Source Encoding:
		* Conducted at time of parsing
		* Cannot be changed during parser lifetime
		* Types:
			* UTF-8 (PHP uses this type of internal documentation representation; bytes up to 21)
			* US-ASCII (single byte)
			* ISO-8859-1 (single byte; default)
	* Target Enconding
		* Conducted at time of PHP Passing data to xml handlers
		* Target encoding initially set to same as source encoding
		* Can be changed at any time
	* Characters not capable of source encoding cause an error
	* Characters not capable of target encoding are demoted (to "?")