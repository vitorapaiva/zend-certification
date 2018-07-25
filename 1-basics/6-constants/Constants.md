# Constants

## Definition

* Identifier for a value that does not change once defined

## Naming

* Start with a letter or underscore, are case sensitive, contain only alphanumeric characters and underscores. By convention, use only uppercase letters

## Access

* May be defined and accessed anywhere in a program
* Must be defined before use; cannot be changed subsequently

# Magic Constants (_XXX_)

## Definition

* PHP provides a set of predefined constants defined by the PHP core (Ex> E_ERROR; TRUE) (REVISAR)

* Several of these can change, depending upon where they are used; therefore, not true constants (EX: __DIR__; __NAMESPACE__)
	* __DIR__: returns the current working directory;
	* __FILE_: returns the current working directory and file name;
	* __FUNCTION__: returns the current function name
	* __CLASS__: returns the current class and namespace if defined
	* __LINE__: returns the current line number at the point of use
	* __METHOD__: returns the current method name;
	* __TRAIT__: returns the trait name including namespace if defined;
	* __NAMESPACE__: returns the current namespace

*Example:
ClassName::class: returns the fully qualified class name

namespace NS{
	class ClassName {}
	echo ClassName::class;
}

