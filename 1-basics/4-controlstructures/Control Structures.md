# Control Structures

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

