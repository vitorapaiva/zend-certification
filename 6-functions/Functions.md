# Function definition
	* Blocks of code that execute in isolation (and local scope), performing an action
	* Functions names are case-insensitive when defined in global scope
	* Can be referenced before defined unless function conditional
	* Types: built-in (PHP supplied); user-defined; externally provided

# Declaring functions
	* Return values and parameters are optional, parameters may be assgined default values; Since PHP 7.1, new void functions and methods are possible. Set param default to avoid Error exception
		* Ex:
			function myFunction($p) {
				// do something
				return $p;
			}
			$x = myFunction("ABC"); //$x == "ABC"
			$x = myFunction(); //Error exception thrown
		* Ex:
			function myFunction($p="ABC"){
				// do something
				return $p;
			}
			$x = myFunction("DEF"); //$x == "DEF"
			$x = myFunction(); //$x == "ABC"

# Function arguments (REVISAR)
	func_num_args() number of parameters
	func_get_arg(nr) paramater number "NR"s (starting at 0)
	func_get_args() All parameters as an array

* Argument list is a set of comma-delimited expressions
* Can pass arguments in several ways
	* By value (default)
		* Creates copy: argument changes extend only within function
	* By reference (REVISAR)
		* Use "&" to supply parameter by reference
		* Call time pass reference not allowed any more
			* By default, argument values (parameters)
			* Changes to any reference affects all references