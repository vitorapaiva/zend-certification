#SIMPLEXML (REVISAR)

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


