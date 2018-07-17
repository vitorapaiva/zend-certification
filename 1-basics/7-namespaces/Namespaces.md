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

* Unless a namespace is defined, classes and functions are contained within the global space
	* Prepend "\" to indicate use of an element from global scope (REVISAR)

* Once code elements within a single namespace are defined, they can be used in other php files

## Importing/Aliasing namespaces

* Once declared, import namespace with the "use" operator

* Can create aliases for namespaces
	* Ex: If complete namespace name is path1pth2path3, set =E then, when need to call, can reference alias as E/PATH4 (REVISAR)

## Note

* Namespaces are not equivalent to classes. A class is an abstract definition of an object, while a namespace is an evironment in which a class, function, or a constant can be defined

