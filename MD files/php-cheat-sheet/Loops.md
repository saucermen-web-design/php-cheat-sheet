Loops

# Loops

* In PHP, we have the following loop types:

	* while - loops through a block of code as long as the specified condition is true

	* do...while - loops through a block of code once, and then repeats the loop as long as the specified condition is true

	* for - loops through a block of code a specified number of times

	* foreach - loops through a block of code for each element in an array

## `do...while` Loop

* The `do...while` loop **will always execute the block of code once**, it will **then check the condition, and repeat** the loop while the specified condition is true.

* Syntax

```
do {
  code to be executed;
} while (condition is true);
```

## `for` Loop

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

## `foreach` Loop

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

## `break` and `continue`

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