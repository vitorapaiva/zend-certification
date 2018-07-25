# Namespaces

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

