# 1 - XML Basics

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

# 2 - XML Extension

* Extension allows for parsing of XML Documents
* Create XML Parsers (+Params) and define corresponding handlers (REVISAR)
	xml_parser_create() ... AND ...
	xml_parser_create_ns() For Parser with namespace support
	xml_set_element_handler()	See other functions in PHP Manual

#3 - SIMPLEXML (REVISAR)

* Requires the LIBXML extension (enabled by default in php) 
	* Functions part of expat library also enabled by default
* Set of predefined error code constants available
	* Available when dynamically loaded at runtime or when compiled into php
	* Partial List
		XML_ERROR_**
			_SYNTAX
			_INVALID_TOKEN
			_UNKNOWN_ENCODING
		XML_OPTION_**
			_OPTION CASE FOLDING
				_SKIP_WHITE
* Definition
	* "Simple" access to xml data from PHP

* Concept: OOP access for XML data
	* Elements become object properties
	* Attributes can be accessed via associative arrays

* Functions:
	$xml = simplexml_load_string('<?xml...');
	$xml = simplexml_load_file('file.xml');
	$xml = new SimpleXMLElement('<?xml...');

* Class: (Examples)
	Creates a SimpleXMLElement Object
		SimpleXMLElement::construct()
	Identifies an element's attributes
		SimpleXMLElement::attributes()
	Retrivies an element's name
		SimpleXMLElement::getName()
	Finds children of given node
		SimpleXMLElement::children()
	Counts the number of children of an element
		SimpleXMLElement::count()
	Returns a well-formed XML String Based on a SimpleXML Element
		SimpleXMLElement::asXML()
	Runs an Xpath query on the current node
		SimpleXMLElement::xpath()

#4 - DOM (REVISAR)

* Definition
	* DOM extensions permits manipulating of XML documents with its API and PHP
* Requires the libxml extension (enable by default in PHP)
	* Functions part of expat library also enabled by default
* Encoding:
	* Uses UTF-8 encoding
* SimpleXML and DOm
	* simple_xml_import_dom() converts a dom node into a SimpleXML Object
* Set of predefined constants available
	* Available when extension dynamically loaded at runtime or when compiled into php
	* Partial list (see PHP manual for full list)
		xml_element_node Defines node as a DOM element
		xml_text_node Defines node as a DOMText

#5 - SOAP (REVISAR)

* Definition
	* Derived acronym for Simple Object Access Protocol
	* Versions 1.0 and 1.1 released by the industry; popularity led to control by W3C with version 1.2
	* Extension used to write SOAP servers and clients

* Requires the LIBXML extension (enabled by default in PHP)

* Runtime configuration
	* SOAP cache functions are affected by php.ini settings (soap.wsdl_cache_*)

* Set of predefined constants available
	* Available when dynamically loaded at runtime or when compiled into php
	* Partial List (all integers)
		SOAP_1_1 1
		SOAP_1_2 2
		SOAP_ENCONDED 1
		SOAP_LITERAL 2
		SOAP_AUTHENTICATION_ 0/1
		SOAP_ENC_* 		300/301
		SOAP_CACHE_*	0/1/2/3
		SOAP_PERSISTENCE_* 1/2
		SOAP_RPC 1
* SOAP Functions
	is_soap_fault Checks if a SOAP call has failed
	use_soap_error_handles Indicates whether to use an error handler

#6 - REST

* Definition
	* Rest is acronym for Representational State Transfer
	* Design standard (not an extension); set of 4 architectural principles for designing web pages and services
		* Stateless
		* Exposes URIs
		* Can transfer any format, for example, XML, JSON, or both
* Data types supported include:
	* Ascii strings
	* Integers
	* Booleans
	* Scalars
* REST uses HTTP "verbs"
	GET List (without identifier)
	GET Resource(with identifier)
	POST Create
	PUT  Update(with identifier)
	DELETE Delete(with identifier)
* Rest and request heards
	* Two Concepts
		CONTENT-TYPE: what is being provided
		ACCEPT: what is expected in response
	* Status codes:
		201 = created
		400 = Bad Request / Failed validation
		401 = Unauthorized
		204 = No Content (useful with delete)
		500 = Aplication error
	* ext/curl is a common way of sending more complex header request from a PHP script
* Context switching
	* Refers to the act of providing different output based on criteria from the request
	* The process inspects the HTTP request heards and/or the request URI, and varies the response appropriately
	* Commonly used for:
		* Providing different output for requests originated via XMLHttpRequest
		* Providing different output for requests originated via XMLHttpRequest
		* Providing different output based on accept HTTP headers (ex: rest endpoints)
		* Providing alternate layouts/contents based on browser detection

#7 - Json & Ajax (REVISAR)

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

#8 - Date & Time

* Definition
	* Functions that retrieve the date and time from the PHP Server
	* Flexbile Date and Time formatting due to the fact that they are stored as a 64-bit number
	* Functions values reflect locale set on server, as well as special date adjustments like daylight savings, time, leap year
* Runtime configuration
	* date.* Functions are affected by php.ini settings
	* date.default_latitude; date.timezone
* Set of predefined constants available
	* DateTime constants provide standard date formats, in conjunction with a date functione like date()
* DateTime Class (REVISAR)
	* Constants: format(Examples)
		const string DateTime::*
		::COOKIE = 1, d-M-y H:i:s T; Monday, 14-AUG-17 15:52:01 UTC
		::RSS = D, d M Y H:i:s O; MON, 14 AUG 2017 15:52:01+0000
	* Methods: Format(Examples)
		public __construct([[string $time="now", DateTimeZone $timezone = NULL]])

		public DateTime add(DateInterval $interval)

		public DateTime setDate (int $year, int $month, int $day)

	* Static methods: format (OOP-Styles Examples)
		Add a specified amount of time to a datetime object
			public DateTime DateTime::add(DateInterval $interval)
		Return a new datetime object (instantion)
			public DateTime::__construct()([[string $time="now", DateTimeZone $timezone = NULL]])
		Return a datetime object in a specific format
			public static DateTime DateTime::createFromFormat(string $format, string $time [, DateTimeZone $timezone])
		Return a date formatted according to a given format
			public string DateTime::format(string $format)
		Return the difference between two datetime objects
			public DateInterval DateTime::diff(DateTime $datetime2, bool $absolute = false])	public DateTime
		Return the unix timestamp
			public int DateTime::getTimestamp(void)
		Alter the current timestamp
			public DateTime DateTime::modify(string $modify)
	* Each case, the method returns an object on success, false on failure
		$timezone: when set to null, returns the current time
		$format: the parameter must be in a format accepted by date()
		$modify: Date/time string in valid formats (add/subtract)
