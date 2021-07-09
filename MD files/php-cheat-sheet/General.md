General

# General

* PHP is a loosely typed language meaning it automatically associates a data type to the variable, depending on its value. Since the data types are not set in a strict sense, you can do things like adding a string to an integer without causing an error.

	* In PHP 7, type declarations were added. This gives us an option to specify the expected data type when declaring a function, and by adding the `strict` declaration, it will throw a "Fatal Error" if the data type mismatches.

		* To specify strict we need to set `declare(strict_types=1)`;. This **must be on the very first line** of the PHP file.

* Variables always start with a dollar sign.

* No dot notation

* Everything is function based

* PHP excutes prior to JS/HTML/CSS

* PHP console logging function:

```
	function console_log( $data ){
	  echo '<script>';
	  echo 'console.log('. json_encode( $data ) .')';
	  echo '</script>';
	}

	// Usage:
	$myvar = array(1,2,3);
	console_log( $myvar ); // [1,2,3]
	
```

#### Should utilize `print_r()`, or `echo` over this

* `is_numeric()` function can be used to find whether a variable is numeric. The function returns true if the variable is a number or a numeric string, false otherwise.

* `var_dump()` function returns the data type and value of a variable.

* `__construct()` function, PHP will automatically call this function when you create an object from a class.

```
<?php
	class Car {
	  public $color;
	  public $model;
	  public function __construct($color, $model) {
	    $this->color = $color;
	    $this->model = $model;
	  }
	  public function message() {
	    return "My car is a " . $this->color . " " . $this->model . "!";
	  }
	}

	$myCar = new Car("black", "Volvo");
	echo $myCar -> message();
	echo "<br>";
	$myCar = new Car("red", "Toyota");
	echo $myCar -> message();
?>
```