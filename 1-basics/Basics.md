# 1 - Syntax

## Punctuation
	* Terminate code statements with a semi-colon (;)
	* Use appropriate tags

## TAGS

### Opening
	*<?php
	*<?= (short for <?php echo)
### Closing
	*?>
	*?>

### Comments
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

## Bitwise operators
	
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
	According to W3C, Bitwise operators allow operating on the bitwise representation of their arguments. 
### What is a bit?
	A bit (Binary digIT) is the basic unit of information stored in the computing system that exists in two possible states, represented as ON or OFF. In a computer system, the ON state considered as 1 and OFF state considered as 0. These states can be compared with two states of a flip-flop, two states of an electric switch ( ON and OFF) e.t.c. These two values 0 and 1 are called Binary digit and these digits are in a specific number system, that is BINARY number system which constructs upon the base of 2.
	In decimal number system, a number construct upon the base of 10. Let us see how a decimal number can be constructed -

	  231=(2 x 102)+(3 x 101)+(1 x 100)
	      =200+30+1
	      =231

	The binary number system also follows the same concept. The only difference is the base is 2 instead of 10. Let us see how a binary number can be converted into a decimal number -

	1011010=(1 x 2^6)+(0 x 2^5)+(1 x 2^4)+(1 x 2^3)+(0 x 2^2)+(1 x 2^1)+(0 x 2^0)
		  =(1 x 64) +(0 x 32)+(1 x 16)+(1 x 8)+(0 x 4)+(1 x 2)+(0 x 1)
		  =64+0+16+8+0+2+0
		  =90

	So, (1011010)2= (90)10  
	
	<?php
	$x=77;
	$y=198;
	echo $x & $y; // 68
	?>
	Placing in a table, they share two bits in two places (64, 4)
	Place Value 	128 	64 	32 	16 	8 	4 	2 	1 	  	 
		$x 	0 	1 	0 	0 	1 	1 	0 	1 	= 	77
		$y 	1 	1 	0 	0 	0 	1 	1 	0 	= 	198
		
	<?php
	$x=5;
	$y=11;
	echo $x | $y; //15
	?>
	The $x and $y sets together either 1st or 2nd or 3rd or 4th bits. So return value is the addition of place value of the sets bits, that is 8+4+2+1=15. 
	1 Byte ( 8 bits )
	Place Value 	128 	64 	32 	16 	8 	4 	2 	1 	  	 
		$x 	0 	0 	0 	0 	0 	1 	0 	1 	= 	5
		$y 	0 	0 	0 	0 	1 	0 	1 	1 	= 	11
	
	<?php
	$x=12;
	$y=11;
	echo $x ^ $y; //7
	?>
	The $x and $y sets together either 1st or 2nd or 3rd or 4th bits but they shared together only a 4th bit. So return value is the addition of place value of the set bits but not the bit shared together, that is 4+2+1=7
	1 Byte ( 8 bits )
	Place Value 	128 	64 	32 	16 	8 	4 	2 	1 	  	 
		$x 	0 	0 	0 	0 	1 	1 	0 	0 	= 	12
		$y 	0 	0 	0 	0 	1 	0 	1 	1 	= 	11
	<?php
	$x=12;
	$y=10;
	echo $x & ~ $y; //4
	?>
	Place Value	128	64	32	16	8	4	2	1	 	 
		$x	0	0	0	0	1	1	0	0	=	12
		$y	0	0	0	0	1	0	1	0	=	10
	The $x and $y sets together either 1st or 2nd or 3rd or 4th bits but they shared together only a 4th bit. So return value is the 4, because of only bit sets in $x but not in $y.
	
	<?php
	$x=12;
	$y=10;
	echo ~ $x &  $y; //2
	?>
	
	In this case, the return value is 2 because the bit set on $y but not on $x.
### Bit shifting
	If a and b are two numbers, BIT SHIFTING shifts a bits b number of steps. each step refers to multiply by two if it is BIT SHIFT LEFT. If it is BIT SHIFT RIGHT, then each step refers to division by two. If the number can no longer be divided by two, the return is 0
	
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
	Ex:
		function add(&$var){ // The &amp; is before the argument $var
		$var++;
		}
		$a = 1;
		$b = 10;
		add($a);
		echo "a is $a,";
		add($b);
		echo " a is $a, and b is $b"; // a is 2, a is 2, and b is 11
	Ex:
		$array = array(1,2,3,4);
		foreach ($array as &$value){
		$value = $value + 10;
		}
		unset ($value); // Must be included, $value remains after foreach loop
		print_r($array); //Array ( [0] => 11 [1] => 12 [2] => 13 [3] => 14 )
		
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
	* $value = $_GET['id'] ?? 1; (checks if the value of $_GET['id'] is null. If not, returns id. If it is, returns 1)
	
* Spaceship operator, short form
	* A <=> B
	* Return 1 if A > B, -1 if B > A, 0 if A == B
* SWITCH
	* Use to evaluate (Boolean Value) against a series of conditions, to determine which code to execute for each condition
	switch ($i) {
	    case 0:
		echo "i equals 0";
		break;
	    case 1:
		echo "i equals 1";
		break;
	    case 2:
		echo "i equals 2";
		break;
	}
## Loops

* WHILE
	* Executes statement until condition is no longe evaluated as boolean true; condition evaluated at beginning
	while (salario < 5000) 
        {
                salario *= 100; 
        }
* DO-WHILE - (REVISAR)
	* Executed statement until condition is no longer evaluated as boolean true; condition evaluated at end
	do {
		salario *= 100;
	} while (salario < 5000)
* FOR
	* Has three statements in parentheses, executes first statement as a one time assignment. Iteration continues while the second statement (a loop condition) is no longer evaluated as boolean true. Third statement is executed at the end of each iteration

* FOREACH 
	* Used only for arrays; assigns value of current element to the variable and advances the array pointer util it reaches the last element
	foreach (array_expression as $value) ($value of each position can be used in the foreach)
	    statement
	foreach (array_expression as $key => $value) (both the $key and the $value are available in the foreach)
	    statement
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
	* Used to evaluate the contents of a string as php code. It executes the string passed as a php code.
	$string = 'taça';
	$name = 'café';
	$str = 'Esta é uma $string com o meu $name nela.';
	echo $str; //Esta é uma taça com o meu café nela.

* include and include_once()  (REVISAR)
	* Used to both include and evaluate a file

* require() and require_once()  - (REVISAR)
	* These constructs are similar to include() and include_once(), except that a failure in execution results in a fatal error, while include() generates a warning
	
### Functional Difference :

include vs include_once : There is only one difference between include() and include_once(). If the code from a file has been already included then it will not be included again if we use include_once(). Means include_once() include the file only once at a time.

include vs require : if include() is not able to find a specified file on location at that time it will throw a warning however, it will not stop script execution. For the same scenario, require() will throw a fatal error and it will stop the script execution.

require vs require_once : There is only one difference between require() and require_once(). If the code from a file has been already included then it will not be included again if we use require_once(). Means require_once() include the file only once at a time.

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

* PHP provides a set of predefined constants defined by the PHP core (Ex> E_ERROR; TRUE)

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

	* Repository for PHP extensions; similar structure and concept to the php code repository PEAR (PHP Extension and Application Repository). PECL is the repository and its extensions can be installed through the PEAR commands

## CORE Extensions 
	* There are a set of various php language elements, called core extensions, that are part of the php core
	* They include specific arrays, classes, objects, etc.
	* They cannot be left out of the PHP compilation
		* Arrays
		* Classes/Objects
		* CSPRNG
		* Date/Time
		* Directories
		* Error Handling
		* Program execution
		* Filesystem
		* Filter
		* Function Handling
		* Hash
		* PHP Options/Info
		* Mail
		* Math
		* Misc.
		* Network
		* Output Control
		* Password Hashing
		* Phar
		* Reflection
		* POSIX Regex
		* Sessions
		* SPL
		* Streams
		* Strings
		* Tokenizer
		* URLs
		* Variable handling

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
	* Classes use the CamelCase rule
	* The double underscore prefix is reserved, and refers to elements considered magical

# 9 - Configuration

## Definition

	* Configuration files estabilish the initial settings for applications, as well as servers and operating systems

## PHP.INI

	* Configuration file for PHP
	* File run upon server starting (CGI) or upon invocation (CLI). PHP CLI is the command-line interface for PHP (e.g. for creating standalone applications). PHP CGI is the common gateway interface for PHP (e.g. for web applications)
	* Search Order under Windows:
		* sapi MODULE > phprc VARIABLE > Registry Keys > HKEY_LOCAL_MACHINE\software\php > Working Directory (NOT CLI) > Directory (SERVER or PHP) > Win Directory (REVISAR)

## USER.INI (REVISAR)

	* PHP Supports user type ini files

		* Processed by cgi/fastcgi SAPI. SAPI ( Server Application Programming Interface ) also know as ISAPI ( Internet Server Application Programming Interface) for Microsoft, NSAPI (Netscape Server Application Programming Interface) for Netscape. It is the mechanism that controls the interaction between the "outside world" and the PHP/Zend engine.
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

	* Clears circular-reference variables  once prerequisites are met, via root-buffer full or call to the function GC_COLLECT_CYCLES()
	* Garbage Collection Execution hinders perfomance

## OPCODE CACHE
	OpCode Caches are a performance enhancing extension for PHP. They do this by injecting themselves into the execution life-cycle of PHP and caching the results of the compilation phase for later reuse. It is not uncommon to see a 3x performance increase just by enabling an OpCode cache.
	* Stores the bytecode/opcode results of compiling PHP code which often improves perfomance
	* Available into PHP (needs to be turned on). third-party products are also available


