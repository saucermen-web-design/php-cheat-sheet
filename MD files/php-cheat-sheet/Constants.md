Constants

# Constants

* Constants are **like** variables **except** that once they are defined they **cannot** be changed or undefined.

* A valid constant name starts with a letter or underscore (no $ sign before the constant name).

#### Unlike variables, constants are automatically global across the entire script.

* To create a constant, use the `define()` function.

	* Syntax:

		* `define(name, value, case-insensitive)`

		* `name`: Specifies the name of the constant
		
		* `value`: Specifies the value of the constant
		
		* `case-insensitive`: Specifies whether the constant name should be case-insensitive. Default is false

* In PHP7, you can create an Array constant using the `define()` function.