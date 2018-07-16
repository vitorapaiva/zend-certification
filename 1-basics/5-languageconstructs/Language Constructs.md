# Language Constructs

## Output Constructs

* die() and exit()
	* These constructs are equivalent. Used to output a result and then terminate the running script

* echo()
	* Used to output a result(text, strings, variables). If using strings containing quotations, make sure you handle them correctly (use apostrophe or escape with \)

* return()
	* Used to halt execution of a function (called within function) or of a script (called within global scope)

* print()
	* Used to output a string (is an operator)

## Evaluation Constructs

* empty()
	* Used to assess whether a variable (only) is empty (empty string, empty array, 0, 0.0, "0", NULL, FALSE, a variable without assigned value)

* eval() - REVISAR
	* Used to evaluate the contents of a string as php code

* include and include_once()  - REVISAR diferenca entre include e include_once
	* Used to both include and evaluate a file

* require() and require_once()  - REVISAR require entre include e require_once
	* These constructs are similar to include() and include_once(), except that a failure in execution results in a fatal error, while include() generates a warning

## Other Constructs

* isset()
	* Use to determine whether a variable has been set (therefore is not null)

* unset()
	* Use to unset the variable

* list() - REVISAR COMO FUNCIONA
	* Use to assign a group of variable in one step	