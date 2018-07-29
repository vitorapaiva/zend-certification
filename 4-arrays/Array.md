# 1 - Array Definition

* Way of ordering data by associating values to key
* Unique keys are associated with a single value or set of values

# Creating arrays

* Indexed numerically (indexed array)
	* Ex: $x = array('a','b','c');
	* Ex: $x = ['a','b','c'];
	* Ex: $x = array(0>='a',1=>'b',2=>'c');
	* Ex: $x = [0=> 'a', 1=>'b', 2=>'c'];

* Indexed with strings (associative array)
	$x = array(
		'XML' => 'eXtensible Markup Language'
	);
	$x = [
		'XML' => 'eXtensible Markup Language'
	];

# Filling arrays
* range() creates an array with values from an interval
		* Default step is "1"
		* Ex: $x = range(1.2,4.1); // == array(1.2,2.2,3.2)

# Splitting arrays

* array_splice(array,offset,length(optional),maintainIndices(optional,boolean)) Returns part of an array
	* optional 3rd param, length
	* optional 4th param, maintain indices (boolean)

	* Negative offset means count from the end of the array
	* Negative length exclude elements x positions from the end of the array
		* Ex: $x = array(1,2,3,4,5);
			  $y = array_slice($x,-4,-1); //array(2,3,4)

# Adding elements

* array_push() adds 1 or more elements to the end of an array

	* array is provided by reference

	* return value is the new number of array elements
		* Ex: $x = [1,2,3];
			  $n = array_push($x,4,5); // $n = 5
		* Alternative: $n[] = 4; $n[] = 5;

* array_unshift() adds 1 or more elements to the beginning of an array

	* Already existing elements are moved towars the end

	* Return value is the new number of array elements
		* Ex: $x = [3,4,5];
			  $n = array_unshift($x,1,2); // $n == 5

# Removing elements

* array_pop() removes 1 element at the end of an array
	* array is provided by reference
	* Return value is the removed element
		* Ex: $x = [1,2,3]
			  $n = array_pop($x); // $n == 3

* array_shift() removes 1 element at the beginning of an array
	* Remaining elements are moved towards the front
	* Return value is the removed element
		* Ex: $x = [1,2,3];
			  $n = array_shift($x); //$n==1

# Looping arrays

*for Loop and indices
	* Ex: for($i=0;$i<count($a);$i++){
				echo $a[$i];
		  }
	* Only makes sense if there are no gaps in the indices

* foreach Loop and values
	* Ex: foreach ($a as $value){
			echo $value.'<br>';
		  }

* foreach loop and keys and values
	* Ex: foreach ($a as $key => $value){
			echo "key: $value<br>";
		  }

* array_walk() provides access to all array elements
	* A callback function is called for each element

* Checking for array values
	* array_key_exists ($key,$array)
		Determines whether there is an index $key in the array $array

	* in_array($element,$array)
		Determines whether there is an element $element in the array $array

	* array_keys() is an array of all array indices

	* array_values() is an array of all array values

# Sorting arrays (REVISAR)

	* sort($a) sorts values alphabetically
		* The second parameter indicates the sort mode
			SORT_LOCALE_STRING Sorts according the locale settings
			SORT_NUMERIC numeric sorting
			SORT_REGULAR "Normal" sorting (default)
			SORT_STRING  Sorting as strings

# Other sorting functions
	rsort() like sort(), but in reverse
	asort() sorts associative arrays (maintains key-value)
	arsort() like asort(), but in reverse
	ksort() sorts by keys
	krsort() like ksort(), but in reverse
	usort() user-defined sort

# Natural sorting
	* natsort() returns results based on how a human would see order
		(*9.PHP > *10.PHP > *11.PHP) "natural" string sorting vs
		(*10.PHP > *11.PHP > *9.PHP) "normal" string sorting

# Merging Arrays
	* array_merge($x, $y) Creates an array containing the elements of both arrays, X and Y

# Comparing arrays (REVISAR)
	* array_diff($x, $y) compares the two arrays, X and Y
	* return value is an array with all elements in $x not in $y
	* related functions:
		array_diff_assoc() compares values and keys
		array_diff_key()   compares only keys
		array_diff_uassoc() Like array_diff_assoc but with user-defined compare function
		array_diff_ukey		Like array_diff_key() but with user-defined compare function

# SPL - ArrayObject Class (REVISAR)
	* Class allows objects to function as arrays
		ArrayObject::STD_PROP_LIST Properties are retained when accessed as a list(Ex: var_dump,foreach)
	* Related arrayobjects (selection) 	
		ArrayObject::append appends a value
		ArrayObject::asort sorts the entries by value
		ArrayObject:natsort sorts according to a "natural order"

