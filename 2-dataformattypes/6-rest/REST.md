#REST

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
