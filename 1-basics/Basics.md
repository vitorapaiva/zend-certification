# 1 - Syntax

## Punctuation
	* Terminate code statements with a semi-colon (;)
	* Use appropriate tags

## TAGS

### Opening
	*<?php
	*<?= (short for <?php echo)
## Closing
	*?>
	*?>

## Comments
	//Used for a single comment line
	//Must be repeated for multiple lines
	
	/* and */ are used to delineate a comment block
	
	/* used once at beginning
	used once at the end */

# 2 - Operators

## Arithmetic operators

	* Basic calculations
		* + (adding)
		* - (substracting)
		* * (multiplying)
		* / (dividing)
	* Modulus (remainder when dividing)
		** Ex: $m = 5%2; // $m == 1

## Bitwise operators (REVISAR)
	
	* Use to work with bits withing an integer; arithmetic
	* Integral Numbers are internally converted into bits
		**Ex: 5 -> 0101 = 0*8 + 1*4 + 0*2 + 1*1
	* $a & $b equivalent to 'AND': matching "1" in both operands
	* $a | $b equivalent to OR: at least one "1" in an operand
	* $a ^ $b equivalent to XOR: true only if operands are diferent
	* $a << $b Shift bits from $a by $b times
		** Ex: 4 << 2 == 16 (each step meaning multiply by two)
	* $a >> $b Shift bits from $a by $b times
		** Ex: 4 >> 2 == 1 (each step meaning divide by two)
	* ~$a (NOT) convert 0s into 1s ; 1s into 0s
		** Ex: ~11==-12

## Assingment Operators
	* Assign (=)
		* When using arrays, assign value to keys with =>
	* Short forms (combined)
		* Assignment (+ and operator)
			Works with operators: - * / & | ^ >> <<
			Ex: $a += 1; is short-hand for $a = $a + 1;
		* Combined/concatenating assingment (.=)
			Ex: $a = "Hello,";
			    $a.= "World !"; ...results in "hello, world!"
	* Increase / decrease (++ --) 
		* Placement important: in front of expression - increased or descrease first; after expression, the reverse
			Ex:
			$a=0;
			$b=0;
			echo ++$a; //(result 1)
			echo $b++; //(result 0)
			
## Comparison operators
	* Value Equality (==)		Value Inequality (!=)
	Php handles data type conversion "123" == 123
	* Value/type equality (===)			Value/type inequality(!==)
		* Compares value with a type check. PHP checks the data type "123" !== 123
	* Greater than (>) 	Less than (<)
	* Grater or equal (>=)	Less than or equal (<=)
 
## String operators
	* Concatenate (.) and concatenating assingment (.=) see above

## Array operators
	+ union
	== equal
	=== identical
	!= not equal
	<> not equal
	!== not identical

## Logical operators

	Example		Operator	Evaluates as true when
	$a and $b	and		Both $a and $b true
	$a or $b	or		Either $a or $b true
	$a xor $b	xor		Either $a,$b true; not both
	! $a		not		$a not true
	$a && $b	and		both $a and $b true
	$a || $b	or		either $a or $b true
	$a ^  $b    xor 	either $a,$b true;not both

## Execution operators
	* use backticks `` to execute the contents enclosed by them as a shell command, equivalent to shell_exec()

## Operator precedence
	* follows mathematical precedence in most instances (Ex: multiplication/division precedes addition/subtractions)
	* use parentheses to enforce non-standard precedence

# 3 - Variables

## Naming
* Start with a "$"
* Can contain letters, numbers, and underscores
* Must start with letter or underscore and by convention should start with lower case letter or underscore
* Case-sensitive

## Referencing
* Variables can be assigned by value or by reference
* The ampersand (&) creates a reference, or alias, and causes both the original variable and alias to point to the same memory value
	Ex:
		$a=10;
		$b=&$a;
		echo $a.'<br>'; //(10)
		echo $b.'<br>'; //(10)
		$a=12;
		echo $a.'<br>'; //(12)
		echo $b.'<br>'; //(12)

## Initializing
* Variables typing is set automacatically by the PHP parser and called "Type juggling/coercion"
* Initializing variables empty is a good practice if it is possible it already points to memory values and you want to start empty
* The function isset() returns a boolean on a passed variable containing a value other than null string, null or zero

# 4 - Control Structures

## Conditions

* IF
	* Evaluates for a condition (boolean value), to determine whether to execute code; can be nested
* ELSE
	* Provides alternative execution, when combined with IF(=FALSE)
* ELSEIF(ELSE IF)
	* Provides alternative execution, when combined with IF (=FALSE), but its own condition must be met (FLOW: IF...ELSEIF...ELSE)
* IF-ELSE(TERNARY OPERATOR)
	* Common assignment form:
		* $foo = <expression> ? <value if true> : <value if false>;
* TERNARY OPERATOR, SHORT FORM
	* Shorthand assignment form: raises an E_NOTICE if no value and therefore not recommended
	* $FOO = <EXPRESSION> ?: <VALUE IF FALSE>;
* Null coalesce operator (REVISAR)
	* Null coalescing assignment form: No E_NOTICE if no value (best pratice)
	* $foo = <expression> ?? <value if false>;
* Spaceship operator, short form
	* A <=> B
	* Return 1 if A > B, -1 if B > A, 0 if A == B
* SWITCH
	* Use to evaluate (Boolean Value) against a series of conditions, to determine which code to execute for each condition

## Loops

* WHILE
	* Executes statement until condition is no longe evaluated as boolean true; condition evaluated at beginning

* DO-WHILE - (REVISAR)
	* Executed statement until condition is no longer evaluated as boolean true; condition evaluated at end

* FOR
	* Has three statements in parentheses, executes first statement as a one time assignment. Iteration continues while the second statement (a loop condition) is no longer evaluated as boolean true. Third statement is executed at the end of each iteration

* FOREACH - REVISAR sintaxes do foreache
	* Used only for arrays; assigns value of current element to the variable and advances the array pointer util it reaches the last element

* CONTINUE
	* Within loops, used to skip subsequent code within the iteration and jump to the next condition evaluation step

* BREAK
	* Halts execution of loops utilizing the for, foreach, while, do-while, switch control structures

# 5 - Language Constructs

## Output Constructs

* die() and exit()
	* These constructs are equivalent. Used to output a result and then terminate the running script

* echo()
	* Used to output a scalar (string, float, boolean, int) value. If using strings containing quotations, make sure you handle them correctly (use apostrophe or escape with \)

* return()
	* Used to halt execution of a function (called within function) or of a script (called within global scope)

* print()
	* Used to output a scalar value

## Evaluation Constructs

* empty()
	* Returns boolean true on an empty value passed in: a no element array, 0, 0.0 ...

* eval() (REVISAR)
	* Used to evaluate the contents of a string as php code

* include and include_once()  (REVISAR)
	* Used to both include and evaluate a file

* require() and require_once()  - (REVISAR)
	* These constructs are similar to include() and include_once(), except that a failure in execution results in a fatal error, while include() generates a warning

## Other Constructs

* isset()
	* Use to determine whether a variable has been set (therefore is not null)

* unset()
	* Use to unset the variable

* list() 
	* Common use:
		Assign a list of variables by destructuring array values
			$info = array('coffee', 'brown', 'caffeine');
			//Listing all the variables
			list($drink,$color,$power)=$info;
		With associative array:
			$info=array('drink'=>'coffee','color'=>'brown','power'=>'caffeine');
			//Listing all the variables
			list("a"=>$a,"b"=>$b,"c"=>$c) = $info
# 6 - Constants

## Definition

* Identifier for a value that does not change once defined

## Naming

* Start with a letter or underscore, are case sensitive, contain only alphanumeric characters and underscores. By convention, use only uppercase letters

## Access

* May be defined and accessed anywhere in a program
* Must be defined before use; cannot be changed subsequently

# Magic Constants (_XXX_)

## Definition

* PHP provides a set of predefined constants defined by the PHP core (Ex> E_ERROR; TRUE) (REVISAR)

* Several of these can change, depending upon where they are used; therefore, not true constants (EX: __DIR__; __NAMESPACE__)
	* __DIR__: returns the current working directory;
	* __FILE_: returns the current working directory and file name;
	* __FUNCTION__: returns the current function name
	* __CLASS__: returns the current class and namespace if defined
	* __LINE__: returns the current line number at the point of use
	* __METHOD__: returns the current method name;
	* __TRAIT__: returns the trait name including namespace if defined;
	* __NAMESPACE__: returns the current namespace

*Example:
ClassName::class: returns the fully qualified class name

namespace NS{
	class ClassName {}
	echo ClassName::class;
}

# 7 - Namespaces

## Definition

* Namespaces are a method of grouping related PHP code elements within a library or application

## Use

* Helps to prevent accidentally re-defining functions, classes, constants, etc

* Avoids having to use long, highly descriptive class names

* Constants, classes and functions are affected by the use of namespaces

* Create sub-namespaces to sub-divide a library

## Declaring namespaces

* Must declare the use of namespaces with keyword 'namespace' at the beginning of the code file (right after <?PHP)

* Use one namespace per code file (best practice)

* Unless a namespace is defined, constants, classes, functions, traits and interfaces are defined with the global space
	* Within a namespace qualifying with a "\" references the global namespace

* Once code elements within a single namespace are defined, they can be used in other php files
Example:
	namespace NS {
		class Db {
			public function getInstance(){
				return new \pdo(...);
			}
		}
	}

## Importing/Aliasing namespaces

* Once declared, import namespace with the "use" operator

* Declarations may be grouped (use m\namespace\{A,B,C}) (REVISAR)

* Can create aliases for namespaces
	* Ex: 
		Use Path1\Path2\Path3 as E;
		$test = new E\Some_Class();

## Note

* Namespaces are not equivalent to classes. A namespace is an execution enviroment isolation in which a class, function, constant, trai and interface are defined and therefore protected from naming collisions from a different environment

# 8 - Extensions

## There are many add-ons (extensions) available for specific programming tasks

	* Added to the php.ini configuration file

	* Need to configure php.ini to activate the extensions you want to use, as well as specify all then needed paths (Ex.: libraries)

	* Not all extensions can be discussed within this guide, pĺease review the complete listing available in the php manual (REVISAR)


## PECL (PHP Extension Community Library)

	* Repository for PHP extensions; similar structure and concept to the php code repository PEAR (PHP Extension and Application Repository) (REVISAR)

## CORE Extensions (REVISAR)

	* There are a set of various php language elements, called core extensions, that are part of the php core

	* They include specific arrays, classes, objects, etc

## Userland rules
	
	* Userland refers to those applications that run in the user space (not the kernel)

	* Select rules: (see the complete listing in the php manual) (REVISAR)

## Global Namespace Constructs (REVISAR)

	* Functions
	* Classes
	* Interfaces
	* Constants (other than class)
	* Variables (defined outside of functions or methods)

## Internal Naming

	* Functions use underscores between words
	* Classes us the CamelCase rule
	* The double underscore prefix is reserved, and refers to elements considered magical

# 9 - Configuration

## Definition

	* Configuration files estabilish the initial settings for applications, as well as servers and operating systems

## PHP.INI

	* Configuration file for PHP
	* File run upon server starting (CGI) or upon invocation (CLI) (REVISAR)
	* Search Order under Windows:
		* sapi MODULE > phprc VARIABLE > Registry Keys > HKEY_LOCAL_MACHINE\software\php > Working Directory (NOT CLI) > Directory (SERVER or PHP) > Win Directory (REVISAR)

## USER.INI (REVISAR)

	* PHP Supports user type ini files

		* Processed by cgi/fastcgi SAPI (REVISAR)
		* Must use PHP_INI_PERDIR or PHP_INI_USER

	* PHP searches for these ini files in all directories

	* Controlled by directives user_ini.filename,user.cache_ttl
		* File named by user_ini.filename (default=user.ini)
		* File reading frequency defined by user.cache_ttl

## Settings

	* Can define version/s of PHP in ini file
	* Generally, use ini_set() within the php script; some settings require php.ini or httpd.conf

# 10 - Perfomance

## Factors affecting perfomance (two major areas)
	* Reduced memory usage
	* Run-time delays

## Garbage Collection

	* Clears circular-reference variables (REVISAR) once prerequisites are met, via root-buffer full or call to the function GC_COLLECT_CYCLES()
	* Garbage Collection Execution hinders perfomance (REVISAR)

## OPCODE CACHE

	* Stores the bytecode/opcode (REVISAR) results of compiling PHP code which often improves perfomance
	* Available into PHP (needs to be turned on). third-party products are also available (REVISAR)


