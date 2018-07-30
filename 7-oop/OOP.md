# Objects (REVISAR)

* Converting objects to strings
	* The magic method __toString() is called, if available
	* Includes print, string interpolation, operation with strings, calling functions that expect strings

* Copying objects
	* keyword: clone
	* Objects are always passed by reference
	* Cloning an object causes the object itself to be copied instead of passing the reference
		* Cloning by default copies all the properties, but uses assignment, not clone, so cloning is "shallow" by default
	* PHP executes the magic method __clone() upon cloning, if available

* Serializing objects
	* Functions: serialize()/unserialize()
	* Magic method __sleep() is executed with serialization, if available
	* Allows you specify which properties should be stored (serialized) and which should not be stored
		* can also create/change properties for serialization
	* Magic method __wakeup() is executed with deserialization, if available
		* Ex: to open a database connection unique to the object

# Creating classes and instantiation

* Keyword: class

* A class defines the abstract chracteristics of an object, including its properties and methods

* Properties and methods defined by a class are called "members"

* Structure:
	Keyword > class name> {constants, properties & methods}
	Properties = class variables
	Methods = class functions

* Create an instance of a class with the keyword "new" (REVISAR)
	* An object is created unless it has a constructor defined that throws and exception
	* Classes should be defined "prior" to instantiation
		* With autoloading, a class can be defined (loaded) at the moment it is required by the new operator
		* Assigning an existing object to a new variable, or passing as a function parameter, result in a reference to the same object
		Ex:
			class myClass {
				// ...
			}

			$c = new myClass();
	* Create an anonymous class with "$c = new class {}"

# Inheritance: Class

* Use the keyword extends in the class declaration to have a class inherit the methods and properties of another class
	* A class can inherit from only one class
	* Inherited methods and properties can be overriden by redeclaring them with the same name

* Whenever an extending class overrides the parents' method definition, the parents' method will not be called

	* Similarly for magic methods defined in the subclass (REVISAR)
	* Overriden properties and methods cannot have a lower visibility
		* For example, if classA has a public method called getA(), classB which extends classA cannot declare a method called getA() and declare it private
		* Classes and methods marked with final cannot be overridden
		* The parameter signature cannot be "stricter" than before or an E_STRICT error will be thrown (except for the constructor)

# Abstract classes (REVISAR)

* Keyword: abstract

* Can be used as a base or skeleton of a derived class

* May contain method implementations

* Abstract methods must be implemented in derived classes

* Visibility can become weaker / more permissive, but not stronger / less permissive (Ex: you cannot go from public to private)

# Interfaces (REVISAR)

* Keywords: interface, implements

* Provides methods to implement
	* Does not contain any implementation itself

* Classes may implement more than one interface

* Interfaces may inherit from other interfaces using the extends keyword

* All methods are assumed to be public in the interface definition - can be defined explicity as public, or implictly

* When a class implements multiple interfaces, there cannot be any naming collision between methods defined in the different interfaces unless the duplicated methods have the same signature

# Exceptions (REVISAR)

* Keyword: throw ... to launch an exception
* try/catch/finally structure: try {...} catch(...){...} finally {...}
	* A catch block may use type-hinting to expect specific exceptions
	* Need to provided the type in the catch
	* finally block contains code that is executed whether an exception happened or not
* Custom exceptions need to extend the base Exception class

# Constructors / destructors (REVISAR)

* __construct() is a reserved method name for the class constructor
* function __construct is used to declare a constructor class method
	* These are setup methods for new objects
* ___destruct() is a reserved method name for the class destructor
	* If a class maintains an open file handle or connection throughout its life, then the __destruct() method is a good place for a close-type operation
* __destruct() is called whenever an object is destroyed (when all its references are removed or the end of the script) is reached

# Properties (variables)

* Class member variables are called properties or attributes
* Visibility keywords: public, private, protected (REVISAR)
* Declared like any variable; if initialized, must be with a constant value
* Creating a variable within the class..
* Ex:
	class myClass {
		public $member = "ABC";
		// ...
	}
	$c = new myClass();
	echo $c->member;

# Methods(functions)

* Methods are functions within a class construct
* If visibility is not explicitly defined, then default is public
* Can access properties or methods of the current instance using $this (format $this->property), for non-static properties
	Ex: 
		class myClass {
			public $member="ABC";
			function showMember(){
				echo $this->member;
			}
		}
		$c = new myClass();
		$c->showMember();

# Static properties / methods

* Keyword: static
* Scope resolution operator (::)
	* Token that permits access to the static, constant, or overriden properties / method of a class
		* Use the class name whenever referencing these elements outside of the class definition
		* Self always refers to the current class; parent refers to the parent of the current class (the one it extends)
		* Static context is working with a class directly and not with objects
* Requires declaration, as with any method; otherwise results in a fatal error
* No objects instances
* You can access a static class method using a variable reference (Ex: ClassName::$varMethod)

# Autoload (REVISAR)

* PHP executes the __autoload() function, if defined, whenever there is an attempt to use a class or interface that has not been defined
	* Param: name of missing class

* Exceptions thrown in __autoload() can now be caught in a catch block, as long as the custom excepton class is available
	* __autoload() can recursively load the custom exception class

* spl_autoload() is used as an implementation for __autoload()
	* Call spl_autoload_register,which will register a function as an __autoload() implementation
	* Boolean: it prepends the autoloader on the autoload stack when true; appends when false

# Reflection (REVISAR)

* Allows for introspection of:
	* Objects
	* Classes
	* Methods
	* Properties
	* Functions
	* Parameters
	* Exceptions
	* Extensions
	* Generators
	* Return types

* Helper classes format: ReflectionXXX (where XXX = object/class...)

# Type Hinting

* Data types may be provided for function & method parameters and return types

	* Classes
	* Arrays
	* Interfaces
	* Iterable
	* Scalars

* If a parameter data type does not match a specified type hint, a fatal error occurs

* Class type matches either exact type or any type that extends or implements (in the case of interfaces) this type

* As long as the type-hinted class exists somewhere below the passed class' hierarchy, it will be allowd

* Strict data typing available with declare(strict_types=1)

# Class constants

* A constant that is only available within a class or interface scope
	* Similar in concept to a constant that is re-defined using define()

* Interfaces may also include constants

* Reference a class constant with the <ClassName>::CONSTANT syntax; the classname can actually be a variable

* Visibility of class constants available since PHP 7.1

# Late static binding

* Binds the "static" keyword to the name of the calling class late at run time
	* Stores the class named in the last "non-forwarding" call
	* Static method calls class explicitly named (name::xx)

* Static references (Ex: self::xx) use the current class to which the function belongs

# Magic methods

	* When accessing non-existent properties, PHP will execute special ("magic") functions, if available
	* Ex:
		__get() reads a non-existent property
		__set() writes a non-existent property
		__isset() checks if the non-existent property is set
		__unset() unsets or destroys a non-existent property

	* When accessing non-existent methods, PHP will execute the special __call() function, if available

	* The __callStatic() magic method allows the calling of non-existent static methods (must be public)

# SPL (REVISAR)

* Acronym for "Standard PHP Library"
* Examples:
	ArrayIterator
		* Creates a stand-alone iterator object over an array, which allows it to iterate over the same array multiple times and also passes the iteration state around in an object

		* Ex: current element, next element

		* Allows foreach access

	* ArrayObject
		* Interface that implements an array
		* Ex: number of elements, read/write access
		* Allows access to the object using array functions

# Generators (REVISAR)

* Mechanism to generate iterators

* A generator function returns multiple values

* Individual values are returned using the yield keyword

* Ex:
	function myGenerator() {
		for($i=1;$i<=0;$i++){
			yield $i;
		}
	}

* Generator may use return for the final return expression; the generator's getReturn() method gives access to this value

# Traits (REVISAR)

* A construct that encapsulates reusable properties and methods

* A trait is like a non-instatiable class

* Classes can use traits

* Keyword trait to define a trait, keyword use to use it within a class

* Trait precedence: current class members > trait methods > inherited methods

* May change visibility of trait methods using the as keyword:
	class c { 
		use t { 
			method 1 as protected; 
		}
	}

* A class may use multiple traits
	* Fatal error if traits have conflicting names

* Conflict resolution with insteadof operator:
	use t1,t2 {
		t1::method1 insteadof t2;
	}

* Can also use aliasing
	use t1,t2 {
		t2::method 1 as method1_from_t2;
	}

