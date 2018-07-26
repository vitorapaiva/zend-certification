#DOM (REVISAR)

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