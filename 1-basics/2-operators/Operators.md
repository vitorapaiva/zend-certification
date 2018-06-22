# Operators

## Arithmetic operators

	* Basic calculations
		** + (adding)
		** - (substracting)
		** * (multiplying)
		** / (dividing)
	* Modulus (remainder when dividing)
		** Ex: $m = 5%2; // $m == 1

## Bitwise operators (review)
	
	* Use to work with bits withing an integer; arithmetic
	* Integral Numbers are internally converted into bits
		**Ex: 5 -> 0101 = 0*8 + 1*4 + 0*2 + 1*1
	* Shift bits << X move bits by X times
		** Ex: 4 >> 2 == 1 (like dividing by 4)
	* Negate bits ~ convert 0s into 1s ; 1s into 0s

## Logical Operators:
	* & equivalent to 'AND': matching "1" in both operands
	* | equivalent to OR: at least one "1" in an operand
	* ^ equivalent to EITHER-OR: only one "1" in both operands

## Assingment Operators
	* Assign (=)
		** When using arrays, assign value to keys with =>
	* Short forms (combined)
		** Assignment (+ and operator)
			Works with operators: - * / & | ^ >> <<
			Ex: $a += 1; is short-hand for $a = $a + 1;
		** Combined/concatenating assingment (.=)
			Ex: $a = "Hello,";
			    $a.= "World !"; ...results in "hello, world!"
	* Increase / decrease (++ --)
		** Placement important: in front of expression - increased or descrease first; after expression, the reverse

## Comparison operators
	* Equality (==)		Inequality (!=)
	Php handles data type conversion "123" == 123
	(===)			(!==)
	PHP checks the data type "123" !== 123
	* Greater than (>) 	Less than (<)
	* Grater or equal (>=)	LEss than or equal (<=)
 
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

## Execution operators
	* use backticks `` to execute the contents enclosed by them as a shell command, equivalent to shell_exec()

## Operator precedence
	* follows mathematical precedence in most instances (Ex: multiplication/division precedes addition/subtractions)
	* use parentheses to enforce non-standard precedence