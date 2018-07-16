# Control Structures

## Conditions

* IF
	* Evaluates for a condition (boolean value), to determine whether to execute code; can be nested
* ELSE
	* Provides alternative execution, when combined with IF(=FALSE)
* ELSEIF(ELSE IF)
	* Provides alternative execution, when combined with IF (=FALSE), but its own condition must be met (FLOW: IF...ELSEIF...ELSE)
* IF-ELSE(TERNARY OPERATOR)
	* Special form: (EXPRESSION) ? VALUEIFTRUE : VALUEIFFALSE
* TERNARY OPERATOR, SHORT FORM
	* (VALUEIFTRUE) ?: VALUEIFFALSE
* SWITCH
	* Use to evaluate (Boolean Value) against a series of conditions, to determine which code to execute for each condition

## Loops

* WHILE
	* Executes statement until condition is no longe evaluated as boolean true; condition evaluated at beginning

* DO-WHILE - REVISAR diferenca entre while e do-while
	* Executed statement until condition is no longer evaluated as boolean true; condition evaluated at end

* FOR
	* Executes first statement one time as an assignment, the second statement as a looping condition checked at the beginning of the first and subsequent iteratins until condition is no longer evaluated as boolean true, then executes the third and final statement at the end of each iteration

* FOREACH - REVISAR sintaxes do foreache
	* Used only for arrays; assigns value of current element to the variable and advances the array pointer util it reaches the last element

* CONTINUE
	* Within loops, used to pass over any remaining code within the iteration and return to the initial condition evaluation step

* BREAK
	* Halts execution of loops utilizing the for, foreach, while, do-while, switch control structures

