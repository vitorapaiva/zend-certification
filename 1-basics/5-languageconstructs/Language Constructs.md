# Language Constructs

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
