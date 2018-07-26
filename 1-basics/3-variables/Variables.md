# Variables

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

