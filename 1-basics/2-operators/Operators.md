# Operators

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