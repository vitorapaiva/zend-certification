#SOAP (REVISAR)

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

