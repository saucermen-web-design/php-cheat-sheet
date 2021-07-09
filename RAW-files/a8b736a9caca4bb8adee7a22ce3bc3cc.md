Functions

# Functions

#### A function name must start with a letter or an underscore. Function names are __NOT__ case-sensitive.

* The following example shows how to use a default parameter. If we call the function setHeight() without arguments it takes the default value as argument:

	```
	<?php declare(strict_types=1); // strict requirement
	function setHeight(int $minheight = 50) {
	  echo "The height is : $minheight <br>";
	}

	setHeight(350);
	setHeight(); // will use the default value of 50
	setHeight(135);
	setHeight(80);
	?>
	```

* To let a function return a value, use the `return` statement.

	* PHP 7 also supports Type Declarations for the return statement. Like with the type declaration for function arguments, by enabling the strict requirement, it will throw a "Fatal Error" on a type mismatch.

		* To declare a type for the function return, add a colon `:` and the type right before the opening curly `{` bracket when declaring the function.
		
		```
		<?php declare(strict_types=1); // strict requirement
		function addNumbers(float $a, float $b) : float {
			return $a + $b;
		}
		echo addNumbers(1.2, 5.2);
		?>
		```

		* You can specify a different return type, than the argument types, but make sure the return is the correct type.

* In PHP, arguments are usually passed by value, which means that a copy of the value is used in the function and the variable that was passed into the function cannot be changed.

* When a function argument is passed by reference, changes to the argument also change the variable that was passed in. To turn a function argument into a reference, the `&` operator is used.

	```
	<?php
	function add_five(&$value) {
	  $value += 5;
	}

	$num = 2;
	add_five($num);
	echo $num;
	?>
	```

id: a8b736a9caca4bb8adee7a22ce3bc3cc
parent_id: 41b6510b27e54240bee2cce720f52b4d
created_time: 2021-06-23T18:42:48.324Z
updated_time: 2021-06-23T18:42:52.733Z
is_conflict: 0
latitude: 38.06110000
longitude: -84.45810000
altitude: 0.0000
author: 
source_url: 
is_todo: 0
todo_due: 0
todo_completed: 0
source: joplin-desktop
source_application: net.cozic.joplin-desktop
application_data: 
order: 0
user_created_time: 2021-06-23T18:42:48.324Z
user_updated_time: 2021-06-23T18:42:52.733Z
encryption_cipher_text: 
encryption_applied: 0
markup_language: 1
is_shared: 0
share_id: 
conflict_original_id: 
type_: 1