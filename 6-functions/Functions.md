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

# Splat operator (REVISAR)

	* function myFunction($a,...$b) {}
	* $a contains the first paramter, $b is an array with all remaining parameters 
	* Also, sometimes, called "rest parameter"

# Return values
	* return statement ends function execution
	* will return values that include arrays,object, anonymous functions

# Variable scope
	* Variables declared within functions only visibile in that function
	* Variables declared outisde of functions are visibile everywhere outside of functions
	* Function using $globals array or "global" keyword

# Variable functions (REVISAR)
	* Parsed similar to variable variables
	* Variables followed by parentheses causes search for, and execution of, function with same name as variable evaluation
	* Commonly used for callbacks, function tables
	* Some use restrictions with common constructs
		* Ex: echo(), print()

# Anonymous functions (closures) (REVISAR)
	* Enable creation of functions without specifying a name
	* Implemented using the Closure class
	* Commonly used as param value for callback functions, or alternatively as variable values
	* To inherit variables from parent scope (function in which closure was declared), these variables must be declaed in the function header with the "use" keyword, or passing parameters in the call line
	* New closure type hint

# Type declarations (REVISAR)
	* Provide data type of parameter
	* function myFunction (int $a, string $b, bool ...$c){}
		* Allowed data types: int, string, bool, float, array, Anything callable, iterable <class name> (new pseudo type introduced in 7.1), <interface name>, nullable

	* Also possible to provide return types
		* function myFunction(float $a): int{}
		* void Return type if there is no return value

	* By default, values will be converted into the target data type

	* declare(strict_types=1) at the beginning of the PHP file enforces the target data type (otherwise a type error occurs)

	* Strict mode also includes enforcing of return types

	* Nullable (? symbol) types for parameters and return values since PHP 7.1: function myFunction (?int $a): ?string {}

	
