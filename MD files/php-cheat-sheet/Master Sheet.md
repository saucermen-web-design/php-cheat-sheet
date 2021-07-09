Master Sheet

# PHP Cheat Sheet
#### Author: Coty McKinney
#### Referenced: https://www.w3schools.com/php
---

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

## Strings

* `strlen()` function returns the length of a string

* `str_word_count()` function counts the number of words in a string

* `strrev()` function reverses a string

* `strpos()` function searches for a specific text within a string. If a match is found, the function returns the character position of the first match. If no match is found, it will return FALSE.

* `str_replace()` function replaces some characters with some other characters in a string.

## Integers

* The `(int)`, `(integer)`, or `intval()` function are often used to convert a value to an integer.

### Here are some rules for integers:

* An integer must have at least one digit

* An integer must NOT have a decimal point

* An integer can be either positive or negative

* Integers can be specified in three formats: decimal (10-based), hexadecimal (16-based - prefixed with 0x) or octal (8-based - prefixed with 0)

### PHP has the following predefined constants for integers:

* PHP_INT_MAX - The largest integer supported

* PHP_INT_MIN - The smallest integer supported

* PHP_INT_SIZE -  The size of an integer in bytes

### PHP has the following functions to check if the type of a variable is integer:

* is_int()

* is_integer() - alias of is_int()

* is_long() - alias of is_int()

## Floats

### PHP has the following predefined constants for floats (from PHP 7.2):

* PHP_FLOAT_MAX - The largest representable floating point number

* PHP_FLOAT_MIN - The smallest representable positive floating point number

* PHP_FLOAT_MAX - The smallest representable negative floating point number

* PHP_FLOAT_DIG - The number of decimal digits that can be rounded into a float and back without precision loss

* PHP_FLOAT_EPSILON - The smallest representable positive number x, so that x + 1.0 != 1.0

### PHP has the following functions to check if the type of a variable is float:

* is_float()

* is_double() - alias of is_float()

## Infinites

* A numeric value that is larger than `PHP_FLOAT_MAX` is considered infinite.

### PHP has the following functions to check if a numeric value is finite or infinite:

* is_finite()

* is_infinite()

## NaNs

* NaN stands for Not a Number.

* NaN is used for impossible mathematical operations.

### PHP has the following functions to check if a value is not a number:

* is_nan()

## Math

### Math Functions:

* `pi()` function returns the value of PI.

* `min()` and `max()` functions can be used to find the lowest or highest value in a list of arguments.

* `abs()` function returns the absolute (positive) value of a number

* `sqrt()` function returns the square root of a number.

* `round()` function rounds a floating-point number to its nearest integer.

* `rand()` function generates a random number.
	
	* To get more control over the random number, you can add the optional min and max parameters to specify the lowest integer and the highest integer to be returned.

## Constants

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

## Operators

### Arithmetic

* used with numeric values to perform common arithmetical operations, such as addition, subtraction, multiplication etc.

#### **Operator** --> **Name** --> **Example** --> **Result**

```
+ --> Addition --> $x + $y --> Sum of $x and $y	

- --> Subtraction --> $x - $y --> Difference of $x and $y	

* --> Multiplication --> $x * $y --> Product of $x and $y	

/ --> Division --> $x / $y --> Quotient of $x and $y	

% --> Modulus --> $x % $y --> Remainder of $x divided by $y	

** --> Exponentiation -->$x ** $y --> Result of raising $x to the $y'th power
```

### Assignment

#### **Assignment** --> **Same as...** --> **Description**

* The PHP assignment operators are used with numeric values to write a value to a variable.

```
x = y --> x = y --> The left operand gets set to the value of the expression on the right	

x += y --> x = x + y --> Addition	

x -= y --> x = x - y --> Subtraction	

x *= y --> x = x * y --> Multiplication	

x /= y --> x = x / y --> Division	

x %= y --> x = x % y --> Modulus
```

### Comparison

* The PHP comparison operators are used to compare two values (number or string).

#### **Operator** --> **Name** --> **Example** --> **Result**

```
== --> Equal --> $x == $y --> Returns true if $x is equal to $y	

=== --> Identical --> $x === $y --> Returns true if $x is equal to $y, and they are of the same type	

!= --> Not equal --> $x != $y --> Returns true if $x is not equal to $y	

<> --> Not equal --> $x <> $y --> Returns true if $x is not equal to $y	

!== --> Not identical --> $x !== $y --> Returns true if $x is not equal to $y, or they are not of the same type	

> --> Greater than --> $x > $y --> Returns true if $x is greater than $y	

< --> Less than --> $x < $y --> Returns true if $x is less than $y	

>= --> Greater than or equal to --> $x >= $y --> Returns true if $x is greater than or equal to $y	

<= --> Less than or equal to --> $x <= $y --> Returns true if $x is less than or equal to $y	

<=> --> Spaceship --> $x <=> $y -->Returns an integer less than, equal to, or greater than zero, depending on if $x is less than, equal to, or greater than $y. Introduced in PHP 7.
```

### Increment/Decrement

#### **Operator** --> **Name** --> **Description**

```
++$x --> Pre-increment --> Increments $x by one, then returns $x	

$x++ --> Post-increment --> Returns $x, then increments $x by one	

--$x --> Pre-decrement --> Decrements $x by one, then returns $x	

$x-- --> Post-decrement --> Returns $x, then decrements $x by one
```

### Logical

* logical operators are used to combine conditional statements.

#### **Operator** --> **Name** --> **Example** --> **Result**

```
and --> And --> $x and $y --> True if both $x and $y are true	

or --> Or --> $x or $y --> True if either $x or $y is true	

xor --> Xor --> $x xor $y --> True if either $x or $y is true, but not both	

&& --> And --> $x && $y --> True if both $x and $y are true	

|| --> Or --> $x || $y --> True if either $x or $y is true	

! --> Not --> !$x --> True if $x is not true
```

### String

#### **Operator** --> **Name** --> **Example** --> **Result**

```
. --> Concatenation --> $txt1 . $txt2 --> Concatenation of $txt1 and $txt2	

.= --> Concatenation assignment --> $txt1 .= $txt2 --> Appends $txt2 to $txt1
```

### Array

#### **Operator** --> **Name** --> **Example** --> **Result**

* array operators are used to compare arrays.

```
+ --> Union --> $x + $y --> Union of $x and $y	

== --> Equality --> $x == $y --> Returns true if $x and $y have the same key/value pairs	

=== --> Identity --> $x === $y --> Returns true if $x and $y have the same key/value pairs in the same order and of the same types

!= --> Inequality --> $x != $y --> Returns true if $x is not equal to $y	

<> --> Inequality --> $x <> $y --> Returns true if $x is not equal to $y	

!== --> Non-identity --> $x !== $y --> Returns true if $x is not identical to $y
```

### Conditional Assignment

#### **Operator** --> **Name** --> **Example** --> **Result**

* conditional assignment operators are used to set a value depending on conditions.

```
?: --> Ternary --> $x = expr1 ? expr2 : expr3 --> Returns the value of $x.  The value of $x is expr2 if expr1 = TRUE.  The value of $x is expr3 if expr1 = FALSE	

?? --> Null coalescing --> $x = expr1 ?? expr2 --> Returns the value of $x.  The value of $x is expr1 if expr1 exists, and is not NULL.  If expr1 does not exist, or is NULL, the value of $x is expr2.  Introduced in PHP 7
```

## Conditional Statments

* The `if...elseif...else` statement executes different codes for more than two conditions.

### Switch Statment

* The switch statement is used to perform different actions based on different conditions.

	* Use the switch statement to select one of many blocks of code to be executed.

* Syntax

```
switch (n) {
  case label1:
    code to be executed if n=label1;
    break;
  case label2:
    code to be executed if n=label2;
    break;
  case label3:
    code to be executed if n=label3;
    break;
    ...
  default:
    code to be executed if n is different from all labels;
}
```

* This is how it works: 
	
	* First we have a single expression n (most often a variable), that is evaluated once. The value of the expression is then compared with the values for each case in the structure. If there is a match, the block of code associated with that case is executed. 

	* Use break to prevent the code from running into the next case automatically. The default statement is used if no match is found.

## Loops

* In PHP, we have the following loop types:

	* while - loops through a block of code as long as the specified condition is true

	* do...while - loops through a block of code once, and then repeats the loop as long as the specified condition is true

	* for - loops through a block of code a specified number of times

	* foreach - loops through a block of code for each element in an array

### `do...while` Loop

* The `do...while` loop **will always execute the block of code once**, it will **then check the condition, and repeat** the loop while the specified condition is true.

* Syntax

```
do {
  code to be executed;
} while (condition is true);
```

### `for` Loop

* The for loop is used when you know in advance how many times the script should run.

* Syntax

```
for (init counter; test counter; increment counter) {
  code to be executed for each iteration;
}
```

* Parameters:

	* init counter: Initialize the loop counter value
		
		* test counter: Evaluated for each loop iteration. If it evaluates to TRUE, the loop continues. If it evaluates to FALSE, the loop ends.
		
		* increment counter: Increases the loop counter value

### `foreach` Loop

* The foreach loop **works only on arrays**, and is used to loop through each key/value pair in an array.

* Syntax

```
foreach ($array as $value) {
  code to be executed;
}
```

* For every loop iteration, the value of the current array element is assigned to $value and the array pointer is moved by one, until it reaches the last array element.

* Example using key/value pair array:

```
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $val) {
  echo "$x = $val<br>";
}
?>
```

### `break` and `continue`

* The `break` statement can be used to jump out of a loop.

	* Example:

	```
	<?php
	for ($x = 0; $x < 10; $x++) {
	  if ($x == 4) {
	    break;
	  }
	  echo "The number is: $x <br>";
	}
	?>
	```

* The `continue` statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

	* Example: 

	```
	<?php
	for ($x = 0; $x < 10; $x++) {
	  if ($x == 4) {
	    continue;
	  }
	  echo "The number is: $x <br>";
	}
	?>
	```

## Functions

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

## Arrays

* `array()` function is used to create an array

* In PHP, there are three types of arrays:

	* Indexed arrays - Arrays with a numeric index

	* Associative arrays - Arrays with named keys

	* Multidimensional arrays - Arrays containing one or more arrays

* `count()` function is used to return the length (the number of elements) of an array.

### Indexed Arrays

* Example of looping through an indexed array:

```
<?php
$cars = array("Volvo", "BMW", "Toyota");
$arrlength = count($cars);

for($x = 0; $x < $arrlength; $x++) {
  echo $cars[$x];
  echo "<br>";
}
?>
```

### Associative Arrays

* Associative arrays are arrays that use named keys that you assign to them.  The named keys can then be used in a script.

* Example:

```
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
echo "Peter is " . $age['Peter'] . " years old.";
?>
```

* To loop through and print all the values of an associative array, you could use a `foreach` loop.

* Example: 

```
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $x_value) {
  echo "Key=" . $x . ", Value=" . $x_value;
  echo "<br>";
}
?>
```

### Multi-dimensional Arrays

* A multidimensional array is an array containing one or more arrays.

* PHP supports multidimensional arrays that are two, three, four, five, or more levels deep. However, arrays more than three levels deep are hard to manage for most people.

#### The dimension of an array indicates the number of indices you need to select an element.

* For a **two-dimensional** array you need **two indices** to select an element

* For a **three-dimensional** array you need **three indices** to select an element

### Sorting Arrays

* The elements in an array can be sorted in alphabetical or numerical order, descending or ascending.

* Array sort functions:

	* sort() - sort arrays in ascending order
	
	* rsort() - sort arrays in descending order

	* asort() - sort associative arrays in ascending order, according to the value

	* ksort() - sort associative arrays in ascending order, according to the key

	* arsort() - sort associative arrays in descending order, according to the value

	* krsort() - sort associative arrays in descending order, according to the key

## Superglobals

* Some predefined variables in PHP are "superglobals", which means that they are always accessible, regardless of scope - and you can access them from any function, class or file without having to do anything special.

* The PHP superglobal variables are:

	* `$GLOBALS`
	
	* `$_SERVER`

	* `$_REQUEST`

	* `$_POST`

	* `$_GET`

	* `$_FILES`

	* `$_ENV`

	* `$_COOKIE`

	* `$_SESSION`

### `$GLOBALS`

* `$GLOBALS` is a PHP super global variable which is used to access global variables from anywhere in the PHP script (also from within functions or methods).

* PHP stores all global variables in an array called `$GLOBALS[index]`. The index holds the name of the variable.

* Example:

	```
	<?php
	$x = 75;
	$y = 25;
	 
	function addition() {
	  $GLOBALS['z'] = $GLOBALS['x'] + $GLOBALS['y'];
	}
	 
	addition();
	echo $z;
	?>
	```

### `$_SERVER`

* `$_SERVER` is a PHP super global variable which holds information about headers, paths, and script locations.

* The example below shows how to use some of the elements in `$_SERVER`:

	```
	<?php
	echo $_SERVER['PHP_SELF'];
	echo "<br>";
	echo $_SERVER['SERVER_NAME'];
	echo "<br>";
	echo $_SERVER['HTTP_HOST'];
	echo "<br>";
	echo $_SERVER['HTTP_REFERER'];
	echo "<br>";
	echo $_SERVER['HTTP_USER_AGENT'];
	echo "<br>";
	echo $_SERVER['SCRIPT_NAME'];
	?>
	```

The following table lists the most important elements that can go inside `$_SERVER`:
<br />

| Element/Code       | Description     |
| :------------- | :----------: |
|  `$_SERVER['PHP_SELF']` | Returns the filename of the currently executing script   |
| `$_SERVER['GATEWAY_INTERFACE']`   | Returns the version of the Common Gateway Interface (CGI) the server is using |
| `$_SERVER['SERVER_ADDR']` | Returns the IP address of the host server |
| `$_SERVER['SERVER_NAME']` | Returns the name of the host server |
| `$_SERVER['SERVER_SOFTWARE']` | Returns the server identification string |
| `$_SERVER['SERVER_PROTOCOL']` | Returns the name and revision of the information protocol (such as HTTP/1.1) |
| `$_SERVER['REQUEST_METHOD']` | Returns the request method used to access the page (such as POST) |
| `$_SERVER['REQUEST_TIME']` | Returns the timestamp of the start of the request (such as 1377687496) |
| `$_SERVER['QUERY_STRING']` | Returns the query string if the page is accessed via a query string |
| `$_SERVER['HTTP_ACCEPT']` | Returns the Accept header from the current request |
| `$_SERVER['HTTP_ACCEPT_CHARSET']` | Returns the Accept_Charset header from the current request (such as utf-8,ISO-8859-1) |
| `$_SERVER['HTTP_HOST']` | Returns the Host header from the current request |
| `$_SERVER['HTTP_REFERER']` | Returns the complete URL of the current page (not reliable because not all user-agents support it) |
| `$_SERVER['HTTPS']` | Is the script queried through a secure HTTP protocol |
| `$_SERVER['REMOTE_ADDR']` | Returns the IP address from where the user is viewing the current page |
| `$_SERVER['REMOTE_HOST']` | Returns the Host name from where the user is viewing the current page |
| `$_SERVER['REMOTE_PORT']` | Returns the port being used on the user's machine to communicate with the web server |
| `$_SERVER['SCRIPT_FILENAME']` | Returns the absolute pathname of the currently executing script |
| `$_SERVER['SERVER_ADMIN']` | Returns the value given to the SERVER_ADMIN directive in the web server configuration file (if your script runs on a virtual host, it will be the value defined for that virtual host) (such as someone@w3schools.com) |
| `$_SERVER['SERVER_PORT']` | Returns the port on the server machine being used by the web server for communication |
| `$_SERVER['SERVER_SIGNATURE']` | Returns the server version and virtual host name which are added to server-generated pages |
| `$_SERVER['PATH_TRANSLATED']` | Returns the file system based path to the current script |
| `$_SERVER['SCRIPT_NAME']` | Returns the path of the current script |
| `$_SERVER['SCRIPT_URI']` | Returns the URI of the current page |
<br />

### `$_REQUEST`

* `$_REQUEST` is a PHP super global variable which is used to collect data after submitting an HTML form.

* The example below shows a form with an input field and a submit button. When a user submits the data by clicking on "Submit", the form data is sent to the file specified in the action attribute of the `<form>` tag. In this example, we point to this file itself for processing form data. If you wish to use another PHP file to process form data, replace that with the filename of your choice. Then, we can use the super global variable `$_REQUEST` to collect the value of the input field:

	```
	<html>
	<body>

	<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
	  Name: <input type="text" name="fname">
	  <input type="submit">
	</form>

	<?php
	if ($_SERVER["REQUEST_METHOD"] == "POST") {
	  // collect value of input field
	  $name = $_REQUEST['fname'];
	  if (empty($name)) {
	    echo "Name is empty";
	  } else {
	    echo $name;
	  }
	}
	?>

	</body>
	</html>
	```

### `$_POST`

* `$_POST` is a PHP super global variable which is used to collect form data after submitting an HTML form with method="post". `$_POST` is also widely used to pass variables.

### `$_GET`

* `$_GET` is a PHP super global variable which is used to collect form data after submitting an HTML form with `method="get"`.

* `$_GET` can also collect data sent in the URL.

## Regular Expressions

* A regular expression is a sequence of characters that forms a search pattern. When you search for data in a text, you can use this search pattern to describe what you are searching for.

	* A regular expression can be a single character, or a more complicated pattern.

	* Regular expressions can be used to perform all types of text search and text replace operations.

* In PHP, regular expressions are strings composed of delimiters, a pattern and optional modifiers.

* Syntax

	* `$exp = "/w3schools/i";`

	* In the example above, `/` is the delimiter, `w3schools` is the pattern that is being searched for, and `i` is a modifier that makes the search case-insensitive.

	* The delimiter can be any character that is not a letter, number, backslash or space. The most common delimiter is the forward slash `/`, but when your pattern contains forward slashes it is convenient to choose other delimiters such as `#` or `~`.

### Regular Expression Functions

* PHP provides a variety of functions that allow you to use regular expressions. The `preg_match()`, `preg_match_all()` and `preg_replace()` functions are some of the most commonly used ones.

| Function | Description |
| :------------- | -----------: | 
| `preg_match()` | Returns 1 if the pattern was found in the string and 0 if not | 
| `preg_match_all()` | Returns the number of times the pattern was found in the string, which may also be 0 |
| `preg_replace()` | Returns a new string where matched patterns have been replaced with another string |

### Regular Expression Modifiers

* Modifiers can change how a search is performed.

| Modifier | Description |
| :------------- | -----------: |
|  `i` | Performs a case-insensitive search |
| `m` | Performs a multiline search (patterns that search for the beginning or end of a string will match the beginning or end of each line) |
| `u` | Enables correct matching of UTF-8 encoded patterns | 

### Regular Expression Patterns

* Brackets are used to find a range of characters.

| Expression | Description |
| :------------- | -----------: |
|  `[abc]` | Find one character from the options between the brackets |
| `[^abc]` | Find any character NOT between the brackets |
| `0-9` | Find one character from the range 0 to 9 | 

### Metacharacters

* Metacharacters are characters with a special meaning.

| Metacharacter | Description |
| :------------- | -----------: |
|  `|` | Find a match for any one of the patterns separated by | as in: cat/|dog/|fish |
| `.` | Find just one instance of any character |
| `^` | Finds a match as the beginning of a string as in: ^Hello | 
| `$` | Finds a match at the end of the string as in: World$ |
| `\d` | Find a digit |
| `\s` | Find a whitespace character |
| `\b` | Find a match at the beginning of a word like this: \bWORD, or at the end of a word like this: WORD\b |
| `\uxxxx` | Find the Unicode character specified by the hexadecimal number xxxx |

### Quantifiers

* Quantifiers define quantities.

| Quantifier | Description |
| :------------- | -----------: |
|  `n+` | Matches any string that contains at least one n |
| `n*` | Matches any string that contains zero or more occurrences of n |
| `n?` | Matches any string that contains zero or one occurrences of n | 
| `n{x}` | Matches any string that contains a sequence of X n's |
| `n{x,y}` | Matches any string that contains a sequence of X to Y n's |
| `n{x,}` | Matches any string that contains a sequence of at least X n's |

#### If your expression needs to search for one of the special characters you can use a backslash `\` to escape them. For example, to search for one or more question marks you can use the following expression: `$pattern = '/\?+/';`

### Grouping

* You can use parentheses to apply quantifiers to entire patterns. They also can be used to select parts of the pattern to be used as a match.

	* Example:
	```
	<?php
	$str = "Apples and bananas.";
	$pattern = "/ba(na){2}/i";
	echo preg_match($pattern, $str); // Outputs 1
	?>
	```

## Form Handling

* When the user fills out a form and clicks the submit button, the form data is sent for processing to a PHP file.

#### Proper validation of form data is important to protect your form from hackers and spammers!

### GET vs. POST

* Both GET and POST create an array (e.g. array( key1 => value1, key2 => value2, key3 => value3, ...)). This array holds key/value pairs, where keys are the names of the form controls and values are the input data from the user.

* Both GET and POST are treated as `$_GET` and `$_POST`. These are superglobals, which means that they are always accessible, regardless of scope - and you can access them from any function, class or file without having to do anything special.

* `$_GET` is an array of variables passed to the current script **via the URL parameters**.

* `$_POST` is an array of variables passed to the current script **via the HTTP POST method**.

### GET

* **Information** sent from a form with the GET method is **visible to everyone** (all variable names and values are displayed in the URL). 

* GET also has **limits on the amount of information** to send. The limitation is **about 2000 characters**. However, because the variables are displayed in the URL, it is **possible to bookmark** the page.

* Should only be used for sending non-sensitive data.

#### GET should **NEVER** be used for sending passwords or other **sensitive information**!

### POST

* **Information** sent from a form with the POST method is **invisible to others** (all names/values are embedded within the body of the HTTP request) and has **no limits on the amount of information** to send.

* Moreover POST supports advanced functionality such as support for multi-part binary input while uploading files to server.

* However, because the variables are not displayed in the URL, it is **not possible to bookmark the page**.

#### Developers prefer POST for sending form data.

## Form Validation

* `$_SERVER["PHP_SELF"]` is a super global variable that returns the filename of the currently executing script.

	* the `$_SERVER["PHP_SELF"]` sends the submitted form data to the page itself, instead of jumping to a different page. This way, the user will get error messages on the same page as the form. 

* `htmlspecialchars()` function converts special characters to HTML entities.

	* This means that it will replace HTML characters like `<` and `>` with `&lt`; and `&gt`;. This prevents attackers from exploiting the code by injecting HTML or Javascript code (Cross-site Scripting attacks) in forms.

		* Cross-site scripting (XSS) is a type of computer security vulnerability typically found in Web applications. XSS enables attackers to inject client-side script into Web pages viewed by other users.

		* Assume we have the following form in a page named "test_form.php":

		```<form method="post" action="<?php echo $_SERVER["PHP_SELF"];?>">```
		
		* Now, if a user enters the normal URL in the address bar like "http://www.example.com/test_form.php", the above code will be translated to:

		```<form method="post" action="test_form.php">```

		* So far, so good.  However, consider that a user enters the following URL in the address bar:

		```http://www.example.com/test_form.php/%22%3E%3Cscript%3Ealert('hacked')%3C/script%3E```

		* In this case, the above code will be translated to:

		```<form method="post" action="test_form.php/"><script>alert('hacked')</script>```

		* This code adds a script tag and an alert command. And when the page loads, the JavaScript code will be executed (the user will see an alert box). This is just a simple and harmless example how the `PHP_SELF` variable can be exploited.

		* Be aware that any JavaScript code can be added inside the `<script>` tag! A hacker can redirect the user to a file on another server, and that file can hold malicious code that can alter the global variables or submit the form to another address to save the user data, for example.

### How to Avoid `$_SERVER["PHP_SELF"]` Exploits

	* `$_SERVER["PHP_SELF"]` exploits can be avoided by using the `htmlspecialchars()` function.

	``` <form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>"> ```

	* The `htmlspecialchars()` function converts special characters to HTML entities. Now if the user tries to exploit the `PHP_SELF` variable, it will result in the following output:

	``` <form method="post" action="test_form.php/&quot;&gt;&lt;script&gt;alert('hacked')&lt;/script&gt;"> ```

	* The exploit attempt fails, and no harm is done!

### Validate Form Data With PHP

* The first thing we will do is to pass all variables through PHP's `htmlspecialchars()` function.

	* When we use the `htmlspecialchars()` function; then if a user tries to submit the following in a text field:

	`<script>location.href('http://www.hacked.com')</script>`

	* this would not be executed, because it would be saved as HTML escaped code, like this:

	`&lt;script&gt;location.href('http://www.hacked.com')&lt;/script&gt;`

	* The code is now safe to be displayed on a page or inside an e-mail.

* We will also do two more things when the user submits the form:

	* Strip unnecessary characters (extra space, tab, newline) from the user input data (with the `PHP trim()` function)

	* Remove backslashes `\` from the user input data (with the PHP `stripslashes()` function)

* The next step is to create a function that will do all the checking for us (which is much more convenient than writing the same code over and over again).

	* We will name the function `test_input()`.

* Now, we can check each `$_POST` variable with the `test_input()` function, and the script looks like this:

```
<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>
```

* Notice that at the start of the script, we check whether the form has been submitted using `$_SERVER["REQUEST_METHOD"]`. 

	* If the `REQUEST_METHOD` is `POST`, then the form has been submitted - and it should be validated. If it has not been submitted, skip the validation and display a blank form.

	* However, in the example above, all input fields are optional. The script works fine even if the user does not enter any data.

* The next step is to make input fields required and create error messages if needed.

## Required Form Fields

* These fields cannot be empty and must be filled out in the HTML form.

* In the following code we have added some new variables: $nameErr, $emailErr, $genderErr, and $websiteErr. 

	* These error variables will hold error messages for the required fields. 

		* We have also added an if else statement for each `$_POST` variable. 

			* This checks if the `$_POST` variable is empty (with the PHP `empty()` function). If it is empty, an error message is stored in the different error variables, and if it is not empty, it sends the user input data through the `test_input()` function:

```
<?php
// define variables and set to empty values
$nameErr = $emailErr = $genderErr = $websiteErr = "";
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  if (empty($_POST["name"])) {
    $nameErr = "Name is required";
  } else {
    $name = test_input($_POST["name"]);
  }

  if (empty($_POST["email"])) {
    $emailErr = "Email is required";
  } else {
    $email = test_input($_POST["email"]);
  }

  if (empty($_POST["website"])) {
    $website = "";
  } else {
    $website = test_input($_POST["website"]);
  }

  if (empty($_POST["comment"])) {
    $comment = "";
  } else {
    $comment = test_input($_POST["comment"]);
  }

  if (empty($_POST["gender"])) {
    $genderErr = "Gender is required";
  } else {
    $gender = test_input($_POST["gender"]);
  }
}
?>
```

* Then in the HTML form, we add a little script after each required field, which generates the correct error message if needed (that is if the user tries to submit the form without filling out the required fields):

```
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">

Name: <input type="text" name="name">
<span class="error">* <?php echo $nameErr;?></span>
<br><br>
E-mail:
<input type="text" name="email">
<span class="error">* <?php echo $emailErr;?></span>
<br><br>
Website:
<input type="text" name="website">
<span class="error"><?php echo $websiteErr;?></span>
<br><br>
Comment: <textarea name="comment" rows="5" cols="40"></textarea>
<br><br>
Gender:
<input type="radio" name="gender" value="female">Female
<input type="radio" name="gender" value="male">Male
<input type="radio" name="gender" value="other">Other
<span class="error">* <?php echo $genderErr;?></span>
<br><br>
<input type="submit" name="submit" value="Submit">

</form>
```

* The next step is to validate the input data, that is "Does the Name field contain only letters and whitespace?", and "Does the E-mail field contain a valid e-mail address syntax?", and if filled out, "Does the Website field contain a valid URL?".

### how to validate names, E-mails, and URLs

* The code below shows a simple way to check if the name field only contains letters, dashes, apostrophes and whitespaces. If the value of the name field is not valid, then store an error message:

```
$name = test_input($_POST["name"]);
if (!preg_match("/^[a-zA-Z-' ]*$/",$name)) {
  $nameErr = "Only letters and white space allowed";
}
```

#### The `preg_match()` function searches a string for pattern, returning true if the pattern exists, and false otherwise.

* The easiest and safest way to check whether an email address is well-formed is to use PHP's `filter_var()` function.

* In the code below, if the e-mail address is not well-formed, then store an error message:

```
$email = test_input($_POST["email"]);
if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
  $emailErr = "Invalid email format";
}
```

* The code below shows a way to check if a URL address syntax is valid (this regular expression also allows dashes in the URL). 
	
	* If the URL address syntax is not valid, then store an error message:

```
$website = test_input($_POST["website"]);
if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
  $websiteErr = "Invalid URL";
}
```

* The next step is to show how to prevent the form from emptying all the input fields when the user submits the form.

## How To Persist Form Values After Submit

* To show the values in the input fields after the user hits the submit button, we add a little PHP script inside the value attribute of the following input fields: name, email, and website.

	* In the comment textarea field, we put the script between the `<textarea>` and `</textarea>` tags. The little script outputs the value of the $name, $email, $website, and $comment variables.

	* Then, we also need to show which radio button that was checked. For this, we must manipulate the checked attribute (not the value attribute for radio buttons):

```
Name: <input type="text" name="name" value="<?php echo $name;?>">

E-mail: <input type="text" name="email" value="<?php echo $email;?>">

Website: <input type="text" name="website" value="<?php echo $website;?>">

Comment: <textarea name="comment" rows="5" cols="40"><?php echo $comment;?></textarea>

Gender:
<input type="radio" name="gender"
<?php if (isset($gender) && $gender=="female") echo "checked";?>
value="female">Female
<input type="radio" name="gender"
<?php if (isset($gender) && $gender=="male") echo "checked";?>
value="male">Male
<input type="radio" name="gender"
<?php if (isset($gender) && $gender=="other") echo "checked";?>
value="other">Other
```

## Date and Time

* `date()` function formats a timestamp to a more readable date and time.

	* Syntax

		* `date(format,timestamp)`

		| Parameter | Description |
		| :------------- | -----------: |
		| format | Required. Specifies the format of the timestamp |
		| timestamp | Optional. Specifies a timestamp. Default is the current date and time |

### Get a Date

* The required format parameter of the date() function specifies how to format the date (or time).

* Here are some characters that are commonly used for dates:

| Character | Description |
| :---- | -----------: |
| d | Represents the day of the month (01 to 31) |
| m | Represents a month (01 to 12) |
| Y | Represents a year (in four digits) |
| l (lowercase 'L') | Represents the day of the week |

	* Other characters, like"/", ".", or "-" can also be inserted between the characters to add additional formatting.

#### Auto Copyright year: `&copy; 2010-<?php echo date("Y");?>`

### Get a Time

* Here are some characters that are commonly used for times:

| Character | Description |
| :---- | -----------:|
| H | 24-hour format of an hour (00 to 23) |
| h | 12-hour format of an hour with leading zeros (01 to 12) |
| i | Minutes with leading zeros (00 to 59) |
| s | Seconds with leading zeros (00 to 59) |
| a | Lowercase Ante meridiem and Post meridiem (am or pm) |

#### Note that the PHP `date()` function will return the **current** date/time of the **server**!

### Get Time Zone

* If you need the time to be correct according to a specific location, you can set the timezone you want to use.

* The example below sets the timezone to "America/New_York", then outputs the current time in the specified format:

```
<?php
date_default_timezone_set("America/New_York");
echo "The time is " . date("h:i:sa");
?>
```

### Create Date With `mktime()`

* The optional timestamp parameter in the `date()` function specifies a timestamp. 
	
	* If omitted, the current date and time will be used (as in the examples above).

* The PHP `mktime()` function returns the Unix timestamp for a date. 

	* The Unix timestamp contains the number of seconds between the Unix Epoch (January 1 1970 00:00:00 GMT) and the time specified.

		* Syntax

			* `mktime(hour, minute, second, month, day, year)`

### Create Date From String With strtotime()

* The PHP `strtotime()` function is used to convert a human readable date string into a Unix timestamp (the number of seconds since January 1 1970 00:00:00 GMT).

	* Syntax
	
		* `strtotime(time, now)`

* PHP is quite clever about converting a string to a date, so you can put in various values:

	* Example:

```
<?php
$d=strtotime("tomorrow");
echo date("Y-m-d h:i:sa", $d) . "<br>";

$d=strtotime("next Saturday");
echo date("Y-m-d h:i:sa", $d) . "<br>";

$d=strtotime("+3 Months");
echo date("Y-m-d h:i:sa", $d) . "<br>";
?>
```

	* However, strtotime() is not perfect, so remember to check the strings you put in there.

## `include` and `require`

* The `include` (or `require`) statement takes all the text/code/markup that exists in the specified file and copies it into the file that uses the include statement.

* The `include` and `require` statements are identical, except upon failure:

	* `require` will produce a fatal error (`E_COMPILE_ERROR`) and stop the script

	* `include` will only produce a warning (`E_WARNING`) and the script will continue

* Syntax

	* `include 'filename'`;

	* `require 'filename'`;

#### Use `require` when the file **is required** by the application.

#### Use `include` when the file is **not required** and application should continue when file is not found.

## File Handling

* PHP has several functions for creating, reading, uploading, and editing files.

#### When you are manipulating files you must be very careful.

#### You can do a lot of damage if you do something wrong. Common errors are: editing the wrong file, filling a hard-drive with garbage data, and deleting the content of a file by accident.

 * `readfile()` function reads a file and writes it to the output buffer.  

### File Open/Read/Close

* A better method to open files is with the `fopen()` function. This function gives you more options than the `readfile()` function.

	* The first parameter of `fopen()` contains the name of the file to be opened and the second parameter specifies in which mode the file should be opened. 

	* The following example also generates a message if the fopen() function is unable to open the specified file:

	```
	<?php
	$myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");
	echo fread($myfile,filesize("webdictionary.txt"));
	fclose($myfile);
	?>
	```

| Modes | Description |
| :---- | -----------:|
| r | Open a file for read only. File pointer starts at the beginning of the file |
| w | Open a file for write only. Erases the contents of the file or creates a new file if it doesn't exist. File pointer starts at the beginning of the file |
| a | Open a file for write only. The existing data in file is preserved. File pointer starts at the end of the file. Creates a new file if the file doesn't exist |
| x | Creates a new file for write only. Returns FALSE and an error if file already exists |
| r+ | Open a file for read/write. File pointer starts at the beginning of the file |
| w+ | Open a file for read/write. Erases the contents of the file or creates a new file if it doesn't exist. File pointer starts at the beginning of the file |
| a+ | Open a file for read/write. The existing data in file is preserved. File pointer starts at the end of the file. Creates a new file if the file doesn't exist |
| x+ | Creates a new file for read/write. Returns FALSE and an error if file already exists |

* `fread()` function reads from an open file.

	* The first parameter contains the name of the file to read from and the second parameter specifies the maximum number of bytes to read.

	* The following PHP code reads the "webdictionary.txt" file to the end:

		* `fread($myfile,filesize("webdictionary.txt"));`

* `fclose()` function is used to close an open file.

	* `fclose()` requires the name of the file (or a variable that holds the filename) we want to close

#### It's a good programming practice to close all files after you have finished with them. You don't want an open file running around on your server taking up resources!

* `fgets()` function is used to read a single line from a file.

#### After a call to the `fgets()` function, the file pointer has moved to the next line.

* `feof()` function checks if the "end-of-file" (EOF) has been reached.

	* useful for looping through data of unknown length.

* `fgetc()` function is used to read a single character from a file.

#### After a call to the `fgetc()` function, the file pointer moves to the next character.

### File Create/Write

* `fopen()` function is also used to create a file.

	* If you use `fopen()` on a file that does not exist, it will create it, given that the file is opened for writing `w` or appending `a`.

	* The example below creates a new file called "testfile.txt". The file will be created in the same directory where the PHP code resides: 

		* `$myfile = fopen("testfile.txt", "w")`

#### If you are having errors when trying to get this code to run, check that you have granted your PHP file access to write information to the hard drive.

* `fwrite()` function is used to write to a file.

	* The first parameter of `fwrite()` contains the name of the file to write to and the second parameter is the string to be written.

	* The example below writes a couple of names into a new file called "newfile.txt":

	```
	<?php
	$myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
	$txt = "John Doe\n";
	fwrite($myfile, $txt);
	$txt = "Jane Doe\n";
	fwrite($myfile, $txt);
	fclose($myfile);
	?>
	```

### File Upload

#### First, ensure that PHP is configured to allow file uploads.

* In your "php.ini" file, search for the `file_uploads` directive, and set it to On.

#### Some rules to follow for the HTML upload form:

	* Make sure that the form uses method="post"

	* The form also needs the following attribute: `enctype="multipart/form-data"`. It specifies which content-type to use when submitting the form

	* Without the requirements above, the file upload will not work.

	* The `type="file"` attribute of the `<input>` tag shows the input field as a file-select control, with a "Browse" button next to the input control.

	* Upload form example:

	```
	<!DOCTYPE html>
	<html>
		<body>
			<form action="upload.php" method="post" enctype="multipart/form-data">
	  			Select image to upload:
	  			<input type="file" name="fileToUpload" id="fileToUpload">
	  			<input type="submit" value="Upload Image" name="submit">
			</form>
		</body>
	</html>
	```

* The "upload.php" file contains the code for uploading a file:

```
<?php
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["fileToUpload"]["name"]);
$uploadOk = 1;
$imageFileType = strtolower(pathinfo($target_file,PATHINFO_EXTENSION));
// Check if image file is a actual image or fake image
if(isset($_POST["submit"])) {
  $check = getimagesize($_FILES["fileToUpload"]["tmp_name"]);
  if($check !== false) {
    echo "File is an image - " . $check["mime"] . ".";
    $uploadOk = 1;
  } else {
    echo "File is not an image.";
    $uploadOk = 0;
  }
}
?>
```

* Script Explanation:

	* `$target_dir = "uploads/"` - specifies the directory where the file is going to be placed

	* `$target_file` specifies the path of the file to be uploaded

	* `$uploadOk=1` is not used yet (will be used later)

	* `$imageFileType` holds the file extension of the file (in lower case)

	* Next, check if the image file is an actual image or a fake image

#### You will need to create a new directory called "uploads" in the directory where "upload.php" file resides. The uploaded files will be saved there.

* Now we can add some restrictions.

* First, we will check if the file already exists in the "uploads" folder. If it does, an error message is displayed, and `$uploadOk` is set to 0:

```
// Check if file already exists
if (file_exists($target_file)) {
  echo "Sorry, file already exists.";
  $uploadOk = 0;
}
```

* Now, we want to check the size of the file. If the file is larger than 500KB, an error message is displayed, and `$uploadOk` is set to 0:

```
// Check file size
if ($_FILES["fileToUpload"]["size"] > 500000) {
  echo "Sorry, your file is too large.";
  $uploadOk = 0;
}
```

* The code below only allows users to upload JPG, JPEG, PNG, and GIF files. All other file types gives an error message before setting `$uploadOk` to 0:

```
// Allow certain file formats
if($imageFileType != "jpg" && $imageFileType != "png" && $imageFileType != "jpeg"
&& $imageFileType != "gif" ) {
  echo "Sorry, only JPG, JPEG, PNG & GIF files are allowed.";
  $uploadOk = 0;
}
```




